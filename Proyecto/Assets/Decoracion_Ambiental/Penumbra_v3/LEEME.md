# Contra Strike — penumbra exterior (v16)

La entrega vigente es Proyecto/Contra_Strike_con_menu.capx. Reabrir el CAPX para ver los cambios y no sobrescribirlo desde una pestaña anterior. El paquete completo es Contra_Strike_actual.zip.

Se reforzó la viñeta de los bordes de pantalla, manteniendo un centro más despejado. Además se añadió CS_PenumbraExterior en Atm_PenumbraExterior: una máscara oscura fija en coordenadas del mundo que cubre los márgenes fuera del bitmap Sprite4. El rectángulo del mapa es aproximadamente x=0,918–3486,918 e y=67,409–433,409. Debajo del terreno la sombra empieza cerca de y=421 y llega gradualmente a casi negro hacia y=526. Los lados y la zona superior tienen su propia transición.

La máscara exterior se dibuja después de los halos y la bruma, para que el vacío no se ilumine con esos efectos, y antes del HUD y los paneles. No tiene colisiones. La tecla L permite comparar toda la atmósfera con/sin efecto. La pausa conserva el estado visual.

Se mantienen los parámetros suaves de v15: intensidad global 0,50, bruma lejana al 10% y cercana al 3%; no se aumentaron las luces ni la neblina. No se cambiaron el mapa, las colisiones, los enemigos, el movimiento ni los eventos de jugabilidad. La penumbra es una máscara visual, no un sistema de sombras físicas.

Los PNG RGBA de la máscara y la viñeta están en Assets/Decoracion_Ambiental/Penumbra_v3. integracion_penumbra.json registra los hashes, cambios y respaldo. Si se cambia la posición, tamaño o extensión del mapa, debe recalcularse la máscara exterior; su degradado está asociado al escenario actual.

Pruebas_penumbra contiene capturas y nueve comprobaciones puntuales en la vista previa real de Construct 2: máscara, orden de capas, conservación de luz/bruma suaves, energía inicial, comparación L y pausa/reanudación. No equivale a completar una partida. Las otras carpetas de pruebas corresponden a revisiones previas.

Respaldo anterior: Entregas/Historial/Superadas/Contra_Strike/Antes_de_penumbra_4ec65d0564. Recursos y jugabilidad anteriores conservados; únicamente se ajustó la viñeta y se añadió la máscara con su capa, tipo, instancia y evento de opacidad.
