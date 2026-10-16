# Contra Strike — juego con menú integrado

Abrir **Contra_Strike_con_menu.capx** en Construct 2. Es un proyecto completo: incluye el nivel original, sus imágenes, música y el menú nuevo. No hay que importar assets ni usar la vista HTML para jugar.

Al ejecutar desde el primer layout aparece Menu. JUGAR DEMO abre Layout 1; CÓMO JUGAR y CRÉDITOS muestran sus paneles. En la partida, MENÚ o ESC abre una confirmación: SÍ, VOLVER regresa al inicio, CANCELAR o ESC continúa. El regreso detiene la música y restaura la escala temporal. Si el editor ejecuta solo el layout seleccionado, seleccionar Menu antes de iniciar la vista previa.

Se conserva la ventana 854×366 y el recorrido, física, sprites y eventos originales. La animación inicial del jugador se corrige de Default a quieto. El explorador sin armas pertenece al menú; los sprites jugables originales se conservan. No se añadieron enemigos, puntuación ni condiciones nuevas de victoria a esta integración.

El archivo del alumno sigue intacto en Juegos de alumnos/Contra Strike/juego.capx. La carpeta Menu y su ZIP son recursos complementarios; el proyecto para abrir está aquí.

Verificación: 13 comprobaciones de estructura y modelo de navegación PASS. Incluyen referencias de imágenes y música, identificadores únicos, conexión al juego y regreso seguro. No se ha abierto ni ejecutado el motor Construct 2 en esta verificación. Falta confirmar la apertura, el aspecto y la navegación real en esa instalación.
