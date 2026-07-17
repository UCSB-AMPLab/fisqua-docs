---
layout: docs
title: Carga
parent: Importaciones
nav_order: 1
lang: es
permalink: /guia/importaciones/carga/
description: Prepara un CSV para empezar una importación, validado al entrar y sin corromper nada en silencio.
---

# Carga

<p class="lede">Prepara un CSV para empezar, validado al entrar y sin corromper nada en silencio.</p>

Una importación empieza en la página de importaciones, al cargar un CSV con tus
registros. El archivo se valida al entrar, y cada rechazo se explica con su
motivo, para que un archivo defectuoso se rechace con una razón en lugar de
entrar a medias:

- El archivo debe guardarse como texto en **UTF-8**, el formato que la mayoría de
  las herramientas ofrece con ese nombre. Cualquier otro se rechaza y no se
  prepara nada.
- Un archivo con **comillas sin cerrar**, **columnas con el nombre repetido** o
  **sin filas de datos** se rechaza antes de guardar nada.

Un archivo válido queda **preparado** —el archivo mismo, junto con una nota de
sus datos— y comienza la cadena de pasos. Preparar el archivo no altera el
catálogo: solo lo guarda para las revisiones que siguen.

<figure>
  <img src="{{ '/assets/img/imports-upload-es.png' | relative_url }}" alt="La página de importaciones: el área para cargar un CSV, la cadena de pasos y la lista de importaciones en curso.">
  <figcaption>La página de importaciones: prepara un CSV y retoma una importación en curso.</figcaption>
</figure>

## Descartar y eliminar

Una carga se puede **descartar** en cualquier momento antes de confirmarse.
Descartarla termina su recorrido pero conserva el archivo y su ficha, así que
una carga abandonada deja rastro. Una carga descartada se puede luego
**eliminar** por completo: se borran el archivo preparado, todo lo que se generó
a partir de él y su ficha.

Una carga que ya se **confirmó no se puede eliminar nunca**: forma parte del
registro permanente de una ejecución, y la constancia de lo que entró al
catálogo no es algo que la interfaz te deje borrar.
