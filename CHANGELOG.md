# Historial de cambios

Las etapas locales se documentan como hitos incluidos en la entrega actual; no se inventaron commits ni publicaciones retroactivas. Las versiones ya publicadas siguen disponibles en [Releases](https://github.com/hfreedo/Contra-Strike/releases) y en el historial de Git.

## v21.0 — 2026-10-18

- Título Flow integrado: 95 cuadros transparentes y respuesta al cursor.
- Doce sonidos sintetizados conectados a eventos, con OGG y M4A; música conservada a -18 dB.
- Pausa, reanudación, reinicio y salida controlan las etiquetas de audio.
- Misil de ocho cuadros orientado por su trayectoria; explosión de 19 cuadros y una reproducción en el impacto.
- Posición de explosión corregida con BBoxTop para respetar suelos girados.
- Checkpoint de la arena comprobado. 88 eventos, 12 espacios libres y cuatro capas.
- 74 pruebas puntuales de motor PASS y tres impactos de trayectoria natural observados.
- Inventario Excel actualizado a 59 recursos, 78 miniaturas y 13 audios catalogados.

## v20.0 — 2026-10-18

- Jefe mecha al final del mapa: nueve animaciones y 72 cuadros.
- Disparos del jugador con Z; patrullas derrotables.
- Vida del jefe, avisos, cañón, ráfagas, misiles marcados y rayo alto en ciclo de 17 segundos.
- Explosión, desaparición y victoria de demo; pausa y reinicio integrados.
- Reaparición prevista en arena durante el combate; corregida selección del cuerpo en la rama de caída.
- 81 eventos, 19 espacios libres y cuatro capas. Atmósfera y cámara conservadas.
- 49 pruebas de motor pasaron antes de la última corrección de caída; esa corrección queda pendiente de ejecución. ZIP/XML del CAPX final comprobados.

## v19.0 — 2026-10-17

- Eventos reducidos de 90 a 60: se liberan 30 y quedan 40 hasta el límite de 100 del proyecto.
- Nivel reorganizado de once a cuatro capas: mundo, atmósfera, HUD y paneles.
- Inicios de nivel, iluminación e indicador de energía consolidados.
- Paneles controlados por objeto y atmósfera anclada a cámara.
- Cierre de Ayuda y Créditos unificado con la condición `CS_PanelMenu != 0`.

## v18 — etapa local incorporada en v19

- Entrada sin bruma, viñeta al 35 % y dos halos iniciales reducidos.

## v17 — etapa local incorporada en v19

- Seguimiento horizontal con altura de cámara estable para mantener visible el suelo al saltar.

## v16 — etapa local incorporada en v19

- Penumbra exterior y viñeta reforzada fuera del mapa.

## v15 — etapa local incorporada en v19

- Intensidad de luces ajustada a 0,50; halos reducidos y bruma al 10 % / 3 %.

## v14 — etapa local incorporada en v19

- Contraste ambiental, halos y bruma animada.

## v13 — etapa local incorporada en v19

- Cristales luminosos, aparatos, chispas y luces variables; conmutación con L.

## v12.0 — 2026-10-17

- Dos enemigos alienígenas animados con patrullas y daño por contacto.
- Indicador de energía HD reducido al 80 %; velocidad y salto suavizados.
- Incluye las correcciones previas de apoyo, techo, animación y limpieza del mapa.

## v1.0 — 2026-10-16

- Primera publicación del proyecto y kit de menú; posterior integración del menú y fondo vertical.

## Validación de la entrega vigente

El editor Construct 2 Free confirmó 60 eventos. Antes de la última corrección de cierre de Ayuda pasaron 22 pruebas de energía/pausa/derrota/reinicio, 19 de cámara/saltos y nueve de capas/atmósfera. La corrección final de cierre tiene comprobación XML y tabla de estados; su ejecución en motor quedó pendiente. No se afirma un recorrido completo.
