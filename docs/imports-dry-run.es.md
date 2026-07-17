---
layout: docs
title: Simulación
parent: Importaciones
nav_order: 4
lang: es
permalink: /guia/importaciones/simulacion/
description: La simulación clasifica cada fila sin escribir nada y te entrega dos informes para que los juzgues.
---

# Simulación

<p class="lede">Mira exactamente qué haría la importación, sin escribir nada.</p>

La simulación clasifica **cada fila** como **creación, actualización, omisión o
rechazo**, sin escribir nada en el catálogo. Produce dos archivos para descargar:

- un **informe** con los totales según su motivo, y
- un **archivo de rechazos** que lleva las columnas originales de cada fila
  rechazada tal cual, con su número de fila y el motivo por el que se rechazó.

No hay un **veredicto automático**. La simulación existe para que leas y juzgues
el resultado antes de comprometerte con él.

<figure>
  <img src="{{ '/assets/img/imports-dry-run-es.png' | relative_url }}" alt="El informe de simulación: totales de creaciones, actualizaciones, omisiones, rechazos y advertencias, con la tabla de filas rechazadas.">
  <figcaption>El informe de simulación: totales por resultado, y cada fila rechazada con su motivo.</figcaption>
</figure>

## Por qué unos problemas bloquean y otros no

El informe trata dos clases de problema de manera distinta, a propósito:

- Un **identificador dañado rechaza la fila**: un código de referencia en blanco,
  un duplicado dentro del archivo, un registro padre que no se encuentra o fue
  rechazado, un registro que termina siendo su propio antepasado, o un valor
  demasiado largo o inválido. Se cuenta como rechazo.
- Un **valor de descripción no reconocido adopta un valor predeterminado
  seguro** y se cuenta como advertencia, sin bloquear nunca.

El motivo: un identificador dañado estropearía cómo encaja el catálogo, así que
la fila no debe entrar; una descripción escueta o inesperada apenas está
incompleta, y un registro incompleto sigue siendo veraz.

## Actualizar los registros que ya existen

La opción **Actualizar los registros que ya existen** decide la suerte de las
filas cuyo código de referencia ya está en el catálogo: **desactivada** (lo
predeterminado) las omite; **activada** las actualiza en su lugar. Vuelve a
ejecutar la simulación para cambiar el modo y ver los nuevos totales.
