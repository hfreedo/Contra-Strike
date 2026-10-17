# Contra Strike — atmósfera y neblina (v14)

Abrir Contra_Strike_con_menu.capx en Construct 2; reabrir el archivo vigente, sin sobrescribirlo desde una pestaña antigua. El paquete completo está en ../Contra_Strike_actual.zip.

La nueva composición combina un tono azul oscuro con viñeta suave, doce halos ampliados 2,1 veces, dos planos de bruma suave en movimiento y diez motas flotantes reutilizadas. Los halos se dibujan por encima de la escena oscurecida, para iluminar visualmente el terreno y los personajes. El HUD y los paneles de menú quedan encima de la atmósfera y conservan su legibilidad. La intención es una caverna con volumen y contraste, inspirada en la referencia del usuario, manteniendo el arte propio del juego.

L compara el juego con/sin halos, bruma, viñeta y motas. Pausa y derrota congelan todos los efectos. No se generan objetos sin límite ni se añadieron colisiones ambientales. Se conservan los cristales, aparatos y chispas de v13. Es una simulación mediante capas: no calcula sombras, oclusión ni iluminación física de materiales.

## Ajustes

Atm_Tono: capa de tono/viñeta fija a la cámara; su acción de opacidad usa 100×CS_AmbActivado. Reducir ese 100 suaviza el oscurecimiento. Atm_Resplandores: doce halos en coordenadas del mundo, con MinLuz=34, MaxLuz=94 y tamaños ampliados. Atm_Bruma: dos texturas transparentes y diez motas en espacio de pantalla; las brumas usan opacidades 32 y 28, con desplazamientos sinusoidales lentos. Reducir esas opacidades aclara el aire.

La acción de inicio de esta revisión establece CS_AmbIntensidad=0,9 después de la inicialización anterior de v13. Editar esa última acción para variar el brillo global; un valor entre 0,5 y 1 sirve como intervalo inicial de ajuste. Fase y Frecuencia por halo conservan ritmos distintos. Todos los cálculos usan CS_AmbTiempo, que sólo avanza durante la partida activa.

## Verificación y recursos

Assets/Decoracion_Ambiental/Atmosfera_v2 contiene las texturas procedurales RGBA y el manifiesto. Las imágenes originales del escenario no se retocaron. integracion_atmosfera_v2.json registra los halos ajustados, texturas, hashes y respaldo. Todos los demás tipos, instancias, colisiones y eventos anteriores se conservaron íntegros respecto al archivo vigente al comenzar este cambio.

Pruebas_atmosfera_v2 contiene la comparación sin/con efecto, una vista previa GIF y 14 comprobaciones en motor real; su subcarpeta Energia contiene otras 22 de controles, UI, pausa, caída, derrota, reintento y menú. Son casos puntuales, no una partida completa. Para la captura del segundo tramo se suspendió temporalmente el cuerpo sólo en la vista previa.

El respaldo anterior se encuentra en Entregas/Historial/Superadas/Contra_Strike/Antes_de_atmosfera_v2_a8a78c8041. Las carpetas Pruebas_ambiente y otras pruebas anteriores son evidencia de versiones previas. El mapa, movimiento suave, sistema de tres cargas, enemigos patrulleros y menús se mantienen; los enemigos todavía no reciben disparos.
