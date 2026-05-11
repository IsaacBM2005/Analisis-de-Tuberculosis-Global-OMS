🫁 Análisis de Tuberculosis Global — OMS
Análisis exploratorio de datos de tuberculosis a nivel mundial, utilizando los datasets públicos de la Organización Mundial de la Salud (OMS/WHO). El proyecto incluye limpieza de datos, transformación, cálculo de tasas de incidencia y visualizaciones.

📌 Descripción
Este notebook realiza un análisis completo sobre los casos de tuberculosis reportados a nivel global. A partir de los datos crudos de la OMS, se reconstruye una tabla analítica que permite explorar los casos por género, grupo de edad, método diagnóstico y evolución temporal.

📂 Datasets utilizados
ArchivoDescripciónwho.csvCasos de tuberculosis reportados a la OMS por país y añopopulation.csvPoblación total por país y año

Los archivos deben ubicarse en Google Drive en la ruta: MyDrive/data/


🔬 Métodos de diagnóstico analizados
CódigoDescripciónspBaciloscopia pulmonar positiva — casos más infecciosossnBaciloscopia pulmonar negativa — casos difíciles de confirmarepTuberculosis extrapulmonar — afecta otros órganosrelRecaída — pacientes previamente tratados y dados de alta

⚙️ Flujo del análisis
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

📊 Variables creadas

genero — Masculino / Femenino
metodo — Método de diagnóstico (sp, sn, ep, rel)
grupoedad — Grupos: 0-14, 15-24, 25-34, 35-44, 45-54, 55-64, 65+
tasa_incidencia — Casos nuevos por cada 100,000 habitantes


📦 Librerías requeridas
pythonpandas
numpy
matplotlib
seaborn
plotly

Todas disponibles por defecto en Google Colab.


▶️ Cómo ejecutar

Abre el notebook en Google Colab
Monta tu Google Drive cuando se solicite
Coloca los archivos who.csv y population.csv en MyDrive/data/
Ejecuta las celdas en orden


📈 Outputs generados

tuberculosis.csv — Dataset limpio y enriquecido guardado en Drive
grafica_incidencia.png — Gráfica de tasa de incidencia por año


📝 Notas

El código NA del ISO2 de Namibia fue corregido manualmente, ya que Pandas lo interpreta como valor nulo.
Los valores faltantes en columnas de casos se imputan con 0.


📄 Licencia
Datos originales: Organización Mundial de la Salud (OMS)
