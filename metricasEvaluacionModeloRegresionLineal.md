# 📊 Métricas para Evaluar un Modelo de Regresión Lineal

---

## 1. Métricas Basadas en Errores

Estas métricas cuantifican la diferencia entre los valores reales \( y_i \) y los valores predichos \( \hat{y}_i \).

### 🔸 MAE — Mean Absolute Error

$$
\text{MAE} = \frac{1}{n} \sum_{i=1}^{n} \left| y_i - \hat{y}_i \right|
$$

- Promedio de errores absolutos.
- Robusta ante valores atípicos.

---

### 🔸 MSE — Mean Squared Error

$$
\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

- Penaliza más los errores grandes.
- No tiene la misma unidad que \( y \).

---

### 🔸 RMSE — Root Mean Squared Error

$$
\text{RMSE} = \sqrt{\text{MSE}} = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}
$$

- MSE en las mismas unidades que \( y \).

---

### 🔸 MAPE — Mean Absolute Percentage Error

$$
\text{MAPE} = \frac{100\%}{n} \sum_{i=1}^{n} \left| \frac{y_i - \hat{y}_i}{y_i} \right|
$$

- Error relativo en porcentaje.
- Sensible a valores reales cercanos a cero.

---

### 🔸 SMAPE — Symmetric MAPE

$$
\text{SMAPE} = \frac{100\%}{n} \sum_{i=1}^{n} \frac{|y_i - \hat{y}_i|}{(|y_i| + |\hat{y}_i|)/2}
$$

- Versión simétrica del MAPE.
- Estable cuando \( y_i \approx 0 \).

---

## 2. Métricas Basadas en Varianza Explicada

### 🔸 R² — Coeficiente de Determinación

$$
R^2 = 1 - \frac{\text{SSE}}{\text{SCT}} = \frac{\text{SSR}}{\text{SCT}}
$$

- Mide la proporción de variabilidad explicada por el modelo.
- Varía entre 0 (malo) y 1 (perfecto).

---

### 🔸 R² Ajustado

$$
R^2_{adj} = 1 - \left(1 - R^2\right) \cdot \frac{n - 1}{n - k - 1}
$$

- Penaliza por usar variables irrelevantes.
- \( k \): número de variables independientes.

---

### 🔸 SCT — Suma Total de los Cuadrados
### 🔸 TSS - Total Sum of Squares

$$
\text{SCT} = \sum_{i=1}^{n} (y_i - \bar{y})^2
$$

- Mide la variación total en los datos.

---

### 🔸 SSR — Sum of Squares for Regression o Sum of Squares Residual (Suma de los Cuadrados de la Regresión)
### 🔸 ESS - Explained Sum of Squares

$$
\text{SSR} = \sum_{i=1}^{n} (\hat{y}_i - \bar{y})^2
$$

- Variación explicada por el modelo.

---

### 🔸 SSE — Sum of Squared Errors (Suma de los Cuadrados del Error -Residuos-)
### 🔸 RSS - Residual Sum of Squares

$$
\text{SSE} = \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

- Variación no explicada por el modelo.

---

## 3. Métricas Estadísticas

### 🔸 Estadístico t

$$
t = \frac{\hat{\beta}_j}{SE(\hat{\beta}_j)}
$$

- Evalúa si el coeficiente \( \beta_j \) es significativamente distinto de 0.

---

### 🔸 p-valor

$$
p = 2 \cdot P(T > |t|)
$$

- Probabilidad de obtener un valor tan extremo como \( t \) bajo la hipótesis nula.

---

### 🔸 Estadístico F

Evalúa si al menos una variable independiente tiene un efecto significativo.

$$
F = \frac{\text{SSR} / k}{\text{SSE} / (n - k - 1)}
$$

- \( k \): número de predictores.

---

### 🔸 Prob(F-statistic)

- El p-valor asociado al estadístico F.
- Evalúa la hipótesis nula: todos los coeficientes \( \beta_i = 0 \).

---

## 4. Métricas de Evaluación de Residuos

### 🔸 Durbin-Watson

- Evalúa autocorrelación en los residuos.
- Ideal: cercano a 2.

---

### 🔸 Jarque-Bera

- Prueba de normalidad para los residuos.

---

### 🔸 Omnibus

- Prueba combinada para normalidad (asimetría y curtosis).

---

### 🔸 Skewness y Kurtosis

- Asimetría (skewness): ideal cercano a 0.
- Curtosis: ideal cercano a 3 (normal).

---
