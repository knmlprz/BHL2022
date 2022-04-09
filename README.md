# INFRAPRICE
## Oczyszczene i redukcja wymiarowości 
Oczyszczanie danych to najważniejsza część zadania. Bez dobrze przygotowanych danych, modele
nie dadzą nam wiarygodnych wyników. Tabela przedstawiająca czym są kolumny znajduje się poniżej:

| Cecha              | Objaśnienie                                                                                                                                               |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| BORO               | Numer kodujący:  1 = MANHATTAN, 2 = BRONX,  3 = BROOKLYN, 4 = QUEENS, 5 = STATEN ISLAND                                                                   |
| Block              | Numer bloku (tego prostokąta z działek): MANHATTAN 1 TO 2,255.  BRONX 2,260 TO 5,958.  BROOKLYN 1 TO 8,955.  QUEENS 1 TO 16,350. STATEN ISLAND 1 TO 8,050 |
| LOT                | Numer działki (unikalny tylko w bloku)                                                                                                                    |
| LTFRONT            | Szerokość działki                                                                                                                                         |
| LTDEPTH            | Głębokość działki                                                                                                                                         |
| STORIES            | Liczba pięter                                                                                                                                             |
| AVLAND             | Faktyczna wartość działki                                                                                                                                 |
| AVTOT              | Całkowita wartość działki                                                                                                                                 |
| EXLAND             | Rzeczywista wartość gruntów zwolnionych z podatku                                                                                                         |
| EXTOT              | Całkowita wartość gruntów zwolnionych z podatku                                                                                                           |
| EASMENT            | Służebności gruntu np. słup energetyczny, studzienka ze światłowodem itp.                                                                                 |
| EXCD1              | Zwolnienie z podatku od nieruchomości                                                                                                                     |
| POSTCODE           | Kod pocztowy                                                                                                                                              |
| BLDFRONT           | Szerokość budynku                                                                                                                                         |
| BLTDEPTH           | Głębokość budynku                                                                                                                                         |
| Latitude           | Szerokość geograficzna                                                                                                                                    |
| Longitude          | Długość geograficzna                                                                                                                                      |
| Community Board    | kategoria (ID wspólnoty mieszkaniowej)l                                                                                                                   |
| Council District - | kategoria (ID rada dzielnicowa)                                                                                                                           |
| Census Tract       | kategoria (ID obszaru spisowego)                                                                                                                          |
| BIN                | NIEZNANA (prawdopodobnie przekształcenie BBL)                                                                                                             |


Część tych zmiennych zostało odrzuconych na starcie. Były to m. in.: 
- POSTCODE
- BIN - nie wiemy jak została stworzona
- Community Board - id, odrzucone po stworzeniu pierwszych modeli
- Council District - id, odrzucone po stworzeniu pierwszych modeli
- Census Tract - id, odrzucone po stworzeniu pierwszych modeli

Kolejne odrzuciliśmy wykorzysując metody Feature Selection (SFS) już tworząc modele oraz dokonując ich analalizy (jej cześć znajduje się w pliku `EDA_Kolumn.ipynb`. Z do ciekawszych zależności można zaliczyć:
- Działki, których Całkowita wycena była niewielka, sprzedawane były za kilkukrotnie większą cenę
- W surowym zbiorze danych w dwóch rekordach znajdował się błąd. Rekordy te były przemieszane.

![Wykres](docs/avtot_fullval.png)

## Wybór i wytrenowanie modelu uczenia maszynowego

Do trenowania i wyboru uczenia wykorzystaliśmy biblioteke Pycaret. Pozwala na tranowanie
wielu modeli na raz, automatycznie dokonuje ich oceny w wybranym zadaniu (wybierać można spośrod
klasyfikacji i regresjii) i dokonuje automatycznej optymalizacji ich parametrów.

Ponad to wszystko, genrowanie są informacje o najlepszym modelu. Są to:
- Hiperparamery
- Reszty modelu 
- Błędy predykcji
- Feature Selection (ile cech potrzebne było do osiągnęcia
