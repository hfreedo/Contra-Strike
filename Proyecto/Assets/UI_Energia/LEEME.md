# UI de energía — recursos de Retro Diffusion

Extraídos de la lámina de 256×256 proporcionada por el usuario. El original conserva su transparencia. Los archivos separados están en RGBA, con fondo transparente y píxeles originales; se quitó el fondo plano de los recortes y se unieron los tres fragmentos del botón excluyendo las guías de separación.

- marco.png: 107×24; tres huecos transparentes para los segmentos.
- lleno.png, vacio.png y danio.png: 25×12, mismo tamaño y origen central.
- icono.png: 15×15.
- boton.png: 72×19, sin guías de separación.
- lamina_original_retrodiffusion.png: referencia original sin modificaciones.
- manifest.json: dimensiones y rango alfa.

Ya están incrustados en Contra_Strike_con_menu.capx; no hay que importarlos otra vez. La barra y sus tres segmentos se muestran a escala 2 en la capa fija Energia_HUD. Las posiciones del marco y de sus huecos están definidas en el proyecto. Los estados de cada segmento se llaman lleno, vacio y danio.

Al reutilizarlos en otro proyecto, importar los tres estados como animaciones del mismo Sprite con un solo fotograma cada una, velocidad 0, origen central y colisiones deshabilitadas. Mantener el mismo tamaño entre estados; usar escalas enteras y muestreo de píxeles para conservar nitidez. El texto se edita en Construct 2 y no forma parte de los PNG.
