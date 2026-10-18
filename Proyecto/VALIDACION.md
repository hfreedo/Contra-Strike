# Validación v21

CAPX SHA-256: `91dbff5936b949fb2069203df21cb2d8814ab962aa49a5538c4a663e4d8ef585`

La revisión vigente abrió en Construct 2 Free con **88 eventos, 12 espacios libres y cuatro capas**. Pasaron **74 comprobaciones en la vista previa real**:

- 27 de combate, patrón completo, proyectiles, vida, victoria, menú y reinicio.
- 9 de orientación del disparo, terreno, patrullas, contacto, checkpoint y rayo.
- 13 del misil animado, impacto, daño, pausa y eliminación de la explosión, incluidos dos impactos simultáneos.
- 25 del título, botones, ayuda, reproducción y señal de audio, pausa, reanudación y transiciones.

Además, se observaron tres lanzamientos y caídas naturales del patrón: los tres crearon explosiones en la superficie de la plataforma final. La colocación usa `pisoFijo.BBoxTop-14`, que considera la rotación de los suelos.

Las pruebas preparan algunos casos reposicionando jugador y proyectiles. El ciclo completo del jefe se observa con protección temporal del jugador; el último impacto se prepara con un punto de vida. La prueba de audio instrumenta Web Audio para comprobar reproducción y señal, sin reemplazar la valoración auditiva de la mezcla. No es una partida manual completa ni una exportación validada en otros equipos.

La estructura ZIP/XML y la preservación de las instancias previas de juego se comprobaron. La verificación del paquete registra hashes de extracción.
