> Integrado en el CAPX v21. Los formatos de runtime incluidos son OGG y M4A; WAV se conserva como fuente. Reproducción, pausa y señal comprobadas en motor. La mezcla auditiva final está pendiente.

# Propuesta de sonidos v1

Efectos sintetizados originales mediante osciladores y ruido. No son grabaciones ni voces generadas por IA. WAV PCM mono, 44,1 kHz, 16 bits; OGG Vorbis para el juego. Los valores en manifest.json son un punto de partida de mezcla, no niveles finales aprobados.

Escuchar.html permite revisar cada efecto. Escuchar_efectos.wav reúne los efectos, separados por silencios. El ambiente se escucha por separado.

## Construct 2

Importar los WAV mediante Import sounds y comprobar que Construct 2 prepara los formatos de reproducción necesarios. Los OGG ya están disponibles como alternativa para el runtime web; verificar compatibilidad de los navegadores objetivo antes de publicar. Añadir el objeto Audio si no existe.

Conectar Play (not looping) a los eventos descritos en manifest.json, aprovechando las acciones de creación y de daño ya existentes. No crear un evento Every tick que reproduzca sonidos. El misil suena al lanzarse; la explosión al crear CS_ExplosionMisil, no en cada fotograma ni en cada tick de contacto con el suelo. Alternar los tres disparos evita monotonía. No reproducir ambos sonidos de lanzamiento e impacto al mismo tiempo.

El ambiente sí usa Loop, con etiqueta ambiente y volumen sugerido -22 dB. Al volver al menú, detener esa etiqueta. Pausar/reanudar sus etiquetas junto al estado de pausa: detener la escala de tiempo del juego no basta para garantizar que el audio se pause.

La respuesta del cursor debe sonar una vez al entrar al botón, no repetirse mientras permanece encima. Victoria y derrota también requieren transición única.

## Alcance

Se verificaron formatos, duración, valores finitos y margen de pico. Son una propuesta para evaluación auditiva; ya están conectados a eventos del CAPX v21. La mezcla y sincronización requieren una prueba de juego.
