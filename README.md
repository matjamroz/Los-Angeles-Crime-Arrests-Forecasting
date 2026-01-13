# Los-Angeles-Crime-Arrests-Forecasting

English below

### Opis projektu
Głównym celem niniejszego projektu jest zbadanie i porównanie skuteczności różnorodnych modeli predykcyjnych w prognozowaniu danych o przestępczości i aresztowaniach w Los Angeles. Zamiast polegać na jednym rozwiązaniu, projekt analizuje, jak rożne modele uczenia maszynowego radzą sobie w specyficznym, nieliniowym środowisku.

### EDA i przetwarzanie danych
W fazie eksploracji danych skupiono się na zrozumieniu natury zjawisk przestępczych:
* **Analiza brakujących danych**: Identyfikacja luk w raportowaniu incydentów, uzupełnianie niekompletnych rekordów, usunięcie nie wnoszących nic kolumn.
* **Data Imputation**: Systemowe zarządzanie brakami danych w opisach i kodach.
* **Profilowanie demograficzne**: Rozkład wieku, płci oraz pochodzenia osób aresztowanych.
* **Resampling**: Agregacja danych do interwałów miesięcznych (`M`) oraz godzinowych.
* **Analiza temporalna**: Badanie natężenia przestępczości w cyklach miesięcznych.
* **Wizualizacja trendów**: Mapowanie dynamiki zdarzeń w czasie dla kluczowych dzielnic Los Angeles.
* **Dekompozycja Sezonowa**: Rozbicie szeregu na trend, sezonowość i szum.

* **Test Stacjonarności**: Wykorzystanie testu Dickeya-Fullera do determinacji, czy szereg wymaga różnicowania.
* **Analiza Autokorelacji**: Precyzyjna identyfikacja rzędów opóźnień dla procesów Moving Average i AutoRegressive.
* **Analiza Sezonowości Miesięcznej**: Identyfikacja cyklicznych wzorców w skali roku.
* **Analiza Lag 12**: Badanie korelacji rok-do-roku za pomocą wykresów opóźnień.

### Benchmark Modeli 
W ramach badania przetestowano następujące architektury:
1. **Prophet**: Modelowanie trendów nieliniowych z punktami zmiany (changepoints).
2. **SARIMA (Manual & Auto)**: Wykorzystanie `pmdarima` do automatycznej optymalizacji parametrów oraz manualne dopasowanie SARIMAX.
3. **Holt-Winters (Exponential Smoothing)**: Potrójne wygładzanie wykładnicze z trendem i sezonowością addytywną.
4. **LSTM**: Sieć neuronowa z dwiema warstwami LSTM oraz regularyzacją L2.

5. **Modele Bazowe (Naive & Seasonal Naive)**: Służące jako punkt odniesienia dla zaawansowanych algorytmów.

### Ewaluacja Modeli
Skuteczność każdego modelu oceniana jest na dwóch płaszczyznach:

**1. Metryki błędów:**
* **MAE** (Mean Absolute Error) – średni błąd bezwzględny.
* **MAPE** (Mean Absolute Percentage Error) – błąd wyrażony procentowo.
* **R² Score** – stopień wyjaśnienia zmienności przez model.

**2. Walidacja Statystyczna:**
* **Test Shapiro-Wilka**: Stosowany w fazie oceny modelu do analizy residuów. Sprawdza, czy błędy modelu mają rozkład normalny.
* **Diagnostyka residuów**: Badanie wykresów przebiegu i histogramów residuów.


---


### Project Description
The primary goal of this project is to investigate and compare the effectiveness of various predictive models in forecasting crime and arrest data in Los Angeles. Instead of relying on a single solution, the project analyzes how different machine learning models perform in a specific, non-linear environment.

### EDA and Data Processing
The data exploration phase focused on understanding the nature of criminal phenomena:
* **Missing Data Analysis**: Identifying gaps in incident reporting, completing incomplete records, and removing non-contributing columns.
* **Data Imputation**: Systematic management of missing data in descriptions and codes.
* **Demographic Profiling**: Distribution of age, gender, and descent of arrestees.
* **Resampling**: Data aggregation into monthly (`M`) and hourly intervals.
* **Temporal Analysis**: Studying crime intensity in monthly cycles.
* **Trend Visualization**: Mapping incident dynamics over time for key Los Angeles districts.
* **Seasonal Decomposition**: Breaking down the series into trend, seasonality, and noise.
* **Stationarity Test**: Using the Dickey-Fuller test to determine if the series requires differencing.
* **Autocorrelation Analysis**: Precise identification of lag orders for Moving Average and AutoRegressive processes.
* **Monthly Seasonality Analysis**: Identification of recurring annual patterns.
* **Lag 12 Analysis**: Investigating year-over-year correlation using lag plots.

### Model Benchmarking
The following architectures were tested as part of the study:
1. **Prophet**: Non-linear trend modeling with changepoints.
2. **SARIMA (Manual & Auto)**: Using `pmdarima` for automatic parameter optimization and manual SARIMAX fitting.
3. **Holt-Winters (Exponential Smoothing)**: Triple exponential smoothing with trend and additive seasonality.
4. **LSTM**: Neural network with two LSTM layers and L2 regularization.
5. **Baselines (Naive & Seasonal Naive)**: Serving as a reference point for advanced algorithms.

### Model Evaluation
The effectiveness of each model is evaluated on two levels:

**1. Error Metrics:**
* **MAE** (Mean Absolute Error).
* **MAPE** (Mean Absolute Percentage Error).
* **R² Score** – the degree of variance explained by the model.

**2. Statistical Validation:**
* **Shapiro-Wilk Test**: Applied during the model evaluation phase for residual analysis. It checks if the model errors follow a normal distribution.
* **Residual Diagnostics**: Examination of residual time-series plots and histograms.
