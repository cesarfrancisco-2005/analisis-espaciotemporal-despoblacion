# Análisis Espaciotemporal y SML de la Despoblación (Albacete / Castilla-La Mancha)

## 📌 Resumen del Proyecto
Este proyecto analiza las dinámicas de despoblación extrema en la provincia de Albacete (2012-2022) y evalúa la viabilidad de un modelo predictivo extrapolado a toda Castilla-La Mancha. Combina **estadística descriptiva, econometría espacial y algoritmos de Spatial Machine Learning (SML)**.

El estudio demuestra cómo la "España Vaciada" no es un fenómeno aleatorio, sino un proceso de contagio espacial (confirmado mediante Índice de Moran y clústeres LISA) fuertemente polarizado entre capitales dinámicas y periferias envejecidas.

📄 **[Descargar la memoria técnica completa (PDF)](proyectofinal.pdf)**

## 🛠️ Stack Tecnológico y Metodología
* **Lenguaje y Entorno:** `R`
* **Librerías principales:** `tidymodels`, `ranger` (Random Forest), `mapSpain`, `waywiser` (Cálculo del Área de Aplicabilidad).
* **Técnicas aplicadas:**
  * Análisis Geoestadístico (Matriz de contigüidad Reina, Índice de Moran Global y Local LISA).
  * Imputación matemática de infinitos en demografía extrema.
  * *Spatial Machine Learning (SML)* mediante Random Forest.
  * Validación cruzada espacial y auditoría de extrapolación (AoA).

## 🚀 Retos Técnicos Resueltos
Uno de los principales valores de este análisis fue la resolución de problemas matemáticos inherentes a la demografía extrema:
1. **Infinitos matemáticos en el Índice de Envejecimiento (IE):** Imputación de un valor mínimo de 1 en municipios con cero jóvenes empadronados para evitar valores NAs y permitir la representación cartográfica.
2. **Fugas de información (Data Leakage):** Transformación de flujos migratorios absolutos a tasas relativas (por cada 1.000 hab.) para evitar que el algoritmo Random Forest predijera basándose espuriamente en el volumen total poblacional.

## 📊 Conclusiones Principales
* **Polarización crítica:** Se identifica un clúster "Alto-Alto" de envejecimiento sistémico en la Sierra de Alcaraz.
* **Impacto exógeno:** Se evidencia un desplome abrupto en las salidas de población durante 2020 debido a las restricciones de la pandemia.
* **Límites de la Inteligencia Artificial espacial:** El cálculo del **Área de Aplicabilidad (AoA)** demuestra que el modelo es fiable en llanuras y sierras manchegas (Albacete, Cuenca, Ciudad Real), pero fracasa sistemáticamente en Toledo y Guadalajara debido a la subversión de datos generada por el área de influencia de Madrid
