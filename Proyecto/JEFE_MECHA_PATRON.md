> Actualización v21: misil y explosión animados, sonido y checkpoint comprobados en motor. Consultar VALIDACION.md. Los detalles de la integración inicial que aparecen abajo se conservan como antecedente.

# Jefe mecha: uso y patrón

- Abrir `Contra_Strike_con_menu.capx` en Construct 2. Z dispara; flechas mueven y saltan; ESC pausa.
- Activación al llegar a X=2940. El jefe está en la plataforma final, alrededor de X=3300, con 24 puntos de vida. La activación repone tres cargas de energía.
- El jugador puede derrotar también a las dos patrullas con los disparos.
- Caer durante el combate tiene prevista reaparición en la arena (2980,343); la última corrección de selección del cuerpo aún requiere prueba en motor.

| Tiempo del ciclo | Comportamiento |
|---|---|
| 0–2 s | Movimiento y vulnerabilidad |
| 2–3 s | Aviso de cañón |
| 3–4 s | Disparo principal |
| 4–5,5 s | Recuperación vulnerable |
| 5,5–6,5 s | Aviso de ráfaga |
| 6,5–7,5 s | Cañones secundarios |
| 7,5–9 s | Recuperación vulnerable |
| 9–10,2 s | Marca y aviso de misiles |
| 10,2–11,4 s | Misiles hacia la posición marcada |
| 11,4–13 s | Recuperación vulnerable |
| 13–14 s | Aviso de rayo alto |
| 14–15 s | Rayo alto: permanecer en el suelo |
| 15–17 s | Recuperación vulnerable y repetición |

Los recursos importables están en `Assets/Combate/Jefe_Mecha/PNG`, con nueve subcarpetas. Son 640×512, origen común (256,416). `GIF` contiene vistas previas; `Hojas` contiene atlas. El CAPX ya incorpora los cuadros: no hace falta reimportarlos para jugar. `UI_Proyectiles` contiene barra, marcador y proyectiles.

Animaciones: reposo, movimiento, disparo_principal, canones_secundarios, rayos_laterales, misiles, danio, explosion y desaparicion.

## Validación

ZIP/XML y 72 cuadros verificados. 27 pruebas de combate y 22 de energía PASS en compilación previa a la última corrección de caída; esta corrección tiene validación XML, ejecución pendiente. Sin recorrido completo manual.

Las pruebas de motor emplean reposicionamiento para preparar la arena y protección temporal al observar el ciclo; la prueba de victoria prepara el último impacto con un punto de vida. No sustituyen una partida manual completa.
