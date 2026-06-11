# wino
# Predykcja jakości białego wina

Projekt przedstawia analizę danych oraz budowę modeli regresyjnych przewidujących jakość białego wina na podstawie jego właściwości fizykochemicznych. Całość znajduje się w notebooku Jupyter Untitled5.ipynb.

## Opis projektu

Celem projektu jest przewidywanie wartości zmiennej quality, czyli oceny jakości białego wina. Ponieważ wartość jakości jest liczbowa, problem został potraktowany jako zadanie regresji.

W projekcie wykonano:

- wczytanie danych winequality-white.csv,
- podstawową eksplorację danych,
- sprawdzenie braków danych i duplikatów,
- wizualizację rozkładu ocen jakości oraz cech numerycznych,
- usunięcie zduplikowanych wierszy,
- podział danych na zbiór treningowy i testowy,
- trenowanie dwóch modeli regresyjnych,
- porównanie modeli za pomocą metryk RMSE, MAE oraz R²,
- analizę ważności cech dla modelu Random Forest,
- zapis wyników do pliku wyniki_modeli.csv.

## Zbiór danych

Projekt korzysta ze zbioru danych Wine Quality — white wine:

text https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-white.csv 

Dane zawierają 4898 próbek oraz 12 kolumn. Zmienną docelową jest quality, a pozostałe kolumny opisują właściwości fizykochemiczne wina, takie jak m.in. kwasowość, cukier resztkowy, chlorki, dwutlenek siarki, pH, siarczany i zawartość alkoholu.

## Użyte technologie

- Python
- Jupyter Notebook / Google Colab
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn

## Struktura repozytorium

text wino/ ├── README.md └── Untitled5.ipynb 

Po uruchomieniu notebooka mogą zostać utworzone dodatkowe pliki:

text winequality-white.csv wyniki_modeli.csv 

## Instalacja

Sklonuj repozytorium:

bash git clone https://github.com/milten-source/wino.git cd wino 

Zainstaluj wymagane biblioteki:

bash pip install numpy pandas matplotlib seaborn scikit-learn notebook 

## Uruchomienie

Uruchom notebook lokalnie:

bash jupyter notebook Untitled5.ipynb 

Możesz też otworzyć notebook w Google Colab. Notebook sam pobiera plik winequality-white.csv, jeżeli nie znajduje go lokalnie.

## Przebieg analizy

### 1. Wczytanie danych

Dane są pobierane z repozytorium UCI Machine Learning Repository i wczytywane do obiektu DataFrame za pomocą biblioteki pandas.

### 2. Eksploracja danych

Notebook sprawdza:

- pierwsze wiersze danych,
- liczbę wierszy i kolumn,
- typy danych,
- statystyki opisowe,
- braki danych,
- liczbę duplikatów,
- rozkład zmiennej quality.

W danych nie wykryto braków, ale znaleziono 937 zduplikowanych wierszy. Po ich usunięciu do modelowania wykorzystano oczyszczony zbiór danych.

### 3. Wizualizacja

W notebooku generowane są wykresy:

- rozkład ocen jakości wina,
- histogramy cech numerycznych,
- zależność między zawartością alkoholu a jakością,
- porównanie modeli według RMSE,
- wartości rzeczywiste vs przewidywane,
- ważność cech w modelu Random Forest.

### 4. Modelowanie

Porównano dwa modele:

| Model | RMSE | MAE | R² |
|---|---:|---:|---:|
| Random Forest Regressor | 0.7381 | 0.5633 | 0.3357 |
| Regresja liniowa | 0.7792 | 0.5974 | 0.2597 |

Lepszym modelem okazał się Random Forest Regressor, ponieważ uzyskał niższą wartość RMSE.

## Najważniejsze cechy według Random Forest

Największe znaczenie dla przewidywania jakości wina miały:

| Cecha | Ważność |
|---|---:|
| alcohol | 0.2507 |
| volatile acidity | 0.1218 |
| free sulfur dioxide | 0.1216 |
| pH | 0.0737 |
| total sulfur dioxide | 0.0665 |

Najważniejszą cechą była zawartość alkoholu (alcohol).

## Wyniki końcowe

Projekt pokazuje, że jakość białego wina można przewidywać na podstawie jego parametrów fizykochemicznych. Spośród porównanych modeli lepszy wynik uzyskał Random Forest Regressor. Wyniki modeli są zapisywane do pliku wyniki_modeli.csv.

## Możliwe usprawnienia

W kolejnych wersjach projektu można dodać:

- strojenie hiperparametrów modelu Random Forest,
- walidację krzyżową,
- porównanie większej liczby modeli,
- zapis wytrenowanego modelu do pliku,
- prostą aplikację do przewidywania jakości wina na podstawie danych wejściowych użytkownika.

## Autor

Projekt przygotowany w ramach analizy danych i uczenia maszynowego dotyczącego jakości białego wina.