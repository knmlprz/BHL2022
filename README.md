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

