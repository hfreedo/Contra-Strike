# Contra Strike — kit de menú v1

Assets generados con image_gen integrada, usando el escenario real y la portada escolar aprobada como referencias. Archivos originales copiados sin recortar, recolorear ni redimensionar. El escudo escolar se reutiliza desde la biblioteca transparente existente.

## Archivos y función

| Archivo dentro de Assets | Uso |
|---|---|
| Fondos/fondo_menu_alien.png | Fondo opaco del menú, sin títulos ni personajes. Es una ilustración de menú, no un fondo repetible del nivel. |
| Personaje/explorador_sin_armas.png | Ilustración transparente del explorador visto de espaldas, manos vacías. Capa independiente para el menú; no es una animación jugable. |
| Titulo/contra_strike.png | Título gráfico transparente, sin escudo ni frase añadida. |
| Interfaz/boton_alien_vacio.png | Una base reutilizable para JUGAR DEMO, CÓMO JUGAR, CRÉDITOS y otros botones. Las etiquetas deben ser Text editables. No son tres textos incrustados en imágenes distintas. |
| Interfaz/panel_alien_vacio.png | Panel transparente para instrucciones y créditos; también puede reutilizarse en pausa/resultados cuando se implementen. |
| Colegio/logo_colegio_transparente.png | Escudo escolar existente, separado del título y del fondo. |

Las dimensiones reales, transparencia y SHA256 están en inventario.json. prompts.json conserva las instrucciones de generación. La copia de trabajo está en `Menus animados/Assets/Contra_Strike/Menu`; la entrega organizada está en `Entregas/Actuales/Contra_Strike/Menu`.

## Importación al proyecto actual

1. Abrir una copia de `Juegos de alumnos/Contra Strike/juego.capx`. Esta entrega no modifica ese CAPX.
2. Mantener inicialmente la ventana global original **854 × 366**. Crear un layout `Menu` del mismo tamaño y una hoja `Menu_Events`. Configurarlo como inicio de la demo. No cambiar la ventana a 1280 × 720 solo para copiar una composición: afectaría también al juego.
3. Crear capas `Fondo`, `Personaje`, `Interfaz` y `Paneles`, en ese orden. Paneles comienza invisible. El menú no requiere ScrollTo ni Platform. Importar cada PNG individual como Sprite; sin Solid, Platform, Sine o colisión física.
4. Usar origen Centro en las imágenes. Copiar posiciones y tamaños de la columna **854x366** de posiciones_construct.csv/json. Conservar las proporciones: el fondo se centra y se escala para cubrir la ventana, recortando lo que salga del viewport. No estirarlo a una relación de aspecto diferente. El preset 1280x720 es una alternativa de composición para un proyecto que ya utilice esa ventana, no una orden de cambiar la cámara del alumno.
5. Usar tres tipos de Sprite para los botones si resulta más sencillo identificar cada clic, todos con la misma imagen de botón vacío. Poner un Text encima de cada uno: JUGAR DEMO, CÓMO JUGAR y CRÉDITOS. Centrar horizontal y verticalmente; reservar 17% de margen a cada lado y 26% arriba y abajo. Usar Segoe UI negrita, crema claro, sin saltos de línea. La referencia web usa 12 px para 854x366 y 24 px para 1280x720; ajustar en el motor si la exportación lo requiere. Evitar letras pegadas a las cápsulas violetas.
6. Añadir el título y el escudo como objetos separados. El nombre del grupo puede completarse en créditos con información real; no inventar autores.

## Acciones del menú

Añadir Mouse, Keyboard y una variable `PanelMenu=0` si no existen. Los nombres del layout de destino deben coincidir con los del proyecto, actualmente `Layout 1`.

- JUGAR DEMO: si PanelMenu=0, restaurar la escala de tiempo a 1 y ejecutar System → Go to layout → Layout 1. No iniciar una segunda música del juego desde el menú si ya comienza en la hoja del nivel.
- CÓMO JUGAR: PanelMenu=1, mostrar Paneles y escribir los controles reales: flechas izquierda/derecha para moverse y arriba para saltar. No anunciar disparos, armas, vidas o una meta funcional si no están implementados.
- CRÉDITOS: PanelMenu=2, mostrar el mismo panel con el nombre del colegio y autores reales.
- VOLVER o ESC: si PanelMenu>0, ocultar Paneles y restaurar PanelMenu=0.
- Bloquear clics del menú principal mientras PanelMenu>0. Ocultar una capa no sustituye esa condición: los clics deben estar limitados por estado.
- Hover o foco: brillo violeta o aumento moderado del tamaño respecto al tamaño base guardado. Restaurar siempre el tamaño base al salir; no multiplicar el tamaño cada tick.

Se puede animar el brillo del personaje o de la escena suavemente; la vista HTML incluye una referencia de iluminación que respeta movimiento reducido. Los PNG entregados son estáticos y no constituyen un video o una secuencia de fotogramas.

## Vista y pruebas

Abrir Vista_previa.html. Permite elegir 854x366 o 1280x720 y abrir ayuda/créditos. El botón JUGAR DEMO explica dónde conectarlo: esta página **no ejecuta Construct 2**. Los nombres de autores están pendientes. Las capturas de la entrega son composiciones de estos assets, no capturas de una partida.

Antes de usarlo en clase: abrir el CAPX modificado en el motor, comprobar recorte del fondo, textos, clics, ESC, salto al juego y música. El explorador sin armas de este kit solo cambia la presentación del menú; el personaje jugable original sigue usando sus propios sprites.
