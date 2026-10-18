# Versión vigente v21: título animado, audio y explosión de impacto

Abrir `Contra_Strike_con_menu.capx` de esta carpeta. El título Flow de 95 cuadros ya está integrado en el menú. El misil usa los ocho cuadros proporcionados y gira según su velocidad. Al tocar el suelo crea una explosión de 19 cuadros, de una sola reproducción, anclada a la superficie real de la colisión.

Los 12 sonidos sintetizados están conectados: disparos del jugador y del mecha, aviso, lanzamiento de misil, explosión, daño, cursor, confirmación, victoria y ambiente. La pausa y el regreso al menú controlan el audio; la música previa se conserva a -18 dB. Se incluyen OGG y M4A para los efectos nuevos.

Controles: flechas para moverse y saltar, **Z para disparar**, ESC para pausa. Derrotar al mecha completa la demo. El proyecto utiliza 88 eventos y cuatro capas; quedan 12 espacios hasta 100.

Validación: 74 comprobaciones puntuales de motor PASS y tres impactos de misil con trayectoria natural observados. Consultar `VALIDACION.md`. Recorrido manual completo y mezcla auditiva final pendientes.

Recursos nuevos: `Assets/Audio/Propuesta_v1`, `Assets/Menu/Titulo_Flow_v1` y `Assets/Combate/Jefe_Mecha/Misil_Impacto_v1`. Ya están importados: no hay que volver a añadirlos para jugar. Cerrar las pestañas antiguas y reabrir este archivo antes de seguir editando.

## Documentación de versiones anteriores

# Versión vigente v20: jefe mecha animado

El mecha aparece al final del escenario con nueve animaciones (72 cuadros), 24 puntos de vida y un patrón de movimiento y ataques de 17 segundos. Disparar con **Z**; las flechas y ESC conservan sus funciones. Se mantienen la iluminación, la atmósfera y la cámara de la versión anterior.

El jefe avisa antes de atacar con cañón principal, ráfagas, misiles y rayo alto. Disparar durante las pausas vulnerables; el escudo rechaza impactos durante avisos y ataques. Los misiles muestran una marca previa y el rayo alto se evita permaneciendo en el suelo. Al derrotarlo se reproducen explosión y desaparición, seguidas del panel de demo completada.

El proyecto utiliza **81 eventos y cuatro capas**; quedan 19 espacios hasta el límite de 100. Guía: [JEFE_MECHA_PATRON.md](JEFE_MECHA_PATRON.md).

**Validación:** ZIP/XML y 72 cuadros verificados. 27 pruebas de combate y 22 de energía PASS en compilación previa a la última corrección de caída; esta corrección tiene validación XML, ejecución pendiente. Sin recorrido completo manual.

Cerrar las pestañas antiguas y reabrir el CAPX de esta carpeta para evitar guardar encima desde una versión anterior.

## Documentación anterior

# Versión vigente v19: 60 eventos y cuatro capas

El contador de Construct 2 Free confirma 60 eventos, frente a los 90 anteriores: se liberaron 30 y quedan 40 espacios hasta 100. El cómputo incluye nueve variables globales. El límite se comparte entre todas las hojas; un subevento también cuenta.

Se agruparon inicios de nivel, iluminación, vida y cierres duplicados. El nivel usa cuatro capas: Layer 0 (mundo y colisiones), Atmosfera, Energia_HUD (vida y botón Menú) y Paneles (confirmación y derrota). Para editar los paneles ocultos, seleccionar sus objetos y cambiar temporalmente su visibilidad; el inicio del nivel los vuelve a ocultar. El menú inicial conserva sus cuatro capas.

Cómo añadir eventos: abrir hoja de comando para la jugabilidad o Menu_Events para el menú; pulsar Añadir evento al final de la hoja. Los 40 espacios son el margen total del proyecto. Añadir acciones a un evento existente no añade otro evento al contador. Conservar el orden cuando unas acciones dependan de otras.

Se conservaron imágenes, UID, geometría, parámetros físicos y eventos de movimiento, animación y patrullas. La atmósfera mantiene su orden visual mediante coordenadas relativas a cámara; los paneles controlan visibilidad por objeto.

Pruebas: carga en Construct 2 y contador 60 confirmados; 22 verificaciones de energía/pausa/derrota/reinicio, 19 de cámara/saltos y nueve de capas/atmósfera pasaron sobre la compilación anterior a la corrección final del cierre de Ayuda. Esa corrección final tiene comprobación XML y tabla de estados; su nueva ejecución quedó pendiente porque el usuario detuvo Computer Use con Escape. No es una prueba de recorrido completo.

Respaldo anterior y hashes: optimizacion_eventos.json. Cerrar las pestañas antiguas y reabrir Contra_Strike_con_menu.capx desde esta carpeta; no guardar encima desde una versión anterior abierta. Las copias de verificación en Historial no son la entrega vigente.

## Documentación anterior

# Ajuste vigente: entrada clara (v18)

Se suavizó la viñeta al 35% de su fuerza en el punto de aparición y se retiró la bruma de esa zona. Los dos halos de la entrada son más pequeños y tenues para no velar al personaje ni al primer suelo. La viñeta se recupera gradualmente entre x=180 y 480; la bruma vuelve entre x=250 y 600. La penumbra fuera del mapa se conserva, igual que el encuadre vertical estable y la jugabilidad.

El cambio está aplicado al CAPX vigente y al ZIP. ZIP/XML y preservación comprobados; esta calibración no tiene una nueva prueba en motor. correccion_entrada_clara.json registra los valores y el respaldo anterior. Reabrir el archivo vigente y evitar sobrescribirlo desde una pestaña antigua.

## Documentación anterior

# Cambio vigente: cámara vertical estable (v17)

Abrir el CAPX vigente Contra_Strike_con_menu.capx de la carpeta Proyecto. Se deshabilitó el comportamiento ScrollTo del cuerpo físico y se añadió un evento Every tick → System: Scroll to position (CS_CuerpoJugador.X, Sprite4.Y-20). Así se conserva el seguimiento horizontal y se fija Y≈230,409 para este mapa horizontal. Con ventana 854×366, el encuadre vertical es aproximadamente y=47,409–413,409 y mantiene visibles los suelos bajos de y≈384,61 durante el salto. El cuerpo, la física, las colisiones y los eventos anteriores de jugabilidad permanecen idénticos.

No se modifica el menú, las luces, la neblina ni la penumbra. Para futuros niveles verticales habrá que diseñar otro seguimiento o límites por zonas; este encuadre está elegido para la distribución actual.

ZIP/XML y preservación comprobados. La prueba nueva en motor queda pendiente: Construct muestra el diálogo «Upgrade to Construct 3» que bloquea continuar y su cierre termina la aplicación. Las vistas previas locales anteriores dejaron de estar disponibles. No se debe presentar la evidencia de versiones anteriores como validación de esta cámara. El guion verificar_camara_estable_runtime.cjs está preparado para comprobar saltos desde suelo y plataformas superiores, seguimiento X y pausa cuando se recupere la ejecución.

correccion_camara.json registra el cambio y el respaldo en Historial/Superadas/Contra_Strike/Antes_de_camara_estable_55793c30e0. Reabrir el archivo vigente y evitar sobrescribirlo desde una pestaña anterior.

## Documentación de la versión anterior

# Contra Strike — penumbra exterior (v16)

La entrega vigente es Proyecto/Contra_Strike_con_menu.capx. Reabrir el CAPX para ver los cambios y no sobrescribirlo desde una pestaña anterior. El paquete completo es Contra_Strike_actual.zip.

Se reforzó la viñeta de los bordes de pantalla, manteniendo un centro más despejado. Además se añadió CS_PenumbraExterior en Atm_PenumbraExterior: una máscara oscura fija en coordenadas del mundo que cubre los márgenes fuera del bitmap Sprite4. El rectángulo del mapa es aproximadamente x=0,918–3486,918 e y=67,409–433,409. Debajo del terreno la sombra empieza cerca de y=421 y llega gradualmente a casi negro hacia y=526. Los lados y la zona superior tienen su propia transición.

La máscara exterior se dibuja después de los halos y la bruma, para que el vacío no se ilumine con esos efectos, y antes del HUD y los paneles. No tiene colisiones. La tecla L permite comparar toda la atmósfera con/sin efecto. La pausa conserva el estado visual.

Se mantienen los parámetros suaves de v15: intensidad global 0,50, bruma lejana al 10% y cercana al 3%; no se aumentaron las luces ni la neblina. No se cambiaron el mapa, las colisiones, los enemigos, el movimiento ni los eventos de jugabilidad. La penumbra es una máscara visual, no un sistema de sombras físicas.

Los PNG RGBA de la máscara y la viñeta están en Assets/Decoracion_Ambiental/Penumbra_v3. integracion_penumbra.json registra los hashes, cambios y respaldo. Si se cambia la posición, tamaño o extensión del mapa, debe recalcularse la máscara exterior; su degradado está asociado al escenario actual.

Pruebas_penumbra contiene capturas y nueve comprobaciones puntuales en la vista previa real de Construct 2: máscara, orden de capas, conservación de luz/bruma suaves, energía inicial, comparación L y pausa/reanudación. No equivale a completar una partida. Las otras carpetas de pruebas corresponden a revisiones previas.

Respaldo anterior: Entregas/Historial/Superadas/Contra_Strike/Antes_de_penumbra_4ec65d0564. Recursos y jugabilidad anteriores conservados; únicamente se ajustó la viñeta y se añadió la máscara con su capa, tipo, instancia y evento de opacidad.
