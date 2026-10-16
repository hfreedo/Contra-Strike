# 🪐 Contra Strike — Un Mundo por Descubrir

<p align="center">
  <img src="Portadas/Contra_Strike_PC_Demo.png" alt="Portada Contra Strike - Un Mundo por Descubrir" width="760">
</p>

<p align="center">
  <a href="https://github.com/hfreedo/Contra-Strike/releases/latest/download/Contra_Strike_original.capx">
    <img src="https://img.shields.io/badge/🎮_Descargar_Proyecto_Construct_2-Contra__Strike.capx-7c3aed?style=for-the-badge" alt="Descargar CAPX">
  </a>
  <a href="https://github.com/hfreedo/Contra-Strike/releases/latest/download/Contra_Strike_Kit_Completo_v1.zip">
    <img src="https://img.shields.io/badge/📦_Descargar_Kit_de_Menú_+_Juego-Contra__Strike__v1.zip-2563eb?style=for-the-badge" alt="Descargar Kit Completo ZIP">
  </a>
</p>

---

## 👋 ¡Bienvenidos al repositorio oficial de Contra Strike!

Este repositorio contiene el proyecto base de **Contra Strike** desarrollado en **Construct 2**, junto con el **Kit de Menú v1** (imágenes separadas con transparencia, coordenadas exactas de posición para Construct 2, vista interactiva HTML y portada oficial) listo para que el equipo lo integre y personalice en clase.

---

## 📥 1. ¿Cómo descargar el juego y los recursos? (Guía para alumnos)

Tienes **tres formas** de obtener los archivos:

1. **Solo quiero el archivo `.capx` para abrirlo en Construct 2:**
   - Haz clic en el botón violeta superior **🎮 Descargar Proyecto Construct 2 (`Contra_Strike.capx`)** o entra en [`Proyecto/Contra_Strike_original.capx`](Proyecto/Contra_Strike_original.capx) y pulsa **Download raw file**.
2. **Quiero el paquete completo `.zip` (Juego + Kit de Menú + Portada):**
   - Haz clic en el botón azul **📦 Descargar Kit de Menú + Juego (`Contra_Strike_v1.zip`)** o visita la sección [**Releases (Lanzamientos)**](https://github.com/hfreedo/Contra-Strike/releases).
3. **Quiero descargar todo el repositorio desde GitHub:**
   - Arriba a la derecha en esta página, haz clic en el botón verde **`<> Code`** y selecciona **`Download ZIP`**. Luego descomprime el archivo en tu computadora.

> [!IMPORTANT]
> **Consejo antes de editar en Construct 2:** Abre `Proyecto/Contra_Strike_original.capx` y guárdalo con un nombre nuevo (por ejemplo, `Contra_Strike_con_menu_v1.capx`) antes de agregar el menú, para mantener siempre un respaldo limpio.

---

## 🖼️ 2. Vista previa del Menú Principal (`Kit_Menu_v1/`)

| Ventana Original del Proyecto (`854 × 366`) | Composición Alternativa HD (`1280 × 720`) |
|:---:|:---:|
| ![Menú 854x366](Kit_Menu_v1/Vista_854x366.png) | ![Menú 1280x720](Kit_Menu_v1/Vista_1280x720.png) |

| Panel «Cómo Jugar» | Panel «Créditos» |
|:---:|:---:|
| ![Panel Cómo Jugar](Kit_Menu_v1/ayuda_854x366.png) | ![Panel Créditos](Kit_Menu_v1/creditos_854x366.png) |

💡 *Puedes probar los botones y paneles interactivos abriendo [`Kit_Menu_v1/Vista_previa.html`](Kit_Menu_v1/Vista_previa.html) en cualquier navegador web.*

---

## 🛠️ 3. Guía Paso a Paso: Cómo integrar el Menú en Construct 2

Sigue estos pasos en **Construct 2** para armar el menú principal exactamente igual a la vista previa:

### Paso 1: Crear el Layout y las Capas
1. Abre tu copia del proyecto en Construct 2. **Conserva la resolución original de ventana `854 × 366`** (no la cambies a `1280 × 720` para no alterar la cámara del nivel jugable).
2. Crea un nuevo Layout llamado **`Menu`** (con tamaño `854 × 366`) y su hoja de eventos **`Menu_Events`**. Configura `Menu` como el *First layout* del proyecto.
3. Dentro del layout `Menu`, crea **4 capas** en este orden (de abajo hacia arriba):
   - `Fondo`
   - `Personaje`
   - `Interfaz`
   - `Paneles` *(configúrala inicialmente como **Invisible**)*

### Paso 2: Importar los Sprites (`Kit_Menu_v1/Assets/`)
Importa cada archivo PNG como objeto **Sprite** (con el punto de origen en el **Centro** y sin comportamientos físicos `Solid` ni `Platform`):

| Objeto Sprite sugerido | Archivo PNG en `Kit_Menu_v1/Assets/` | Capa | Posición `X, Y` (`854×366`) | Tamaño `Ancho × Alto` (`854×366`) |
|---|---|---|:---:|:---:|
| `FondoMenu` | [`Fondos/fondo_menu_alien.png`](Kit_Menu_v1/Assets/Fondos/fondo_menu_alien.png) | `Fondo` | `427, 183` | `854 × 480.63` |
| `ExploradorMenu` | [`Personaje/explorador_sin_armas.png`](Kit_Menu_v1/Assets/Personaje/explorador_sin_armas.png) | `Personaje` | `209.23, 183.59` | `190.32 × 285.48` |
| `TituloMenu` | [`Titulo/contra_strike.png`](Kit_Menu_v1/Assets/Titulo/contra_strike.png) | `Interfaz` | `614.88, 73.2` | `186.66 × 124.44` |
| `BtnJugar` | [`Interfaz/boton_alien_vacio.png`](Kit_Menu_v1/Assets/Interfaz/boton_alien_vacio.png) | `Interfaz` | `614.88, 175.68` | `164.7 × 54.9` |
| `BtnComoJugar` | [`Interfaz/boton_alien_vacio.png`](Kit_Menu_v1/Assets/Interfaz/boton_alien_vacio.png) | `Interfaz` | `614.88, 243.39` | `164.7 × 54.9` |
| `BtnCreditos` | [`Interfaz/boton_alien_vacio.png`](Kit_Menu_v1/Assets/Interfaz/boton_alien_vacio.png) | `Interfaz` | `614.88, 311.1` | `164.7 × 54.9` |
| `LogoColegio` | [`Colegio/logo_colegio_transparente.png`](Kit_Menu_v1/Assets/Colegio/logo_colegio_transparente.png) | `Interfaz` | `819.23, 322.08` | `54.9 × 54.9` |
| `PanelModal` | [`Interfaz/panel_alien_vacio.png`](Kit_Menu_v1/Assets/Interfaz/panel_alien_vacio.png) | `Paneles` | `427, 183` | `483.12 × 322.08` |

*(Si en el futuro deciden trabajar en `1280 × 720`, todas las coordenadas equivalentes están en [`Kit_Menu_v1/posiciones_construct.csv`](Kit_Menu_v1/posiciones_construct.csv)).*

### Paso 3: Agregar los Textos y Programar los Eventos
1. Coloca un objeto **Text** centrado sobre cada botón (`JUGAR DEMO`, `CÓMO JUGAR`, `CRÉDITOS`) con fuente **Segoe UI Bold** (tamaño ~12 pt en `854×366`) en color crema claro (`#FFF0D2`).
2. En `Menu_Events`, crea una variable global o local `PanelMenu = 0` y programa:
   - **Al hacer clic en `BtnJugar` (si `PanelMenu = 0`):** Ir al layout de juego (`System → Go to layout → Layout 1`).
   - **Al hacer clic en `BtnComoJugar` (si `PanelMenu = 0`):** Cambiar `PanelMenu = 1`, hacer visible la capa `Paneles` y mostrar los controles:
     - **Flechas Izquierda / Derecha (`←` / `→`):** Moverse por la base alienígena.
     - **Flecha Arriba (`↑`):** Saltar entre plataformas.
   - **Al hacer clic en `BtnCreditos` (si `PanelMenu = 0`):** Cambiar `PanelMenu = 2`, hacer visible la capa `Paneles` y mostrar el nombre del colegio y los integrantes del grupo.
   - **Al hacer clic en `VOLVER` o presionar `ESC` (si `PanelMenu > 0`):** Ocultar la capa `Paneles` y volver `PanelMenu = 0`.

📄 *Consulta la guía completa con todos los detalles técnicos en [`Kit_Menu_v1/GUIA_CONSTRUCT_2.md`](Kit_Menu_v1/GUIA_CONSTRUCT_2.md).*

---

## 📂 4. Estructura de carpetas del repositorio

```text
Contra-Strike/
├── Proyecto/
│   └── Contra_Strike_original.capx     # ⭐ Proyecto original de Construct 2 para abrir y editar
├── Kit_Menu_v1/                        # Kit completo de Menú de Exploración v1
│   ├── Assets/                         # PNGs separados (Fondo, Explorador, Título, Botón, Panel, Escudo)
│   ├── GUIA_CONSTRUCT_2.md             # Instrucciones paso a paso para importar el menú
│   ├── posiciones_construct.csv        # Tabla de coordenadas exactas (854x366 y 1280x720)
│   ├── Vista_previa.html               # Simulador interactivo del menú en el navegador
│   └── Vista_854x366.png               # Capturas de referencia de cada pantalla
└── Portadas/
    └── Contra_Strike_PC_Demo.png       # Portada promocional oficial en alta resolución
```
