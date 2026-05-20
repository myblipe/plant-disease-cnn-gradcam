# plant-disease-cnn-transfer-learning
Kod do artykułu: Studium przypadku zastosowania architektur ResNet50 i VGG16 do klasyfikacji chorób roślin z wykorzystaniem transfer learningu i metod XAI.

W repozytorium znajdują się dwa pliki:
01_train_fold.ipynb — trenowanie jednego podziału CV, należy uruchomić 5 razy, zmieniając FOLD_IDX od 0 do 4
02_aggregate_gradcam.ipynb — agregacja wyników, test Wilcoxona, macierze pomyłek, Grad-CAM

Jak uruchomić:

Uruchomić notebook w Google Colab z GPU
Wkleić swój KAGGLE_USERNAME i KAGGLE_KEY w komórce konfiguracyjnej
Uruchomić Runtime → Run all

Po uruchomieniu uczenia dataset pobiera się automatycznie, aby odtworzyć pełne uczenie należy wykonać train_fold_colab.ipynb pięciokrotnie, następnie dane, które zostały zapisane na Google Drive zostaną wczytane przez drugi plik aggregate_colab.ipynb, który należy wykorzystać po całościowym uczeniu obu modeli.

Licencja: Unlicense
