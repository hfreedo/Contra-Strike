# Decoración ambiental — Contra Strike v1

Cinco imágenes base estáticas, creadas con image_gen integrado usando el mapa limpio del juego como referencia. Paleta biomecánica cobriza, roja y violeta; señales ámbar. Los diseños se generaron por separado y se prepararon técnicamente mediante recorte del encuadre y escala proporcional por vecino más cercano. No son animaciones y todavía no están importados en el CAPX.

| Carpeta | Base_para_animar.png | Referencia_tamano_juego.png | Movimiento propuesto |
|---|---|---|---|
| Conducto | 256×128 | 128×64 | Pulsos ámbar que recorren los canales |
| Respiradero | 128×192 | 32×48 | Vapor tenue que sube y se disipa |
| Luz | 128×128 | 32×32 | Pulsación lenta de la lente violeta |
| Gotas | 64×128 | 16×32 | Gota que crece, cae y se repone |
| Panel | 192×128 | 48×32 | Parpadeo discreto de indicadores |

Todos los canvas de animación tienen ambos lados ≤256 px. Las medidas para el juego son propuestas iniciales y mantienen la relación de aspecto. El dibujo ocupa sólo parte del canvas: el respiradero conserva espacio superior para vapor y el gotero espacio inferior para la caída.

## Archivos de cada carpeta

- original_generado.png: salida original de alta resolución, sin modificaciones.
- Base_para_animar.png: PNG RGBA con transparencia y canvas preparado. Es la referencia que debes subir a Retro Diffusion.
- Referencia_tamano_juego.png: misma composición a la escala propuesta para el juego. Es una referencia estática, no reemplaza la futura animación.
- Prompt_generacion.txt: prompt exacto utilizado para crear el diseño.
- Prompt_animacion_RetroDiffusion.txt: instrucciones particulares de animación en inglés, listas para copiar.

Vista_previa.png muestra las cinco bases sobre fondo oscuro. Es sólo una composición para revisión y no debe importarse como un sprite. manifest.json registra tamaños, encuadres, alfa y hashes. Los PNG de trabajo tienen exterior transparente; se conservan algunos píxeles parcialmente transparentes en los contornos y resplandores.

## Para animar en Retro Diffusion

1. Cargar Base_para_animar.png del elemento elegido como cuadro inicial. Usar sus mismas dimensiones de salida; no escalar el mapa completo.
2. Copiar su Prompt_animacion_RetroDiffusion.txt. Pedir cámara fija, geometría inmóvil y ciclo continuo. El prompt especifica qué parte puede moverse.
3. Como punto de partida: conducto, luz y panel con 8 cuadros; vapor y gotas con 12. Reproducir a unos 6–8 fps. Son objetivos de producción, no una garantía del resultado generado ni de las opciones disponibles en cada modo.
4. Mantener el mismo tamaño, posición y origen en TODOS los cuadros. No recortar cada cuadro por su contenido: produciría desplazamientos al reproducirlos.
5. Revisar el enlace último–primer cuadro, la estabilidad de la carcasa, los bordes y la transparencia. Evitar movimiento de cámara, cambios de escala, aparición de símbolos, deformaciones o efectos que salgan cortados del canvas. Si el generador mueve o expande demasiado el efecto, reducir su amplitud y repetir.
6. Preferir cuadros PNG o una hoja de sprites con alfa. Si se recibe un GIF, comprobar que su transparencia sea real; el vapor suave puede perder niveles de alfa al exportar a ese formato. El fondo negro o el tablero dibujado dentro de la imagen no son transparencia.

## Para importar después en Construct 2

Crear un Sprite decorativo independiente por elemento. Importar sus cuadros PNG numerados en orden, activar bucle, usar el mismo origen central (0,5;0,5) y desactivar colisiones. Escalar el objeto completo a la medida de juego propuesta, sin deformar los cuadros. La referencia estática permite comprobar el encuadre antes de tener la animación.

Colocar por encima del bitmap del mapa y detrás del jugador/enemigos, en espacio del mundo (parallax 100%, no en la capa del HUD). En el proyecto actual puede hacerse mediante el orden Z de la capa del juego, sin cambiar su geometría. Los dibujos deben apoyar visualmente sobre paredes o techo, evitando los bordes de salto y los lugares de paso. No añadir Solid, Jumpthru ni daño a estos adornos.

Empezar con pocas copias. Variar el cuadro inicial y ligeramente la velocidad para que no pulsen todas a la vez. Evitar una capa por instancia. La animación debe detenerse durante la pausa del juego. Al integrarlos, revisar el resultado con la cámara real: tamaño, legibilidad de enemigos, contraste y que el adorno no parezca una plataforma o un objeto que se puede recoger.

## Estado de entrega

Se verificaron las cinco imágenes finales: dimensiones, canal alfa, márgenes transparentes y composición visual. No se modificaron el mapa, las colisiones, el CAPX ni sus reglas. Quedan pendientes generar las animaciones, revisar sus cuadros e importarlas en Construct 2.
