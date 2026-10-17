# Contra Strike — ambiente animado (v13)

Abrir Proyecto/Contra_Strike_con_menu.capx (desde esta carpeta: Contra_Strike_con_menu.capx). Reabrir el archivo vigente y no sobrescribirlo desde una pestaña antigua. El paquete completo es Contra_Strike_actual.zip.

## Qué está aplicado

Doce fuentes ambientales: dos conductos, dos respiraderos con luz, dos paneles, tres lámparas y tres grupos de cristales violetas. Cada una tiene un halo aditivo independiente, con ritmo y fase propios; el objeto visible también pulsa suavemente. Dos paneles emiten ráfagas de cuatro chispas cada uno. Son ocho sprites reutilizados: se desplazan siguiendo una trayectoria y se desvanecen, sin crear objetos indefinidamente.

No se utilizan vídeos. Las animaciones se calculan con eventos y dt, por lo que se detienen durante pausa, confirmación de salida y derrota. La tecla L permite comparar los halos/chispas encendidos y apagados durante la partida; las carcasas y cristales permanecen visibles. No se añadieron colisiones ni daño ambiental.

Esto simula iluminación mediante resplandores sobre el fondo; no calcula sombras, oclusión por paredes ni iluminación física. Los respiraderos todavía no emiten vapor, ni se animó la caída de gotas: esta revisión se centra en luz variable, cristales y chispas.

## Ajustar el efecto

En la hoja de comando, los eventos añadidos usan CS_AmbTiempo, CS_AmbActivado y CS_AmbIntensidad. La acción de inicio establece intensidad 0,75: bajar a 0,4 para un efecto tenue o subir hasta 1 para más intensidad. Cambiar también esa acción si se quiere otro valor inicial.

Las instancias de luz/halo tienen Fase, Frecuencia, MinLuz y MaxLuz. Frecuencia está en grados de seno por segundo: 90 produce un ciclo de 4 s. Las chispas tienen OrigenX/Y, VX/VY, Fase y Periodo. El tramo visible dura 0,35 s y luego permanece oculto hasta la siguiente ráfaga. Mantener las chispas cerca de sus aparatos.

Los objetos están en Layer 0, por encima del bitmap Sprite4 y por debajo del jugador y enemigos. Mover un aparato requiere mover también su halo y, si tiene chispas, ajustar sus OrigenX/Y. Todos tienen colisiones desactivadas.

## Recursos y pruebas

Assets/Decoracion_Ambiental/Animado_v1 contiene los PNG incrustados, el cristal original generado con image_gen y el manifiesto. Las carcasas proceden del kit v1 creado antes. Los halos y la chispa son texturas procedurales; sus variaciones se controlan en Construct 2. No reemplazar un Sprite por la vista previa GIF.

Pruebas_ambiente contiene capturas, una vista previa animada y el informe de 16 comprobaciones de luces, chispas, pausa, tecla L y regulación. Energia contiene 22 comprobaciones de UI, movimiento inicial, caída, derrota, reintento y menú. Para grabar el tramo de aparatos se reposicionó y suspendió temporalmente el cuerpo sólo en la vista previa. No equivale a completar una partida.

Se preservó íntegramente la edición local que estaba en disco (SHA anterior en integracion_ambiente.json): tipos, instancias, eventos, terreno, colisiones y demás recursos existentes. El respaldo está en Historial/Superadas/Contra_Strike/Antes_de_ambiente_8820145e09. Las pruebas y documentos anteriores corresponden a versiones previas.
