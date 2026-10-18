# Integración v20

Estos recursos ya están incorporados en el CAPX vigente. Las instrucciones de importación siguientes describen el paquete fuente para reutilizarlo.

# Jefe Mecha — redibujado IA v1

72 PNG (nueve secuencias de ocho cuadros), nueve GIF y nueve hojas de sprites. El dibujo fue redibujado con image_gen integrado a partir de las referencias originales. Las primeras tandas con recortes se descartaron; Produccion conserva sólo los atlas seleccionados y sus prompts. Originales/ en la carpeta superior conserva los 44 PNG recibidos, sin cambios.

## Ver las animaciones

Abrir Vista_previa.html. Los GIF tienen fondo oscuro para representar correctamente bordes, humo y resplandores semitransparentes. Repiten todas las secuencias para revisión, con una pausa al final de ataques y destrucción. No son los archivos de importación recomendados.

## Importar en Construct 2

1. Crear un Sprite visual llamado JefeMechaVisual. Abrir su editor de animaciones.
2. Crear las nueve animaciones con los nombres de las carpetas PNG/. Para cada una, importar sus ocho PNG ordenados 000.png a 007.png; eliminar el cuadro inicial vacío que añade el editor si queda uno extra.
3. Todos los cuadros tienen 640 × 512 px. Fijar el origen en **X=256, Y=416** en todos los cuadros de todas las animaciones. En coordenadas normalizadas: X=0,4; Y=0,8125. No recortar transparentes después de establecer el origen.
4. Si se usan Hojas/, importar cada hoja como rejilla de **2 columnas × 4 filas**, celdas 640 × 512 px; leer de izquierda a derecha y de arriba abajo.
5. Activar Loop sólo para reposo y movimiento. En ataques, danio, explosion y desaparicion desactivar Loop. Usar las velocidades de IMPORTAR_CONSTRUCT2.csv como punto de partida; corresponden a los GIF sin la pausa añadida de revisión.
6. Separar el sprite visual del cuerpo físico invisible. La transparencia y los efectos ocupan mucho espacio; no usar el rectángulo completo como colisión. Ajustar el cuerpo al torso/piernas y seguir su posición con el origen del sprite visual. No usar los proyectiles dibujados como colisión del jefe.
7. Al terminar un ataque o danio, volver a reposo/movimiento. Al terminar explosion, reproducir desaparicion; al acabar ésta, destruir el sprite. Para cambiar animación, hacerlo cuando cambia el estado, no reiniciarla cada tick.
8. Crear balas, rayos y misiles como objetos independientes para su daño y trayectoria. Los destellos de estas secuencias son visuales. No suponer daño automático por importar el dibujo.

## Cambios y alcance

- Orientación a la derecha común entre estados.
- Pasos alternados con rodillas y pies diferenciados; revisión de fases por contacto de cuadros.
- Preparación, descarga y recuperación de ataques; reacción de daño de retorno a reposo.
- Explosión progresiva y desaparición con último cuadro realmente transparente.
- Lienzo y origen de exportación comunes; registro técnico de desplazamientos por cuadro.
- Se recuperaron márgenes de proyectiles que cruzaban celdas en los atlas IA y se excluyeron contaminaciones de celdas vecinas. No se redibujaron piezas por código.

Es una primera versión artística redibujada. La IA conserva la identidad general, pero puede variar detalles pequeños de placas, armas y apoyos. Los ataques auxiliares y los rayos usan emisores de los hombros en esta interpretación. Revisar la escala, la continuidad entre estados y el ritmo dentro del juego antes de sustituir al jefe definitivo.

Validado: ocho PNG RGBA por secuencia, dimensiones/origen comunes, nueve GIF decodificables con duración completa, hojas 2×4, último cuadro de desaparición vacío y ausencia de recortes adicionales durante la exportación. No está integrado en un CAPX ni probado en Construct 2. El ZIP original permanece intacto.
