# Contra Strike — movimiento y patrullas (v12)

Abrir Contra_Strike_con_menu.capx en Construct 2. Reabrir el archivo vigente sin sobrescribirlo desde una pestaña anterior.

## Movimiento

Velocidad máxima 240 (antes 330), aceleración 1800 (2500), desaceleración 2200 (2500), fuerza de salto 560 (650) y gravedad 1150 (1500). Se conserva la velocidad máxima de caída de 1000 y el resto de propiedades. Sólo se modificaron esas cinco propiedades Platform del cuerpo físico; los eventos, la geometría, las colisiones, los PNG y la interfaz no cambiaron.

El avance es aproximadamente un 27% más lento. El salto conserva una altura teórica cercana a la anterior (136 frente a 141 px) y dura algo más (0,97 frente a 0,87 s en un plano libre ideal). El alcance horizontal teórico a velocidad máxima baja de 286 a 234 px. Las colisiones pueden acortar esas trayectorias.

## Interfaz y reglas

Se conserva el indicador HD reducido al 80%, sin contador numérico. La partida inicia con tres cargas; caer resta una carga y devuelve al inicio. Con cero aparece derrota: Reintentar/ENTER reinicia, Menú/ESC vuelve al menú. Se mantiene la confirmación de salida durante la partida y el parpadeo de 1,2 s. Las caídas y el contacto con los dos enemigos consumen energía; no hay una condición de victoria nueva.

Los recursos activos están en Assets/UI_Energia/HD_v2. El marco se muestra a 179,2×38,4, los segmentos a 40×19,2 y el icono a 25,6×25,6. El dibujo fuente mantiene su resolución.

## Comprobación y alcance

Pruebas_movimiento/verificacion_movimiento.json contiene los saltos aislados entre apoyos, incluidos accesos superiores y huecos. Cada caso coloca inicialmente el cuerpo sobre su apoyo y simula entradas normales de Platform sin alterar la física. Se admite aterrizar en un apoyo superior intermedio cuando la trayectoria lo intercepta. Pruebas_energia_actual contiene 22 comprobaciones reales de vidas, controles, animación, pausa, derrota, reintento y menú, además de la escala reducida del HUD. Los informes incluyen el SHA del CAPX comprobado.

Estas pruebas no equivalen a completar una partida. La prueba exploratoria de mantener avance y saltar automáticamente al aterrizar cae cerca de x=1379: los apoyos estrechos requieren decidir cuándo saltar. Su registro está en Pruebas_movimiento/recorrido_controlado.json. Se recomienda una pasada manual para valorar la sensación de control. Las carpetas Pruebas_energia_HD, Pruebas_energia, Pruebas_runtime y Pruebas_techo corresponden a revisiones anteriores.

ajuste_movimiento.json registra los valores anteriores y nuevos, los hashes y el respaldo en Historial/Superadas/Contra_Strike/Antes_de_movimiento_suave_8f3b2cb2eb. El original del alumno permanece intacto. El ZIP completo actualizado es ../Contra_Strike_actual.zip; su extracción se verifica con hashes y análisis XML.


## Enemigos patrulleros integrados (v12)

Se incorporaron los GIF del usuario `conter alien walking.gif` (4 cuadros) y `alien 2 walking.gif` (12 cuadros), ambos a 10 fps, conservando transparencia y duración. Los originales están en Assets/Combate/Enemigos/Bipedo/Original y Corredor/Original; los PNG separados en sus subcarpetas Caminar. Se usa un recorte común de la animación y escalado por vecino más cercano a 48×48 y 64×32, con origen central inferior y colisión fija del cuerpo que excluye la cola. No se generó ni redibujó el arte.

CS_AlienBipedo patrulla entre x=1090 y 1275 a 45 px/s, sobre UID 13; CS_AlienCorredor entre 1830 y 2000 a 55 px/s, sobre UID 3. Cada tipo tiene Direccion, MinX, MaxX y Velocidad editables en su instancia. Las patrullas son horizontales con altura fija y límites explícitos sobre su suelo; si se cambia su ubicación o el terreno, hay que recalcular límites y altura. No son enemigos con navegación automática por cualquier plataforma.

El contacto con el cuerpo del jugador consume una carga cuando la protección es cero. Usa el parpadeo/protección existente y la misma derrota, sin teletransportar al jugador al inicio por contacto. Las caídas conservan su reaparición anterior. Pausa y derrota detienen desplazamiento y animación. Reintentar restablece ambos enemigos y las tres cargas.

Pruebas_patrullas contiene 19 comprobaciones reales de movimiento, giros, orientación, cuadros, pausa, daño, protección, derrota y reintento. Pruebas_energia_patrullas contiene 22 comprobaciones de la UI, caída, controles y navegación. Se prepararon contactos mediante reposicionamiento del cuerpo; no equivalen a completar una partida. Las pruebas de versiones anteriores quedan como referencia histórica.

En esta revisión no se añaden disparos ni la derrota de los enemigos: sólo se recibieron animaciones de caminar. El combate y sus estados adicionales siguen descritos en Assets/Combate/PLAN_COMBATE.md. Respaldo anterior: Entregas/Historial/Superadas/Contra_Strike/Antes_de_patrullas_bd97c860cb.
