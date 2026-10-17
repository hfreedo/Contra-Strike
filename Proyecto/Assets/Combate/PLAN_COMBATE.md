# Propuesta de combate para Contra Strike

Estado actualizado v12: los dos GIF del usuario ya están integrados como patrullas con daño por contacto (Assets/Combate/Enemigos). Esta propuesta visual anterior y el diseño de disparos/derrota de enemigos siguen pendientes; los guardianes de la lámina no sustituyen los GIF elegidos.

## Primera demo

Empezar con un solo enemigo terrestre y el disparo del jugador. Añadir el dron después de comprobar impactos, daño, puntuación y reintento. Para una presentación escolar: robots/guardianes alienígenas, disparos de energía y desactivación con chispas, sin sangre.

| Elemento | Diseño y función | Valores iniciales para probar |
|---|---|---|
| Escarabajo centinela | Caparazón cobrizo, ojo cian, patas cortas; patrulla un suelo ancho | 1–2 impactos; 45–60 px/s; 100 puntos |
| Dron explorador | Esfera con aletas y lente luminosa; oscila en un corredor libre | 2 impactos; recorrido horizontal de 100–140 px; 150 puntos |
| Disparo del jugador | Pulso cian con centro blanco y estela corta | 650 px/s; 1 punto de daño; intervalo 0,22 s; vida máxima de 1 s |
| Impacto | Destello blanco/dorado y partículas pequeñas | 0,15–0,25 s, sin colisión |

Son valores de partida, no un balance ya probado. No colocar enemigos en los apoyos de 36–38 px ni junto al punto inicial: allí ya se exige precisión al saltar. Primera zona sugerida: patrulla terrestre en x=1110–1250 sobre el apoyo UID 13. Segunda zona: x=1810–1930 sobre UID 3. Dron opcional alrededor de (2350,280), con límites que eviten suelo, techo y plataformas. Confirmar todo visualmente dentro del motor antes de darlo por colocado.

## Recursos que necesita el combate final

Dimensiones propuestas del canvas nativo; la transparencia también ocupa parte del canvas. Ajustar la ocupación visible tras comparar con el jugador actual de 33×49. No deformar una imagen para forzar estas medidas.

| Objeto | Canvas propuesto | Animaciones necesarias |
|---|---|---|
| Escarabajo | 40×32 | reposo 2 cuadros; caminar 4–6 a 8 fps; recibir daño 2; desactivar 4–6 sin bucle |
| Dron | 32×32 | flotar 4 a 6–8 fps; aviso de ataque 2; disparar 2; desactivar 4–6 |
| Pulso del jugador | 24×12 | vuelo 3–4 a 12 fps, bucle |
| Destello de salida | 24×24 | 3 cuadros, sin bucle |
| Impacto | 32×32 | 4–6 cuadros, sin bucle |
| Pulso enemigo, etapa posterior | 16×16 | 3–4 cuadros, ámbar para distinguirlo del disparo cian |
| Jugador disparando | Canvas estable respecto a sus animaciones actuales | reposo/disparo, caminar/disparo y salto/disparo; o una capa de arma separada si el arte lo permite |

También faltan sonidos breves de disparo, impacto, desactivación y daño. La lámina de diseños propone el aspecto; no sustituye todos esos estados. La generación de imágenes puede cambiar anatomía o centro entre cuadros: revisar continuidad, silueta y alineación antes de importar una animación final. Para esta escala, finalizar cuadros en Aseprite/Piskel o editor equivalente resulta más controlable que convertir un video de Flow en sprites.

## Organización prevista

Conservar la lámina original en Disenos y las referencias existentes en Referencias. Cuando se produzcan los cuadros finales:

    Enemigos/Escarabajo/{Reposo,Caminar,Danio,Desactivar}/000.png
    Enemigos/Dron/{Flotar,Aviso,Disparar,Desactivar}/000.png
    Proyectiles/Jugador/Vuelo/000.png
    Proyectiles/Enemigo/Vuelo/000.png
    Efectos/{Salida,Impacto,Desactivacion}/000.png
    Audio/{disparo,impacto,desactivar,danio}

Cada animación debe tener cuadros con idéntico canvas y origen estable. Enemigos terrestres: ancla inferior central y cuerpo físico separado del dibujo. Dron/proyectiles/efectos: origen central. Importar cuadros en orden numérico, configurar velocidad y bucle; usar colisiones sencillas y pequeñas, excluyendo brillos y estelas. La lámina conceptual completa no se usa como un objeto en el nivel.

## Reglas de Construct 2

1. Usar una variable de orientación (-1/1) y un punto de imagen para la salida del disparo. Crear el pulso en ese punto, con ángulo de movimiento 0° o 180°. Comprobar disparo estando quieto, caminando y saltando en ambas direcciones, sin alterar el cuerpo físico del jugador.
2. Permitir disparar con Z únicamente mientras la partida esté activa y el tiempo de recarga sea cero. Al disparar, fijar la recarga a 0,22 s y descontarla con dt. Pausa, confirmación de salida y derrota deben bloquear los nuevos disparos.
3. Añadir Bullet al pulso, gravedad cero y rebote desactivado. Destruirlo al chocar con pisoFijo o Techo, al terminar su segundo de vida y al salir del layout. Definir deliberadamente si atraviesa pisoTraspasable; para esta demo propongo permitirlo. Las colisiones con el escenario se programan explícitamente.
4. En la colisión pulso-enemigo: destruir ese pulso, restar 1 a la vida de esa instancia, reproducir impacto. Al llegar a cero, cambiar una sola vez al estado desactivado, anular su daño/colisión de combate, sumar puntos una vez y eliminar el dibujo al finalizar su animación.
5. Los enemigos necesitan sus propios cuerpos y sensores de borde; no dibujarlos dentro del mapa. El centinela gira ante una pared, un borde o su límite de patrulla. El dron debe permanecer dentro de su corredor y no atravesar plataformas.
6. En contacto enemigo-jugador, aplicar daño únicamente con CS_EstadoEnergia=0 y CS_Invulnerable=0. Restar una carga, activar los 1,2 s de protección y actualizar el mismo indicador existente. Compartir la regla de derrota; no crear otro contador de vidas. Mantener el tratamiento de caídas que ya funciona y evitar dos descuentos en un mismo impacto.
7. Para la segunda etapa, avisar visualmente durante unos 0,4 s antes de que el dron dispare. Usar proyectiles ámbar, daño de una carga y cadencia lenta. Al principio, mantener un máximo de dos enemigos activos en pantalla.

Documentación oficial: [Bullet](https://www.construct.net/en/construct-2/manuals/construct-2/behavior-reference/bullet) y [Destroy outside layout](https://www.construct.net/en/construct-2/manuals/construct-2/behavior-reference/destroy-outside-layout). El segundo comportamiento elimina objetos fuera del layout, no simplemente fuera de cámara; por eso también se propone un tiempo de vida.

## Cierre de demo y comprobaciones

Una meta breve: desactivar tres guardianes identificados y llegar a la salida. Mostrar «Guardianes 0/3» y puntos; al cumplir ambos requisitos abrir «Demo completada» con Reintentar y Menú. No bloquear la salida con enemigos opcionales o imposibles de alcanzar. En reintento, restablecer enemigos, contador, puntos y las tres cargas; eliminar proyectiles pendientes al reiniciar o cambiar de layout.

Comprobar: orientación y salida del pulso, colisión con paredes, un solo daño por impacto, puntos una sola vez, protección ante contacto continuo, enemigo que no cae de su patrulla, pausa real de proyectiles/IA, derrota compartida, limpieza al volver al menú y reinicio completo. Después hacer una partida manual, porque los saltos aislados ya comprobados no prueban el equilibrio del combate.
