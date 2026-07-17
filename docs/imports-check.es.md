---
layout: docs
title: Verificación
parent: Importaciones
nav_order: 3
lang: es
permalink: /guia/importaciones/verificacion/
description: La verificación muestra todos los problemas que causará tu archivo antes de ejecutar nada.
---

# Verificación

<p class="lede">Todos los problemas que causará tu archivo, a la vista antes de ejecutar nada.</p>

Antes de ejecutar nada, la verificación coteja el archivo preparado con el
perfil de asignación elegido y con el catálogo actual, y muestra todos los
problemas que causaría la importación, agrupados **por tipo** y no fila por
fila: así, un fallo que se repite en mil filas es una sola decisión y no mil.

<figure>
  <img src="{{ '/docs-assets/img/imports-check-es.png' | relative_url }}" alt="La pantalla de verificación con los hallazgos agrupados por tipo, cada uno con sus opciones.">
  <figcaption>La verificación agrupa los hallazgos por tipo y expone las opciones de cada uno.</figcaption>
</figure>

## Los tres tipos de hallazgo

Cada tipo trae sus opciones ya planteadas, para que nunca tengas que adivinar
qué hacer:

- Un hallazgo **bloqueante** señala filas que no se pueden importar tal como
  están: un código de referencia duplicado, o un registro padre que no se
  encuentra en el archivo ni en el catálogo. Esas filas se rechazarán a menos
  que corrijas el archivo y lo cargues de nuevo. No detiene la simulación; las
  filas señaladas simplemente se rechazan.
- Un hallazgo que exige una **decisión** te pide elegir, y es el único tipo que
  detiene la simulación. El caso habitual es un campo obligatorio que algunas
  filas dejan en blanco: aceptas la ausencia o regresas al archivo para
  corregirlo. La simulación queda bloqueada hasta que se responda cada decisión.
- Un hallazgo **informativo** solo explica algo que conviene saber; no bloquea
  nada.

## Aceptar una ausencia siempre deja constancia

Aceptar una ausencia no la borra. Las filas afectadas se importan con
la ausencia registrada como una advertencia, con su motivo, en todos los
informes posteriores, y las aceptaciones quedan guardadas en la carga y se
copian al registro permanente de la ejecución cuando la importación se confirma.
Así, quien lo revise después siempre puede ver qué se dejó pasar y por qué.

Algunos fallos no se pueden aceptar nunca. Un **identificador dañado** —un código
de referencia en blanco o duplicado, un registro padre que no se puede resolver—
siempre provoca el rechazo de la fila, porque dejar entrar uno estropearía cómo
encaja el catálogo en lugar de dejar apenas un campo incompleto.

## Las verificaciones se guardan

El resultado de la verificación se guarda, de modo que la página de
importaciones puede mostrar el estado de cada carga en curso sin recalcularlo.
Si editas el perfil de asignación después de una verificación, esa carga vuelve
a **Verificación pendiente**: el resultado anterior ya no describe lo que haría
el perfil actual, y la verificación debe ejecutarse de nuevo antes de que la
simulación pueda desbloquearse.
