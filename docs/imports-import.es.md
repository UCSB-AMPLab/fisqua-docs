---
layout: docs
title: Importación
parent: Importaciones
nav_order: 5
lang: es
permalink: /guia/importaciones/importacion/
description: "Confirmar es un acto aparte y deliberado: con condiciones, registrado en bitácora y reversible."
---

# Importación

<p class="lede">Confirma la importación: un acto deliberado, con condiciones y reversible.</p>

Confirmar la importación es un **acto aparte y deliberado**, no algo que ocurra
solo cuando termina la simulación. Antes de que se ejecute, deben cumplirse dos
cosas: debe existir un informe de simulación, y el perfil de asignación no puede
haber cambiado desde ese informe. Si editas el perfil después de una simulación,
Fisqua pide una simulación nueva primero.

Para confirmar, escribes un **mensaje obligatorio** de la ejecución (y una
justificación opcional), eliges el **repositorio** donde se archivan los
registros nuevos y confirmas que **revisaste el informe**.

<figure>
  <img src="{{ '/assets/img/imports-import-es.png' | relative_url }}" alt="El paso de importación: el mensaje de la ejecución, el selector de repositorio y la confirmación de revisión que activa el botón de confirmar.">
  <figcaption>El paso de importación: un mensaje de la ejecución, el repositorio donde se archivan los registros y la confirmación de revisión.</figcaption>
</figure>

## El botón nunca se niega en silencio

Mientras falte alguna condición, el botón de confirmar está **desactivado e
indica su motivo** en una línea debajo: aún no hay informe de simulación, quedan
decisiones pendientes, el perfil cambió desde el informe, o no hay repositorio
donde archivar los registros nuevos. Cuando la solución está en otra parte, el
motivo **enlaza a ella**: un espacio de trabajo sin repositorio recibe un enlace
que explica qué es un repositorio, te lleva a crear uno y te devuelve al
formulario de confirmación donde lo dejaste.

## Qué hace la importación

La importación vuelve a leer cada fila directamente de tu archivo preparado —el
informe de la simulación te ayudó a decidir, pero nunca es lo que se escribe—. Va
recorriendo las filas con calma y, si algo la interrumpe, retoma donde quedó sin
importar nada dos veces.

Los registros se **crean o se actualizan, nunca se eliminan**, y se emparejan por
el código de referencia. Las actualizaciones son cuidadosas:

- una **celda en blanco conserva** el valor que ya había,
- los **códigos antiguos se conservan** junto a los nuevos, sin perder ninguno, y
- una fila que ya coincide **se deja intacta** y se cuenta como sin cambios.

Una importación **nunca vuelve a archivar un registro que ya existe**: si el
archivo le da otro registro padre, el informe lo señala pero la importación lo
deja donde está. Cada carga se importa **una sola vez**.

Cada cambio queda **anotado en una bitácora, junto con el valor que reemplazó**,
y esa bitácora es lo que te permite deshacer la importación.
