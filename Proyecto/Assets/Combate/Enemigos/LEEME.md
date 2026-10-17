# Enemigos animados vigentes

Bipedo: GIF conter alien walking.gif; 4 cuadros a 10 fps; canvas 48×48. Corredor: alien 2 walking.gif; 12 cuadros a 10 fps; canvas 64×32. En cada carpeta, Original conserva el GIF; Caminar contiene los PNG RGBA numerados. manifest.json registra recorte, medidas y hashes.

Ya están incrustados en el CAPX. Para reimportar, usar los PNG numerados en orden; origen inferior central (0,5;1), bucle y 10 fps. Mantener un mismo polígono corporal por animación y excluir cola/espacios transparentes. Las dimensiones visibles y la colisión fueron comprobadas en la vista previa; no cambiar el tamaño de cada cuadro por separado.

Límites de patrulla y altura están asociados al terreno actual. Cambiar MinX/MaxX sin revisar el suelo puede sacar al enemigo de su plataforma. El contacto consume una carga y respeta CS_Invulnerable. No hay aún animaciones de ataque, daño o derrota ni proyectiles integrados.
