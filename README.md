# Plant Disease Classification ResNet50 vs VGG16 (Grad-CAM)

Kod źródłowy do studium porównawczego klasyfikacji chorób liści
piętnastu klas zbioru PlantVillage z wykorzystaniem ResNet50 i VGG16,
z analizą interpretowalności decyzji metodą Grad-CAM.

## Dane
PlantVillage subset (15 klas):
https://www.kaggle.com/datasets/emmarex/plantdisease

## Uruchomienie

Wszystkie notebooki przeznaczone do Google Colab z GPU (testowano na NVIDIA Tesla T4, 16 GB VRAM).

1. Podmontuj Google Drive z folderem `plant_disease_classification/`.
2. Wpisz token Kaggle w komórce KAGGLE (pobranie zbioru danych).
3. Uruchom `train_5fold_cv.ipynb` pięciokrotnie, zmieniając `FOLD_IDX` na 0, 1, 2, 3, 4 przed każdą sesją.
4. Uruchom `train_5x2cv.ipynb` pięciokrotnie, zmieniając `REP_IDX` na 0, 1, 2, 3, 4 przed każdą sesją.
5. Uruchom `aggregate.ipynb` — generuje wszystkie statystyki i rysunki.

## Uwagi praktyczne

- Limit sesji Google Colab nie pozwala odpalić wszystkich podziałów za jednym razem,
  dlatego w `train_5fold_cv.ipynb` i `train_5x2cv.ipynb` przewidziano ręczne przełączanie
  parametrów `FOLD_IDX` / `REP_IDX` między sesjami.
- Pełne odtworzenie eksperymentu zajmuje ~25-30 godzin GPU sumarycznie
  (5-fold CV: ~10h, 5×2cv: ~15-20h).
- Wagi modeli i pliki `metrics.json` zapisywane są na podmontowanym Google Drive
  i można je usuwać między sesjami, jeśli brakuje miejsca.

## Ziarna losowości

| Protokół | Seedy |
|---|---|
| 5-fold CV | 42 (jeden, dla `StratifiedKFold`) |
| 5×2cv | 42, 1042, 2042, 3042, 4042 (po jednym na powtórzenie) |

## Licencja

Unlicense (public domain).
