## Sprawozdanie z Laboratorium 3 - Tworzenie i Wdrażanie Modelu ML do Rozpoznawania Obrazów z Azure Machine Learning

---

### Ćwiczenie 1

Celem tego ćwiczenia było zapoznanie się z możliwością tworzenia, szkolenia i wdrażania modeli ML do rozpoznawania obrazów z Azure Machine Learning Studio. Po wejściu na Azure Machine Learning Studio wyskakuje monit o tym, że Microsoft sugeruje korzystanie z zasobów Azure Machine Learning na ml.azure.com z uwagi na kończące się wsparcie w 2024 roku. Dodawanie nowych datasetów jest zablokowane, a liczba dostępnych niewielka - podsumoując zachęcają do używania innego zasobu niż ten wymieniony w instrukcji. Ćwiczenie jest trudne do wykonania w całości i zostanie wykonane na nowym zasobie, a nie tym wymienionym w instrukcji.

---

### Realizacja

W zakładce Designer wybrano Image classification model i tam wybrano architekturę Densenet201 już wytrenowaną uprzednio. Parametry dodatkowego treningu przedstawiono poniżej.

![image](https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/651db2ad-9b0f-4e75-8533-724e99188f46)

Wybrano zbiór ze zwierzętami, Animal Images Dataset, a następnie utworzono pipeline i odczekano odpowiednią ilość czasu, aby model się utworzył i wytrenował. 
Uczenie trwało dość długo, jak na to, że mamy dostępny procesor w chmurze, który powinien być szybki. Taka architektura nie jest ogromna, danych też nie było dużo.

Po wytrenowaniu sieci nie można było użyć swoich danych do sprawdzenia jak sobie poradzi w predykcji.

Postanowiono wykonać inny model -- do predykcji cen aut. Architektura poniżej.

![image](https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/3dcede29-c118-40be-9b40-f12850f31773)

Po wytrenowaniu, wyniki prezentują się następująco (przedostatnia kolumna to etykieta, ostatnia predykcja).

![image](https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/0116bff2-098f-4d8b-9e42-6000e5ccb040)

---

### Podsumowanie

Wykonano ćwiczenie w miarę możliwości na nowym zasobie, a nie tym wspomnianym w instrukcji. Warto tu napomnieć, że w porównaniu do poprzednich ćwiczeń w internecie jest bardzo mało dostępnych materiałów nt. tej usługi - jest ona nowa i może to jest przyczyną. Stara usługa nie będzie wspierana od sierpnia 2024. Upubliczniłem również endpoint, ale nie znalazłem pomocy w ścieżkach learningowych nt. jego obsługi. Jeśli chodzi o trenowanie i tworzenie sieci, przeklikiwałem stronę intuicyjnie.
