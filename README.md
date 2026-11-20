# 📱 Análisis de uso de clientes — ConnectaTel

## 🎯 Objetivo del proyecto
Analizar cómo usan los clientes de ConnectaTel (empresa de telecomunicaciones en México y Colombia) los servicios de llamadas y mensajes, para identificar patrones de uso, detectar comportamientos atípicos y segmentar a los clientes, con el fin de optimizar la oferta de planes.

## 📂 Datasets utilizados
| Archivo | Descripción |
|---|---|
| `plans.csv` | Catálogo de planes (Básico y Premium): precio, minutos, mensajes y GB incluidos, y costo por excedente. |
| `users_latam.csv` | Información de 4,000 clientes: edad, ciudad, fecha de registro, plan y fecha de baja. |
| `usage.csv` | 40,000 eventos de uso: llamadas (duración) y mensajes (longitud). |

## 🔄 Etapas del análisis
1. **Carga y exploración:** estructura, tipos de datos y vista previa de los tres datasets.
2. **Calidad de datos:** detección de nulos, sentinels (-999 en edad, "?" en ciudad), fechas imposibles (año 2026) e inconsistencias.
3. **Limpieza:** reemplazo de sentinels, conversión de fechas y verificación de nulos estructurales (MAR).
4. **Estadística descriptiva:** agregación del uso por cliente y resumen de variables numéricas y categóricas.
5. **Visualización y outliers:** histogramas por plan, boxplots y método IQR.
6. **Segmentación:** clientes agrupados por nivel de uso y por edad.
7. **Insight ejecutivo:** conclusiones y recomendaciones comerciales.

## 💡 Principales hallazgos
- El 74 % de los clientes tiene un uso medio y solo el 7 % un uso alto; el consumo real está muy por debajo de lo que incluyen los planes.
- Los clientes Premium usan lo mismo que los Básico, aunque pagan más del doble.
- Existe un grupo aislado de clientes con 130–155 minutos de llamada que conviene revisar (posible uso empresarial o fraude).
- El 11.7 % de los clientes ya se dio de baja.

## 🛠️ Herramientas
Python, Jupyter Notebook, pandas, numpy, matplotlib y seaborn.

## ▶️ Cómo ejecutar el notebook
1. Descarga o clona este repositorio.
2. Abre el archivo `.ipynb` en Jupyter Notebook o en Google Colab (**File → Upload notebook**).
3. Instala las librerías si es necesario:
   `pip install pandas numpy matplotlib seaborn`
4. Coloca los archivos `plans.csv`, `users_latam.csv` y `usage.csv` en una carpeta y actualiza las rutas de `pd.read_csv()` en la primera sección del notebook (originalmente apuntan a `/datasets/`).
5. Ejecuta todas las celdas en orden (**Kernel → Restart & Run All** en Jupyter, o **Runtime → Run all** en Colab).
