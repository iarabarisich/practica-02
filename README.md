# Práctica 02 — Sistema Astronómico de Magnitudes y Colores

**Astronomía Estelar 2026 — UNLP**

Autores: J.P. Calderón & Roberto Gamen

## 🎯 Objetivos

En esta práctica vas a:

- **Entender** el sistema de magnitudes astronómicas y sus escalas logarítmicas.
- **Aprender** sobre índices de color (B-V, U-B, V-I) y su significado físico.
- **Procesar** datos de sensibilidad de filtros fotométricos (UBVRI).
- **Analizar** la distribución espectral de energía de estrellas.
- **Investigar** la relación entre color y tipo espectral en la secuencia principal.

## 🚀 Cómo comenzar

### Opción 1: GitHub Classroom (recomendado)
1. Accedé al link de Classroom desde el campus virtual.
2. Se creará automáticamente tu repositorio individual.
3. Abre el repo en **Codespaces** (botón verde `<> Code` → Codespaces).

### Opción 2: Local
1. Clona este repositorio.
2. Instala dependencias:
   ```bash
   conda activate ae
   pip install -r requirements.txt
   ```
3. Selecciona el kernel `Python (Practica 02)` en Jupyter.

## 📓 Estructura del Notebook

El notebook contiene las siguientes secciones:

| Sección | Tema | Habilidades |
|---------|------|-----------|
| **A** | Sistema de magnitudes astronómicas | Escala logarítmica, cálculos de mag |
| **B** | Índices de color | B-V, U-B, correlaciones espectrales |
| **C** | Función de sensibilidad de filtros | Lectura de datos, convolución |
| **D** | Distribución espectral de energía | Integración, flujo, temperatura |
| **E** | Relación color-tipo espectral | Análisis de secuencia principal |

### Notebooks Complementarios

- **Introduccion_colores.ipynb**: Tutorial introductorio sobre percepción de colores y sistema UBVRI

## 📦 Estructura del Repositorio

```
practica-02/
├── .devcontainer/
│   └── devcontainer.json          # Configuración Codespaces
├── notebooks/
│   ├── practica_02.ipynb          # Notebook principal
│   └── Introduccion_colores.ipynb # Notebook complementario
├── data/
│   ├── UBVRI.dat                  # Función sensibilidad filtros
│   ├── V.dat                      # Índices de color tipo espectral
│   └── distribucion_espectral_K5V.dat  # SED de estrella K5V
├── src/                           # Scripts auxiliares (opcional)
├── informe/                       # Donde guardar gráficos y resultados
├── requirements.txt               # Dependencias Python
├── README.md                      # Este archivo
└── .gitignore                     # Archivos a ignorar

```

## 🔧 Instalación

### En Codespaces
El entorno se instala **automáticamente**:
1. Se ejecuta `pip install -r requirements.txt`
2. Se instala el kernel `Python (Practica 02)`
3. Ya podés abrir el notebook

### Localmente

```bash
# Activar ambiente conda
conda activate ae

# Instalar dependencias
pip install -r requirements.txt

# (Opcional) Instalar kernel custom
python -m ipykernel install --user --name practica-02 --display-name 'Python (Practica 02)'

# Abrir Jupyter
jupyter notebook
```

## 📋 Flujo de Trabajo

### 1. Comenzar por el Notebook Complementario
- Abre primero **Introduccion_colores.ipynb** para entender conceptos
- Lee con atención la explicación del sistema UBVRI

### 2. Ejecutar el Notebook Principal
- Abre `notebooks/practica_02.ipynb`
- Selecciona el kernel **"Python (Practica 02)"**
- Ejecuta celda por celda (no todo de una)

### 3. Completar los Ejercicios
- Cada sección tiene celdas con `# TODO:` o indicaciones
- **No cambies la estructura**, solo completa lo que se pide
- Valida que los gráficos tengan etiquetas, títulos y leyendas

### 4. Documentar tu Trabajo
- Agrega comentarios explicando tu razonamiento físico
- Si usas IA: **documenta qué pediste y por qué**

### 5. Entregar
- Realiza commits regularmente:
  ```bash
  git add notebooks/practica_02.ipynb
  git commit -m "Completa sección B: Índices de color"
  git push origin main
  ```

## ⚠️ Solución de Problemas

### Error: `No module named 'numpy'` (o similar)
- En Codespaces: relanza el contenedor (Ctrl+Shift+P → "Rebuild Container")
- Localmente: `pip install numpy`

### Error: `*.dat no encontrados`
- Verifica que estés en la carpeta `practica-02`
- Los archivos deben estar en `data/UBVRI.dat`, etc.
- Usa rutas relativas: `'data/UBVRI.dat'`

### Error: `Kernel "Python (Practica 02)" no aparece`
- En Codespaces: relanza el contenedor
- Localmente: `python -m ipykernel install --user --name practica-02`

### Los gráficos se ven distorsionados
- Verifica que uses `plt.tight_layout()` antes de `plt.show()`
- Intenta cambiar el tamaño de figura: `figsize=(10, 6)`

## 🤖 Uso de Agentes IA y Asistentes

Podés usar IA para:
- **✅ Entender conceptos**: magnitudes, colores, distribución espectral
- **✅ Debuggear código**: "¿Por qué este gráfico no aparece?"
- **✅ Explorar numpy/pandas**: "¿Cómo sumo dos arrays de distinto tamaño?"

**PERO NO HAGAS**:
- **❌ Copiar soluciones completas** de otros años o de internet
- **❌ Pedir código sin entender qué hace**
- **❌ Ignorar mensajes de error sin investigar**

**Regla de Oro**: Podés usar IA, pero **vos tenés que entender cada línea** del código que entreguês.

Si usaste IA, documentalo:
```python
# Consulté a [IA/Stackoverflow/etc] para entender cómo 
# interpolar datos entre dos arrays
from scipy.interpolate import interp1d
```

## 📚 Material Útil

- [Documentación numpy](https://numpy.org/doc/stable/)
- [Matplotlib: Guía de plotting](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html)
- [Sistema de magnitudes astronómicas](https://en.wikipedia.org/wiki/Magnitude_(astronomy))
- [Diagrama de Hertzsprung-Russell](https://es.wikipedia.org/wiki/Diagrama_de_Hertzsprung-Russell)
- [Filtros UBVRI (ESO)](https://www.eso.org/sci/facilities/paranal/instruments/general/filters.html)

## ✅ Checklist de Entrega

Antes de hacer push final:

- [ ] Ambos notebooks ejecutan sin errores
- [ ] Los gráficos tienen etiquetas en ejes (xlabel, ylabel)
- [ ] Los gráficos tienen título (title)
- [ ] Los archivos `.dat` se cargan correctamente desde `data/`
- [ ] Los índices de color calculados tienen sentido físico
- [ ] Incluiste comentarios explicando tu razonamiento
- [ ] Si usaste IA, está documentado con contexto
- [ ] Realizaste commits con mensajes descriptivos
- [ ] No hay archivos enormes commiteados (solo `.ipynb` y `.py`)

## 📬 Preguntas / Reporta Bugs

Si encontrás errores en el notebook o las instrucciones:
1. Abrí un **Issue** en GitHub
2. Enviá un email a: `[instructor@email.com]`

---

**¡Éxito con la práctica!** 🚀
