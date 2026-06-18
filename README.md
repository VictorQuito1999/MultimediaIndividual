<h1 align="center">🎓 Portafolio Trabajos Individuales de Multimedia</h1>

<p align="center">
  <strong>Víctor Manuel Quito Chávez</strong><br/>
  <em>Procesamiento Digital de Imágenes · Visión Artificial · Multimedia</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/OpenCV-Visión_Artificial-green?style=for-the-badge&logo=opencv&logoColor=white"/>
  <img src="https://img.shields.io/badge/NumPy-Matricial-orange?style=for-the-badge&logo=numpy&logoColor=white"/>
  <img src="https://img.shields.io/badge/Tkinter-GUI-9b59b6?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/scikit--learn-ML-f39c12?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
</p>

<p align="center">
  Repositorio de proyectos individuales desarrollados para la materia de <strong>Multimedia</strong>.<br/>
  Cada ejercicio aborda un área diferente del procesamiento digital de imágenes y la visión por computadora,<br/>
  implementados desde cero con un enfoque explícito sobre la matemática subyacente.
</p>

---

## 📂 Estructura del Repositorio

```
MultimediaIndividual/
│
├── 📁 a-clasficacionTexturas/     # Ejercicio A — Segmentación de superficies por color (HSV)
│   ├── clasificacionTexturas.py
│   └── index.html
│
├── 📁 b-filtrosuavizado/          # Ejercicio B — Filtro Gaussiano + Detección de Bordes Sobel
│   ├── filtrosuavizado.py
│   └── README.md
│
├── 📁 c-Vacalola/                    # Ejercicio extra — Segmentación avanzada GLCM + LBP + KMeans
│   ├── enlacevacalola.txt
│   
│
├── 📁 assets/                     # Recursos compartidos (CSS, JS)
├── index.html                     # Portafolio web interactivo
└── informe_tecnico_final.pdf      # Informe técnico completo
```

---

## 🧩 Ejercicios

### a) 🌿 Clasificación de Texturas por Color
**Carpeta:** `a-clasficacionTexturas/`

Aplicación de escritorio que segmenta superficies en una imagen usando **umbrales en el espacio de color HSV**. El sistema distingue automáticamente entre tres tipos de suelo:

| Superficie | Espacio HSV | Color en el mapa |
|---|---|---|
| 🟢 **Césped** | H: 35–85, S: 40–255 | Verde brillante |
| 🟤 **Tierra** | H: 10–25, S: 40–255 | Naranja/Marrón |
| ⚫ **Asfalto/Cemento** | S: 0–50 (baja saturación) | Azul eléctrico |

**Modos de análisis:**
- 🔍 **Filtrar Selección** — Aisla una única superficie con máscara binaria AND
- 📊 **Clasificación Total** — Genera un mapa semántico completo por superposición al 50%

**Stack:** `Python` · `Tkinter` · `OpenCV` · `NumPy` · `Pillow`

---

### b) 🌀 Filtro de Suavizado y Detección de Bordes (Matricial)
**Carpeta:** `b-filtrosuavizado/`

Implementación **desde cero** de un pipeline de procesamiento de imagen basado en convolución matricial explícita. No delega operaciones a funciones abstractas de OpenCV, cada kernel se define y aplica manualmente.

**Kernels implementados:**

```
         1  [ 1  2  1 ]                 [ -1  0  1 ]        [ -1  -2  -1 ]
K_Gauss =── [ 2  4  2 ]    Gx (Sobel) = [ -2  0  2 ]  Gy = [  0   0   0 ]
        16  [ 1  2  1 ]                 [ -1  0  1 ]        [  1   2   1 ]
```

**Pipeline:**
1. **Gaussiano 3×3** → suavizado ponderado con normalización (`÷16`)
2. **Sobel 3×3** → gradientes Gx y Gy → `Magnitud = √(Gx² + Gy²)`
3. Conversión a escala de grises con fórmula de luminancia ITU-R: `Y = 0.299R + 0.587G + 0.114B`

**Stack:** `Python` · `Tkinter` · `OpenCV` · `NumPy` · `Pillow`

---

### ⚡ Detección de Texturas Avanzada (GLCM + LBP + KMeans)
**Carpeta:** `pratica/`

Versión extendida de análisis de texturas usando **descriptores estadísticos** y **aprendizaje no supervisado**. A diferencia del ejercicio A (basado en color), este sistema analiza la **estructura espacial** de la imagen.

**Algoritmo:**
1. **GLCM** (Gray-Level Co-occurrence Matrix) — extrae 5 descriptores: contraste, homogeneidad, energía, correlación y disimilaridad
2. **LBP** (Local Binary Patterns) — histograma de 18 bins con radio 2
3. **KMeans Clustering** — agrupa bloques de textura en `K` clases configurables

**Características destacadas:**
- ✅ Procesamiento en hilo separado con barra de progreso en tiempo real
- ✅ Tabla de estadísticas por textura (área %, media gris, desviación estándar)
- ✅ Visualización en 3 modos: Superposición, Segmentación pura, Original
- ✅ Exportación del resultado a PNG/JPEG

**Stack:** `Python` · `Tkinter` · `OpenCV` · `NumPy` · `scikit-learn` · `scikit-image` · `Pillow`

## 🚀 Instalación Rápida

### Ejercicios A y B (dependencias básicas)

```bash
pip install opencv-python numpy Pillow
```

### Ejercicio Extra (dependencias avanzadas)

```bash
cd pratica
pip install -r requirements.txt
```

### Ejecutar cada ejercicio

```bash
# Ejercicio A
python a-clasficacionTexturas/clasificacionTexturas.py

# Ejercicio B
python b-filtrosuavizado/filtrosuavizado.py

# Ejercicio Extra
python pratica/texture_app.py
```

---

## 📄 Documentación

El informe técnico completo se encuentra en `informe_tecnico_final.pdf`, disponible también desde el portafolio web en la sección 📄 Documentación.

---

<p align="center">
  © 2026 · <strong>Víctor Manuel Quito Chávez</strong> · Portafolio Individual de Multimedia
</p>
