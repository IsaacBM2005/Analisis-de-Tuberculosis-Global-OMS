# 🫁 Análisis de Tuberculosis Global — OMS

Análisis exploratorio de datos de tuberculosis a nivel mundial, utilizando los datasets públicos de la Organización Mundial de la Salud (OMS/WHO). El proyecto incluye limpieza de datos, transformación, cálculo de tasas de incidencia y visualizaciones.

---

## 📌 Descripción

Este notebook realiza un análisis completo sobre los casos de tuberculosis reportados a nivel global. A partir de los datos crudos de la OMS, se reconstruye una tabla analítica que permite explorar los casos por género, grupo de edad, método diagnóstico y evolución temporal.

---

## 📂 Datasets utilizados

| Archivo | Descripción |
|---|---|
| `who.csv` | Casos de tuberculosis reportados a la OMS por país y año |
| `population.csv` | Población total por país y año |

> Los archivos deben ubicarse en Google Drive en la ruta: `MyDrive/data/`

---

## 🔬 Métodos de diagnóstico analizados

| Código | Descripción |
|---|---|
| `sp` | Baciloscopia pulmonar positiva — casos más infecciosos |
| `sn` | Baciloscopia pulmonar negativa — casos difíciles de confirmar |
| `ep` | Tuberculosis extrapulmonar — afecta otros órganos |
| `rel` | Recaída — pacientes previamente tratados y dados de alta |

---

## ⚙️ Flujo del análisis

```
Carga de datos (WHO + Population)
        ↓
Limpieza de valores nulos
        ↓
Transformación con melt() → formato largo
        ↓
Extracción de variables: género, método diagnóstico, grupo de edad
        ↓
Merge con datos de población
        ↓
Cálculo de tasa de incidencia (por 100,000 hab.)
        ↓
Visualizaciones (Seaborn + Plotly)
```

---

## 📊 Variables creadas

- **`genero`** — Masculino / Femenino
- **`metodo`** — Método de diagnóstico (sp, sn, ep, rel)
- **`grupoedad`** — Grupos: 0-14, 15-24, 25-34, 35-44, 45-54, 55-64, 65+
- **`tasa_incidencia`** — Casos nuevos por cada 100,000 habitantes

---

## 📦 Librerías requeridas

```python
pandas
numpy
matplotlib
seaborn
plotly
```

> Todas disponibles por defecto en Google Colab.

---

## ▶️ Cómo ejecutar

1. Abre el notebook en [Google Colab](https://colab.research.google.com/)
2. Monta tu Google Drive cuando se solicite
3. Coloca los archivos `who.csv` y `population.csv` en `MyDrive/data/`
4. Ejecuta las celdas en orden

---

## 📈 Outputs generados

- `tuberculosis.csv` — Dataset limpio y enriquecido guardado en Drive
- `grafica_incidencia.png` — Gráfica de tasa de incidencia por año

---

## 📝 Notas

- El código `NA` del ISO2 de Namibia fue corregido manualmente, ya que Pandas lo interpreta como valor nulo.
- Los valores faltantes en columnas de casos se imputan con `0`.

---

## 📄 Licencia

Datos originales: [Organización Mundial de la Salud (OMS)](https://www.who.int/data/gho)

