# Modelado Predictivo Avanzado con Datos Abiertos de Colombia

**Por:** Robinson Alexander Otálvaro  
**Curso:** Análisis de datos avanzado grupo 2  
**Código:** [Enlace a Colab](#)

---

## 1. Introducción
El análisis tiene como objetivo desarrollar un modelo predictivo para estimar el número de accidentes de tránsito en función de características clave relacionadas con los accidentes. Este análisis es crítico para comprender los factores que contribuyen a los accidentes y proporcionar información para la toma de decisiones orientadas a la prevención.

---

## 2. Justificación de las Variables Seleccionadas

1. **territorial (Localización geográfica):** Representa la ubicación administrativa donde ocurrieron los accidentes. Es relevante porque los factores locales, como la infraestructura vial, las regulaciones y el clima, pueden influir en la ocurrencia de accidentes.
2. **clase_accidente (Tipo de accidente):** Clasifica el tipo de accidente (e.g., colisión, atropello, vuelco). Proporciona información sobre las causas y circunstancias específicas de los accidentes.
3. **n_heridos (Número de heridos):** Indica el impacto del accidente en términos de personas lesionadas. Es un proxy del grado de severidad de los accidentes y tiene una correlación directa con el número de eventos.
4. **n_muertos (Número de muertos):** Indica el impacto más severo de un accidente. Su inclusión es crucial para reflejar la gravedad de los eventos y su relación con otros factores.
5. **n_accidentes (Variable objetivo):** Representa el total de accidentes, definido como la suma de heridos y muertos. Es la variable que se busca predecir, ya que proporciona una métrica consolidada del impacto de los accidentes en una región y situación específica.

---

## 3. Proceso Realizado

### 3.1 Carga del Archivo
- **Descripción:** Se utilizó un archivo CSV disponible en una URL pública. Este archivo contenía datos relacionados con los accidentes de tránsito registrados.
- **Pasos:**
  - Se cargó el archivo en un DataFrame de pandas.
  - Se seleccionaron únicamente las columnas relevantes (`territorial`, `clase_accidente`, `n_heridos`, `n_muertos`).
  - Se creó la columna objetivo `n_accidentes` como la suma de `n_heridos` y `n_muertos`.

### 3.2 Limpieza de Datos
- **Manejo de valores nulos:** Se identificaron y eliminaron las filas con valores faltantes en las columnas seleccionadas para evitar errores en el modelado.
- **Conversión de tipos de datos:** Las variables categóricas (`territorial` y `clase_accidente`) se convirtieron en valores numéricos mediante Label Encoding.
- **Eliminación de outliers:** Se aplicó el método del rango intercuartílico (IQR) para detectar y eliminar valores atípicos en las columnas numéricas.

### 3.3 Escalamiento de los Datos
- **Descripción:** Se aplicó escalamiento estándar (StandardScaler) para normalizar las variables numéricas.
- **Pasos:** Se ajustó el escalador a los datos de entrenamiento y se aplicó tanto a los datos de entrenamiento como a los datos de prueba.

---

## 4. Modelado Predictivo

### 4.1 Modelos Implementados
- **Árboles de Decisión**
- **Random Forest**

### 4.2 División de los Datos
- **Descripción:** Los datos se dividieron en:
  - Conjunto de entrenamiento (80%)
  - Conjunto de prueba (20%)
- **Pasos:**
  1. Separación de la variable objetivo (`n_accidentes`) y las variables predictoras (`territorial`, `clase_accidente`, `n_heridos`, `n_muertos`).
  2. Escalamiento aplicado al conjunto de entrenamiento y transformado al conjunto de prueba.

---

## 5. Resultados

### Árbol de Decisión
- **Puntos fuertes:** Alto desempeño en todas las métricas:  
  - Exactitud: 98.5%  
  - Precisión: 98.51%  
  - Recall: 98.5%  
  - F1-Score: 98.45%  
  Modelo interpretable y computacionalmente eficiente.
- **Limitaciones:** Más propenso al sobreajuste.

### Random Forest
- **Puntos fuertes:** Menos propenso al sobreajuste que el Árbol de Decisión.  
  - Exactitud: 97.0%  
  - Precisión: 96.11%  
  - Recall: 97.0%  
  - F1-Score: 96.45%  
  Modelo robusto con capacidad para manejar datos complejos.
- **Limitaciones:** Menos interpretable y con mayor costo computacional.

---

## 6. Comparación de Modelos

| Modelo           | Exactitud | Precisión | Recall | F1-Score |
|-------------------|-----------|-----------|--------|----------|
| Árbol de Decisión | 0.985     | 0.985139  | 0.985  | 0.984535 |
| Random Forest     | 0.970     | 0.961099  | 0.970  | 0.964587 |

---

## 7. Conclusiones

- El Árbol de Decisión es altamente interpretable y útil para comprender las relaciones entre variables, pero su tendencia al sobreajuste limita su capacidad de generalización.
- Random Forest es más robusto y confiable para predicciones generalizables, aunque menos interpretable.
- **Recomendación:** Utilizar un enfoque híbrido: 
  - Random Forest para predicciones confiables.
  - Árbol de Decisión como herramienta explicativa.

---

## 8. Recomendaciones para Mejorar la Precisión
- Optimizar hiperparámetros como `n_estimators` y `max_depth` usando técnicas como GridSearchCV.
- Incluir características adicionales (e.g., condiciones climáticas, épocas festivas).
- Explorar modelos ensemble más avanzados como Gradient Boosting o XGBoost# Modelado Predictivo Avanzado con Datos Abiertos de Colombia

**Por:** Robinson Alexander Otálvaro  
**Curso:** Análisis de datos avanzado grupo 2  
**Código:** [Enlace a Colab](#)

---

## 1. Introducción
El análisis tiene como objetivo desarrollar un modelo predictivo para estimar el número de accidentes de tránsito en función de características clave relacionadas con los accidentes. Este análisis es crítico para comprender los factores que contribuyen a los accidentes y proporcionar información para la toma de decisiones orientadas a la prevención.

---

## 2. Justificación de las Variables Seleccionadas

1. **territorial (Localización geográfica):** Representa la ubicación administrativa donde ocurrieron los accidentes. Es relevante porque los factores locales, como la infraestructura vial, las regulaciones y el clima, pueden influir en la ocurrencia de accidentes.
2. **clase_accidente (Tipo de accidente):** Clasifica el tipo de accidente (e.g., colisión, atropello, vuelco). Proporciona información sobre las causas y circunstancias específicas de los accidentes.
3. **n_heridos (Número de heridos):** Indica el impacto del accidente en términos de personas lesionadas. Es un proxy del grado de severidad de los accidentes y tiene una correlación directa con el número de eventos.
4. **n_muertos (Número de muertos):** Indica el impacto más severo de un accidente. Su inclusión es crucial para reflejar la gravedad de los eventos y su relación con otros factores.
5. **n_accidentes (Variable objetivo):** Representa el total de accidentes, definido como la suma de heridos y muertos. Es la variable que se busca predecir, ya que proporciona una métrica consolidada del impacto de los accidentes en una región y situación específica.

---

## 3. Proceso Realizado

### 3.1 Carga del Archivo
- **Descripción:** Se utilizó un archivo CSV disponible en una URL pública. Este archivo contenía datos relacionados con los accidentes de tránsito registrados.
- **Pasos:**
  - Se cargó el archivo en un DataFrame de pandas.
  - Se seleccionaron únicamente las columnas relevantes (`territorial`, `clase_accidente`, `n_heridos`, `n_muertos`).
  - Se creó la columna objetivo `n_accidentes` como la suma de `n_heridos` y `n_muertos`.

### 3.2 Limpieza de Datos
- **Manejo de valores nulos:** Se identificaron y eliminaron las filas con valores faltantes en las columnas seleccionadas para evitar errores en el modelado.
- **Conversión de tipos de datos:** Las variables categóricas (`territorial` y `clase_accidente`) se convirtieron en valores numéricos mediante Label Encoding.
- **Eliminación de outliers:** Se aplicó el método del rango intercuartílico (IQR) para detectar y eliminar valores atípicos en las columnas numéricas.

### 3.3 Escalamiento de los Datos
- **Descripción:** Se aplicó escalamiento estándar (StandardScaler) para normalizar las variables numéricas.
- **Pasos:** Se ajustó el escalador a los datos de entrenamiento y se aplicó tanto a los datos de entrenamiento como a los datos de prueba.

---

## 4. Modelado Predictivo

### 4.1 Modelos Implementados
- **Árboles de Decisión**
- **Random Forest**

### 4.2 División de los Datos
- **Descripción:** Los datos se dividieron en:
  - Conjunto de entrenamiento (80%)
  - Conjunto de prueba (20%)
- **Pasos:**
  1. Separación de la variable objetivo (`n_accidentes`) y las variables predictoras (`territorial`, `clase_accidente`, `n_heridos`, `n_muertos`).
  2. Escalamiento aplicado al conjunto de entrenamiento y transformado al conjunto de prueba.

---

## 5. Resultados

### Árbol de Decisión
- **Puntos fuertes:** Alto desempeño en todas las métricas:  
  - Exactitud: 98.5%  
  - Precisión: 98.51%  
  - Recall: 98.5%  
  - F1-Score: 98.45%  
  Modelo interpretable y computacionalmente eficiente.
- **Limitaciones:** Más propenso al sobreajuste.

### Random Forest
- **Puntos fuertes:** Menos propenso al sobreajuste que el Árbol de Decisión.  
  - Exactitud: 97.0%  
  - Precisión: 96.11%  
  - Recall: 97.0%  
  - F1-Score: 96.45%  
  Modelo robusto con capacidad para manejar datos complejos.
- **Limitaciones:** Menos interpretable y con mayor costo computacional.

---

## 6. Comparación de Modelos

| Modelo           | Exactitud | Precisión | Recall | F1-Score |
|-------------------|-----------|-----------|--------|----------|
| Árbol de Decisión | 0.985     | 0.985139  | 0.985  | 0.984535 |
| Random Forest     | 0.970     | 0.961099  | 0.970  | 0.964587 |

---

## 7. Conclusiones

- El Árbol de Decisión es altamente interpretable y útil para comprender las relaciones entre variables, pero su tendencia al sobreajuste limita su capacidad de generalización.
- Random Forest es más robusto y confiable para predicciones generalizables, aunque menos interpretable.
- **Recomendación:** Utilizar un enfoque híbrido: 
  - Random Forest para predicciones confiables.
  - Árbol de Decisión como herramienta explicativa.

---

## 8. Recomendaciones para Mejorar la Precisión
- Optimizar hiperparámetros como `n_estimators` y `max_depth` usando técnicas como GridSearchCV.
- Incluir características adicionales (e.g., condiciones climáticas, épocas festivas).
- Explorar modelos ensemble más avanzados como Gradient Boosting o XGBoost, # Modelado Predictivo Avanzado con Datos Abiertos de Colombia

**Por:** Robinson Alexander Otálvaro  
**Curso:** Análisis de datos avanzado grupo 2  
**Código:** [Enlace a Colab](#)

---

## 1. Introducción
El análisis tiene como objetivo desarrollar un modelo predictivo para estimar el número de accidentes de tránsito en función de características clave relacionadas con los accidentes. Este análisis es crítico para comprender los factores que contribuyen a los accidentes y proporcionar información para la toma de decisiones orientadas a la prevención.

---

## 2. Justificación de las Variables Seleccionadas

1. **territorial (Localización geográfica):** Representa la ubicación administrativa donde ocurrieron los accidentes. Es relevante porque los factores locales, como la infraestructura vial, las regulaciones y el clima, pueden influir en la ocurrencia de accidentes.
2. **clase_accidente (Tipo de accidente):** Clasifica el tipo de accidente (e.g., colisión, atropello, vuelco). Proporciona información sobre las causas y circunstancias específicas de los accidentes.
3. **n_heridos (Número de heridos):** Indica el impacto del accidente en términos de personas lesionadas. Es un proxy del grado de severidad de los accidentes y tiene una correlación directa con el número de eventos.
4. **n_muertos (Número de muertos):** Indica el impacto más severo de un accidente. Su inclusión es crucial para reflejar la gravedad de los eventos y su relación con otros factores.
5. **n_accidentes (Variable objetivo):** Representa el total de accidentes, definido como la suma de heridos y muertos. Es la variable que se busca predecir, ya que proporciona una métrica consolidada del impacto de los accidentes en una región y situación específica.

---

## 3. Proceso Realizado

### 3.1 Carga del Archivo
- **Descripción:** Se utilizó un archivo CSV disponible en una URL pública. Este archivo contenía datos relacionados con los accidentes de tránsito registrados.
- **Pasos:**
  - Se cargó el archivo en un DataFrame de pandas.
  - Se seleccionaron únicamente las columnas relevantes (`territorial`, `clase_accidente`, `n_heridos`, `n_muertos`).
  - Se creó la columna objetivo `n_accidentes` como la suma de `n_heridos` y `n_muertos`.

### 3.2 Limpieza de Datos
- **Manejo de valores nulos:** Se identificaron y eliminaron las filas con valores faltantes en las columnas seleccionadas para evitar errores en el modelado.
- **Conversión de tipos de datos:** Las variables categóricas (`territorial` y `clase_accidente`) se convirtieron en valores numéricos mediante Label Encoding.
- **Eliminación de outliers:** Se aplicó el método del rango intercuartílico (IQR) para detectar y eliminar valores atípicos en las columnas numéricas.

### 3.3 Escalamiento de los Datos
- **Descripción:** Se aplicó escalamiento estándar (StandardScaler) para normalizar las variables numéricas.
- **Pasos:** Se ajustó el escalador a los datos de entrenamiento y se aplicó tanto a los datos de entrenamiento como a los datos de prueba.

---

## 4. Modelado Predictivo

### 4.1 Modelos Implementados
- **Árboles de Decisión**
- **Random Forest**

### 4.2 División de los Datos
- **Descripción:** Los datos se dividieron en:
  - Conjunto de entrenamiento (80%)
  - Conjunto de prueba (20%)
- **Pasos:**
  1. Separación de la variable objetivo (`n_accidentes`) y las variables predictoras (`territorial`, `clase_accidente`, `n_heridos`, `n_muertos`).
  2. Escalamiento aplicado al conjunto de entrenamiento y transformado al conjunto de prueba.

---

## 5. Resultados

### Árbol de Decisión
- **Puntos fuertes:** Alto desempeño en todas las métricas:  
  - Exactitud: 98.5%  
  - Precisión: 98.51%  
  - Recall: 98.5%  
  - F1-Score: 98.45%  
  Modelo interpretable y computacionalmente eficiente.
- **Limitaciones:** Más propenso al sobreajuste.

### Random Forest
- **Puntos fuertes:** Menos propenso al sobreajuste que el Árbol de Decisión.  
  - Exactitud: 97.0%  
  - Precisión: 96.11%  
  - Recall: 97.0%  
  - F1-Score: 96.45%  
  Modelo robusto con capacidad para manejar datos complejos.
- **Limitaciones:** Menos interpretable y con mayor costo computacional.

---

## 6. Comparación de Modelos

| Modelo           | Exactitud | Precisión | Recall | F1-Score |
|-------------------|-----------|-----------|--------|----------|
| Árbol de Decisión | 0.985     | 0.985139  | 0.985  | 0.984535 |
| Random Forest     | 0.970     | 0.961099  | 0.970  | 0.964587 |

---

## 7. Conclusiones

- El Árbol de Decisión es altamente interpretable y útil para comprender las relaciones entre variables, pero su tendencia al sobreajuste limita su capacidad de generalización.
- Random Forest es más robusto y confiable para predicciones generalizables, aunque menos interpretable.
- **Recomendación:** Utilizar un enfoque híbrido: 
  - Random Forest para predicciones confiables.
  - Árbol de Decisión como herramienta explicativa.

---

## 8. Recomendaciones para Mejorar la Precisión
- Optimizar hiperparámetros como `n_estimators` y `max_depth` usando técnicas como GridSearchCV.
- Incluir características adicionales (e.g., condiciones climáticas, épocas festivas).
- Explorar modelos ensemble más avanzados como Gradient Boosting o XGBoost, que combinan robustez y precisión para manejas relaciones no lineales. 

---


---
