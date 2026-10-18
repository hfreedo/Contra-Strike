# 🪐 Contra Strike — Un Mundo por Descubrir

## Versión vigente: v21.0

Título Flow animado, sonido sincronizado y misil con explosión en el punto de impacto. Incluye el jefe mecha; 88 eventos y cuatro capas.

- **Abrir en Construct 2:** [`Proyecto/Contra_Strike_con_menu.capx`](Proyecto/Contra_Strike_con_menu.capx).
- **Descargar:** [CAPX](https://github.com/hfreedo/Contra-Strike/releases/download/v21.0/Contra_Strike_con_menu.capx) · [paquete de proyecto y recursos](https://github.com/hfreedo/Contra-Strike/releases/download/v21.0/Contra_Strike_actual_v21.zip).
- **Historial:** [CHANGELOG.md](CHANGELOG.md). Las versiones anteriores se conservan en Git y Releases.
- **Pruebas y límites:** [Proyecto/VALIDACION.md](Proyecto/VALIDACION.md). Los recursos de etapas anteriores conservan sus nombres originales.


<p align="center">
  <img src="Portadas/Contra_Strike_PC_Demo.png" alt="Portada Contra Strike - Un Mundo por Descubrir" width="760">
</p>

<p align="center">
  <a href="https://github.com/hfreedo/Contra-Strike/releases/latest/download/Contra_Strike_con_menu.capx">
    <img src="https://img.shields.io/badge/🎮_Descargar_Juego_Integrado_v21-Contra__Strike__con__menu.capx-22c55e?style=for-the-badge" alt="Descargar CAPX v21 con Menú y Patrullas">
  </a>
  <a href="https://github.com/hfreedo/Contra-Strike/raw/refs/heads/main/Proyecto/Contra_Strike_original.capx">
    <img src="https://img.shields.io/badge/🕹️_Descargar_Proyecto_Original-Contra__Strike__original.capx-7c3aed?style=for-the-badge" alt="Descargar CAPX Original">
  </a>
</p>

---

## 👋 ¡Bienvenidos al repositorio oficial de Contra Strike!

Este repositorio contiene la versión más avanzada del proyecto **Contra Strike** (desarrollado en **Construct 2**): la **Entrega v21**, que incluye el **menú principal interactivo**, **dos patrullas de enemigos alienígenas animados con daño por contacto**, la **interfaz de energía HD integrada en el HUD**, **física de salto y avance suavemente calibrada**, escenarios extendidos y la portada imprimible para el stand escolar.

---

## 📥 1. ¿Cómo descargar el juego y los recursos? (Guía para alumnos)

1. **Quiero el juego completo con Menú, Patrullas y Energía HD listo para jugar en Construct 2 (⭐ Muy Recomendado):**
   - Haz clic en el botón verde superior **🎮 Descargar Juego Integrado v21 (`Contra_Strike_con_menu.capx`)** o entra en [`Proyecto/Contra_Strike_con_menu.capx`](Proyecto/Contra_Strike_con_menu.capx) y pulsa **Download raw file**.
   - ¡Ya tiene los enemigos patrullando, colisiones de techo reparadas, barra de energía HD y menú conectado!
2. **Quiero descargar versiones anteriores o archivos individuales:**
   - Visita la sección [**Releases (Lanzamientos)**](https://github.com/hfreedo/Contra-Strike/releases) para obtener `Contra_Strike_con_menu.capx`, `Contra_Strike_original.capx` o kits en `.zip`.
3. **Quiero descargar todo el repositorio desde GitHub:**
   - Arriba a la derecha en esta página, haz clic en el botón verde **`<> Code`** y selecciona **`Download ZIP`**. Luego descomprime la carpeta en tu computadora.

---

## Jefe final v21

Ver [patrón y controles](Proyecto/JEFE_MECHA_PATRON.md). 74 pruebas de motor pasaron, incluida la reaparición en la arena; consultar [validación](Proyecto/VALIDACION.md).

## 👾 2. Novedades de la Versión v12 (Patrullas Alienígenas, Energía HD y Movimiento Suave)

### A. Enemigos Patrulleros Integrados (Daño por Contacto)
Se incorporaron dos tipos de enemigos alienígenas que vigilan las plataformas de la base:
- **`CS_AlienBipedo`:** Patrulla la plataforma entre `X = 1090` y `X = 1275` a una velocidad de 45 px/s con animación de 4 cuadros (`conter alien walking.gif`).
- **`CS_AlienCorredor`:** Patrulla el tramo entre `X = 1830` y `X = 2000` a una velocidad de 55 px/s con animación de 12 cuadros (`alien 2 walking.gif`).
- **Mecánica de Daño:**
  - Tocar a cualquiera de los dos alienígenas consume **1 carga de energía**.
  - Se activa un **parpadeo de invulnerabilidad temporal de 1,2 segundos** para evitar daño continuo.
  - Al perder las 3 cargas de energía, se activa la pantalla de **Derrota** con opciones para Reintentar (`ENTER`) o volver al Menú (`ESC`).

### B. Barra de Energía HD integrada en el HUD
- La interfaz ahora cuenta con un diseño tecnológico HD reducido al 80% de escala (`Assets/UI_Energia/HD_v2`).
- Muestra el marco espacial, el icono del explorador y **3 segmentos de batería luminosa** que se vacían y tintinean con cada impacto o caída.
- Se eliminó el contador numérico para ofrecer una pantalla mucho más limpia e inmersiva.

### C. Física de Movimiento Calibrada
- **Velocidad máxima:** Ajustada a **240** (antes 330) para un control mucho más preciso en plataformas estrechas.
- **Aceleración y Desaceleración:** 1800 y 2200 para frenadas estables sin derrapes.
- **Salto y Gravedad:** Fuerza de salto **560** y gravedad **1150**, permitiendo un salto más suspendido (0,97 s) que hace los apoyos más cómodos y alcanzables.
- **Techos y Suelos:** 5 techos y apoyos de la caverna fueron corregidos y alineados para garantizar que el explorador nunca quede trabado.

---

## 🖼️ 3. Vista previa del Menú y de la Interfaz

| Menú Principal (`854 × 366`) | Composición Alternativa HD (`1280 × 720`) |
|:---:|:---:|
| ![Menú 854x366](Kit_Menu_v1/Vista_854x366.png) | ![Menú 1280x720](Kit_Menu_v1/Vista_1280x720.png) |

| Panel «Cómo Jugar» | Panel «Créditos» |
|:---:|:---:|
| ![Panel Cómo Jugar](Kit_Menu_v1/ayuda_854x366.png) | ![Panel Créditos](Kit_Menu_v1/creditos_854x366.png) |

---

## 🎨 4. Nuevos Assets de Combate, UI y GIFs

Dentro de [`Proyecto/Assets/`](Proyecto/Assets/) encontrarás todos los recursos utilizados en la v12:
- **`Combate/`:** Diseños conceptuales (`propuesta_combate_v1.png`), plan de combate y carpetas individuales de enemigos con sus cuadros PNG extraídos.
- **`UI_Energia/HD_v2/`:** Atlas de sprites de la barra de energía HD, batería vacía/llena/daño, botones y marcos.
- **`Enemigos_GIF/`:** Archivos GIF originales (`conter alien walking.gif` y `alien 2 walking.gif`) para estudio y animación.

---

## 🖨️ 5. Materiales Imprimibles para la Exposición (`Imprimibles_Contra_Strike/`)

| Material | Archivo PDF listo para imprimir (A4) | Contenido |
|---|---|---|
| **Portada Promocional 12×18 (v1)** | [`Portada_Contra_Strike_12x18_A4_v1.pdf`](Imprimibles_Contra_Strike/01_Portada_Imprimible/Imprimir/Portada_Contra_Strike_12x18_A4_v1.pdf) · [Digital](Imprimibles_Contra_Strike/01_Portada_Imprimible/Digital/Portada_Contra_Strike_PC_Demo_v1.png) | Portada retail con arte del juego y logo oficial, lista para recortar a 12 × 18 cm para cajas de DVD o soporte de mesa. [Leer instrucciones](Imprimibles_Contra_Strike/01_Portada_Imprimible/LEEME.md) |

---

## 📂 6. Estructura de carpetas del repositorio

```text
Contra-Strike/
├── Proyecto/
│   ├── Contra_Strike_con_menu.capx     # ⭐ PROYECTO PRINCIPAL (v12 con Menú, Patrullas y Energía HD)
│   ├── Contra_Strike_original.capx     # Versión original previa del alumno
│   ├── LEEME_v12.md                    # Explicación técnica detallada de la versión v12
│   ├── Assets/                         # Nuevos assets de Combate, Enemigos y UI de Energía HD
│   │   ├── Combate/                    # Propuesta de combate y cuadros de animación
│   │   ├── Enemigos_GIF/               # GIFs originales de patrullas alienígenas
│   │   └── UI_Energia/HD_v2/           # Barra de energía HD y texturas del HUD
│   └── Vista_fondo/                    # Verificación y capturas del escenario extendido
├── Imprimibles_Contra_Strike/          # 🖨️ Portada 12x18 cm en A4 y versión digital
└── Kit_Menu_v1/                        # Kit original de assets de menú con CSV de posiciones
```
