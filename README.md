# Ciencia_de_datos_aplicada_taller-2
Clase: Ciencia de datos aplicada - taller N2 

Integrantes:
- Nicolas Gonzalez Ochoa

- Ana Catalina Gelvez Alvarez

➡️Presentación:


HabitAlpes – Modelo de Estimación del Precio de Venta de Apartamentos en Bogotá
Proyecto de Analítica de Datos — Modelos Predictivos y Análisis Económico

Este proyecto desarrolla un modelo de Machine Learning capaz de estimar el precio de venta de apartamentos ubicados en Bogotá, con el fin de optimizar el proceso de avalúo inmobiliario y reducir costos operativos para la empresa HabitAlpes.

El Notebook principal del proyecto es:
📄 TallerN2_AnaliticaDatos.ipynb

📌 1. Objetivo del proyecto

Construir una herramienta de analítica que permita:

Estimar el precio de venta de apartamentos en Bogotá.

Reducir el tiempo de peritaje experto (de 6 horas a 1 hora).

Minimizar costos administrativos.

Identificar errores graves de subestimación (>20 millones COP).

Evaluar el impacto económico del modelo (ROI, break-even, sensibilidad).

📁 2. Contenido del repositorio
├── data/
│   └── apartamentos.csv               # Dataset original
├── TallerN2_AnaliticaDatos.ipynb      # Notebook completo del proyecto
└── README.md

📊 3. Metodología del proyecto
1. Limpieza y preparación del dataset

Manejo de NaN

Normalización y escalado

Eliminación de outliers vía clipping estadístico

One-hot encoding para variables categóricas

2. Modelos entrenados

Se implementaron y evaluaron 3 modelos:

Modelo	R²	MAE	RMSE
Regresión Lineal	~0.61	~0.38	~0.62
Lasso (L1)	~0.61	~0.38	~0.62
Ridge (L2)	~0.61	~0.38	~0.62

📌 Todos los modelos tuvieron desempeño similar debido a multicolinealidad y alta dispersión del precio.

3. Análisis de multicolinealidad

Se calculó VIF para todas las variables → algunas mostraron VIF elevado.

Se ajustaron modelos regularizados (Lasso/Ridge).

4. Interpretabilidad

Interpretación global con SHAP Summary Plot

Interpretación local con SHAP Force Plot

Explicaciones por observación con LIME

5. Evaluación del error crítico

Se analizaron:

Subestimaciones graves (modelo predice >20M por debajo del precio real).

Sobreestimaciones graves (predicción >20M por encima del valor real).

💰 4. Evaluación económica del modelo

Se analizaron:

Costo actual de operación

6 horas × $9.500 COP/hora × 500 peritajes/mes

→ $28.500.000 COP/mes

Costo con modelo

Solo 1 hora de perito cuando el modelo subestima gravemente

Costo infraestructura por predicción ($10.000)

Mantenimiento mensual

ROI y Break-even

✔ Resultados económicos (ejemplo con precisión = 0.65)
Métrica	Valor
Ahorro mensual	~$17.000.000
Ahorro anual	~$204.000.000
Break-even	~0.7 meses
ROI anual	~1600 %

Se incluye además un análisis de sensibilidad según:

volumen de predicciones (100 → 1000)

precisión del modelo (0.5 → 0.8)

🖼️ 5. Visualizaciones incluidas

Boxplot real vs predicho

Distribución de errores absolutos

Residuos vs valores predichos

Comparación de métricas entre modelos

VIF para multicolinealidad

SHAP: feature importance

LIME: explicación por observación

Gráficos de costo, ahorro y ROI

🚀 6. Tecnologías utilizadas

Python 3.11+

Pandas, NumPy

Scikit-Learn

Matplotlib, Seaborn

Statsmodels

SHAP

Lime

Jupyter / VS Code

📈 7. Conclusiones del proyecto

Los modelos obtienen un R² ≈ 0.61, razonable pero con margen de mejora.

El modelo es estable pero su error absoluto puede llegar a ser alto.

El uso del modelo genera ahorros significativos (más del 50% de los costos).

El ROI del proyecto es muy alto y el retorno ocurre en menos de 1 mes.

La interpretabilidad con SHAP permite identificar:

estrato

administración

sector

metros²
como los factores más relevantes.
