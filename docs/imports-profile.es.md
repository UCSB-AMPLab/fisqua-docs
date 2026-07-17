---
layout: docs
title: Perfil
parent: Importaciones
nav_order: 2
lang: es
permalink: /guia/importaciones/perfil/
description: Un perfil de asignación vincula las columnas de tu hoja de cálculo con los campos de descripción de Fisqua.
---

# Perfil

<p class="lede">Dile a Fisqua qué significan tus columnas: una vez, y para reutilizar.</p>

Un **perfil de asignación** vincula las columnas de tu hoja de cálculo con los
campos de descripción del espacio de trabajo. Las columnas se **emparejan por el
nombre del encabezado, nunca por la posición**, de modo que una exportación con
las columnas en otro orden se asigna igual de bien. Cada columna también se puede
ajustar al entrar, según la forma en que lleguen las exportaciones reales: se
puede copiar tal cual, darle un valor de reemplazo cuando la celda está en
blanco, fijarla en un valor constante, unirla con otras columnas, separarla
cuando una celda trae varios valores, cotejarla con tu vocabulario controlado,
leerla como fecha o arrastrar el valor de la fila anterior.

El perfil se elige en el paso de [Verificación](../verificacion/), y tanto la
verificación como la simulación clasifican cada fila con él.

<figure>
  <img src="{{ '/assets/img/imports-profile-es.png' | relative_url }}" alt="El editor de perfiles de asignación: cada columna de origen junto a un campo de descripción y una transformación.">
  <figcaption>Cada columna de origen se empareja con un campo de descripción, y con una transformación donde el valor necesita ajustarse.</figcaption>
</figure>

## De dónde sale un perfil

Puedes armar uno **desde cero** o partir de una **plantilla de inicio** para un
formato que ya manejes:

- el CSV en ISAD(G) de AtoM
- el inventario FUID del AGN de Colombia
- el listado del Endangered Archives Programme (British Library)
- la plantilla a nivel de ítem del Modern Endangered Archives Program (UCLA)

Estas plantillas de inicio solo se ofrecen para las normas de descripción a las
que corresponden. Elegir una crea un perfil común y editable, propio del espacio
de trabajo, y lo abre en el editor para revisarlo antes del primer uso. Los
ajustes posteriores a una plantilla de inicio no alteran los perfiles ya creados
a partir de ella.

Para un catálogo que empieza de cero, descarga la **plantilla de Fisqua** —un CSV
generado a partir de la norma de descripción del propio espacio de trabajo, una
columna por campo— con su perfil ya construido, de modo que una plantilla
diligenciada no necesita ninguna asignación.

## Nombre y versiones

Los perfiles son **propios de cada espacio de trabajo**, con nombre único y
**versión**, pero la versión solo cambia cuando cambia la asignación misma. Eso
es lo que permite que una simulación fije el perfil exacto con el que se ejecutó:
si editas la asignación después de una simulación, esa carga regresa a la
verificación, de modo que el informe nunca puede describir una asignación que ya
no existe.
