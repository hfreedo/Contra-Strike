# Contra Strike — UI de energía HD v2

Nueva versión gráfica creada con image_gen integrado a partir de la lámina Retro Diffusion y una captura de la partida. No es una ampliación por vecino más cercano: el atlas se regeneró con detalle nuevo. El atlas maestro mide 1254×1254 RGBA y conserva transparencia real en el exterior y en los tres huecos del marco.

## Archivos preparados

- marco.png: 224×48, tres huecos transparentes.
- lleno.png, vacio.png, danio.png: 50×24; regiones internas para colocar detrás del marco.
- icono.png: 32×32, insignia de rayo.
- boton.png: 144×38, botón sin texto.
- vista_3_cargas.png a vista_0_cargas.png: composiciones de referencia.
- vista_estados_hd.png: comparación de los cuatro estados a tamaño nativo.
- atlas_energia_hd.png: imagen maestra generada.
- prompt_imagegen.txt: prompt exacto utilizado y referencias descritas.
- manifest_hd.json: regiones de extracción, dimensiones, alfa, hashes y posiciones.

## Estado de integración

Este kit ya está integrado en Contra_Strike_con_menu.capx (v10). El contador numérico de vidas fue retirado: la cantidad restante se muestra únicamente en los segmentos. No importar las vistas ensambladas como piezas de la interfaz.

Para sustituir el arte, usar un marco de 224×48 y tres segmentos de 50×24. Colocar primero los segmentos y luego el marco encima. Sus centros, respecto a la esquina superior izquierda del marco, son (54,25), (112,25) y (170,25). Mantener los tres estados en el mismo canvas y con origen central. El icono puede ir a la derecha. Conservar las animaciones lleno, vacio y danio y las reglas de energía actuales.

Las regiones de los segmentos tienen relleno opaco en su interior; la máscara visual la proporciona el marco situado encima. Marco, icono y botón sí tienen exterior transparente. Los archivos finales se separaron y dimensionaron desde el atlas mediante preparación técnica; el dibujo del escenario se conserva; las piezas finales se incrustaron en el CAPX.

El ZIP contiene el kit gráfico, no una versión nueva del juego. La vista previa fue revisada visualmente y se comprobaron las dimensiones y el canal alfa. La integración y los estados se comprobaron en la vista previa real de Construct 2: 22 comprobaciones PASS. Evidencia en Proyecto/Pruebas_energia_HD.
