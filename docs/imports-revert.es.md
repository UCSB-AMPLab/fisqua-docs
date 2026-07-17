---
layout: docs
title: Reversión
parent: Importaciones
nav_order: 7
lang: es
permalink: /guia/importaciones/reversion/
description: Una importación terminada se puede deshacer como una ejecución nueva y registrada; nada se fuerza, nada se borra.
---

# Reversión

<p class="lede">Deshaz una importación terminada: como un acto registrado, nunca como un borrado.</p>

Una importación terminada se puede **revertir**: no se borra, sino que se deshace
como una **ejecución nueva y registrada**, con su propio mensaje obligatorio. La
reversión recorre la bitácora de la importación al revés:

- los registros que la importación **creó** se eliminan,
- los que **actualizó** se restauran a los valores que tenían antes, y
- cada cambio que hace para deshacer la importación queda **anotado en la
  bitácora de la reversión**.

Como la reversión también queda en la bitácora, ella misma es reversible:
revertir una reversión vuelve a aplicar la importación original.

<figure>
  <img src="{{ '/assets/img/imports-revert-es.png' | relative_url }}" alt="Los resultados de una reversión: totales de registros eliminados, restaurados y conservados, con un informe de reversión para descargar.">
  <figcaption>Una reversión es una ejecución registrada en sí misma, con totales honestos de lo que deshizo y lo que conservó.</figcaption>
</figure>

## Nada se fuerza

Una reversión nunca arrasa con el trabajo hecho después de la importación.
**Conserva e informa**:

- un registro **editado después** de la importación se conserva intacto, no se
  sobrescribe,
- un contenedor que la importación creó y que desde entonces **recibió registros
  nuevos dentro** se conserva, y
- un **código de referencia reutilizado** desde entonces queda bloqueado para no
  volver a crearse.

Los resultados de la ejecución indican con honestidad los totales de lo
**revertido y lo conservado**, según su motivo, con un informe para descargar.
Una importación se puede revertir **una sola vez**: no hay forma de forzarla, ni
reversión parcial, ni fusión.
