---
layout: post
title: Debian 9 Pantalla negra
date: 2017-07-30 14:28:29 -0700
categories: debian 9 pantalla negra
---

Utilizar Debian siempre es garantía de estabilidad y seguridad, pero esta vez se tuvieron serios problemas ya que el escritorio (no importa cual se use) en cualquier momento se quedaba con la pantalla negra y no había manera de hacer nada más que reiniciar el equipo con el típico botonazo.

Después de investigar se descubrió que el problema era por tener dos tarjetas (Nvidia + Intel integrada), siempre se presentaba el error, sobre todo cuando se reactivaba después de una suspensión.

El problema se resuelve fácilmente, se crea el archivo /etc/modprobe.d/blacklist-intel.conf con el siguiente contenido:

    install i915 /usr/bin/false

Guardar y reiniciar.

Esto resuelve el problema.
