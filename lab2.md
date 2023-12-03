## Sprawozdanie z Laboratorium 2 - Integracja z Azure Bing Search Service

---

### Ćwiczenie 1

Celem tego ćwiczenia było zapoznanie się z usługą Azure Bing Search i praktyczne zastosowanie jej w aplikacji. Wykorzystano Bing Search API do przeprowadzania złożonych zapytań wyszukiwania i analizy wyników.

---

### Realizacja

---

#### Krok 1: Środowisko
   Wykorzystano już zainstalowane na komputerze Microsoft Visual Studio 2022 i Visual Studio Code dla ćwiczenia 1.

---

#### Krok 2: Utworzenie zasobu Azure Cognitive Services
   Dokonano konfiguracji jak na screenie poniżej.

   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/7dcf1773-3404-418b-a1d5-8150a13af757" alt="image" style="width:60%;"/>

---

#### Kroki 3-7:
   Ten punkt laboratorium jako jedyny wykonano w Pythonie z uwagi na lepszą znajomość i szybkość wykonania z pomocą poradników dostępnych w menu 'Quickstart'. Utworzono małe okno zbierające od użytkownika typ wyszukiwania i hasło wyszukiwania. Dostępne typy to wyszukiwanie: wiadomości (news), zdjęć (images) oraz zwykłe wyszukiwanie (web). Po kliknięciu 'Search' wyniki otwierają się w nowej karcie przeglądarki. Zdecydowano się rozszerzyć aplikację o wyświetlanie od razu najlepszego zwróconego wyniku. Rezultaty poniżej.

<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/0bd2ec8b-5e22-40ed-bbb3-a0ab8e644ed7" alt="image" style="width:80%;"/>

<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/a0e26fa9-90e8-48ac-992d-c622ac505f08" alt="image" style="width:80%;"/>

<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/004961c8-18f2-4f51-a449-5f4ca5de1d67" alt="image" style="width:80%;"/>

---

### Ćwiczenie 2

Celem tego ćwiczenia było zaznajomienie się z Azure Speech Service oraz wykorzystanie tej usługi.

---

### Realizacja

---

#### Krok 1 i 2: Zasób Azure Speech
   Skonfigurowano zasoby jak na poniższym screenie.
   
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/79035517-489e-4a24-b247-71db7c5ab2cb" alt="image" style="width:60%;"/>
   
---

#### Krok 3, 4 i 5: Klucz dostępu, endpoint i działanie programu
   Z utworzonego zasobu, z menu po lewej wybrano Keys and Endpoint i dane z tej zakładki posłużyły do uwierzytelnienia w aplikacji C#. Korzystano z poradnika Microsoftu, ale zmieniono język rozpoznawania mowy na polski oraz wklejono endpoint i region wprost, zamiast dodawać zmienne środowiskowe.
W ramach testu powiedziano do mikrofonu: "To jest demo laboratorium drugiego". Output programu przedstawiono na poniższym screenie.

   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/5055b790-4fe7-41bb-b12a-b3772503ba25" alt="image" style="width:100%;"/>

---

#### Krok 6: Konwersja tekstu na mowę

Ponownie wykorzystano poradniki ścieżki learningowej Microsoftu i sprawnie utworzono konsolową aplikację do konwersji tekstu na mowę. Zmieniono klucze do uwierzytelnienia i wybrano kompatybilny głos dla języka polskiego. Program odczytuje tekst wpisany do konsoli po starcie. Dostępne są 3 głosy dla języka polskiego. Przedstawiono je poniżej.

  <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/4fc035be-882a-41dc-a393-8a4221790879" alt="image" style="width:70%;"/>

Wykonano próbę działania programu, wszystko wykonało się poprawnie i zgodnie z oczekiwaniami. Tekst przekonwertowano poprawnie.

  <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/c580c120-2ac0-44cf-bafa-04d4578dbdef" alt="image" style="width:100%;"/>

Możliwe jest również dodawanie własnego głosu, po dostarczeniu próbek treningowych.

Aby wykonać zadanie tłumaczenia tekstu z kroku 7 należałoby utworzyć nowy zasób z Translator API. Dla tego zasobu również istnieje ścieżka learningowa (https://learn.microsoft.com/en-us/azure/ai-services/translator/quickstart-text-rest-api?tabs=csharp), która bardzo szybko pomaga stworzyć podstawową aplikację. Możliwe jest rozponawanie języka automatycznie lub podawanie ich wprost.

---

### Ćwiczenie 3

Celem tego ćwiczenia było zapoznanie się z Azure Form Recognizer i jego zastosowaniem do analizowania i przetwarzania dokumentów.

---

### Realizacja

---

#### Krok 1 i 2: Zasób Azure Form Recognizer
Skonfigurowano zasoby jak na poniższym screenie.
   
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/a7b2aba1-286f-4026-ac63-77f986b1b674" alt="image" style="width:60%;"/>

---

#### Kroki 3-6: Klucz dostępu, endpoint i działanie programu
   Z utworzonego zasobu, z menu po lewej wybrano Keys and Endpoint i dane z tej zakładki posłużyły do uwierzytelnienia w aplikacji C#. Korzystano z poradnika Microsoftu (https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/quickstarts/get-started-sdks-rest-api?view=doc-intel-4.0.0&pivots=programming-language-csharp), aby utworzyć program konsolowy w C#, który przyjęty dokument parsuje i wypisuje znalezione w nim dane.
Za dokument próbkowy użyłem raport z zawodów sportowych, jest to kilkustronowy dokument, ponieważ opcja parsowania kilku stron od razu jest dostępna w startowym programie. Wyniki na próbce zaproponowanej przez Microsoft były bardzo dobre, ale dla własnego dokumentu wyniki również są satysfakcjonujące.
Link do próbki testowej: https://ampy.pl/files/docs2122/wyniki/2122_futsal_m_final_wyniki.pdf.

Dla porównania próbka testowa Microsoftu: https://raw.githubusercontent.com/Azure-Samples/cognitive-services-REST-api-samples/master/curl/form-recognizer/sample-layout.pdf.

Wyniki przedstawiono poniżej (dla czytelności zakomentowano część programu odpowiedzialną za drukowanie wykrywanych bounding boxów).

<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/60a8ad15-7985-461b-8846-6947ec24c7f2" alt="image" style="width:100%;"/>

Wykryte pary klucz-wartość są dość chaotyczne, część z nich wykryto w pełni i poprawnie, a część jest niekompletnych. Pomimo tego, że dokument ma 11 stron, to w konsoli wydrukowano tylko informacje o pierwszych dwóch stronach (zaznaczony fragment w konsoli na powyższym screenshocie).
Tabele ze strony drugiej wykryto w pełni i poprawnie, tak samo jak wartości klucz-wartość. Dla strony pierwszej poprawnie wykryto linijki tekstu i ramki, w których się ten tekst znajduje.

Użyty kod oferuje znajdowanie tekstu, par klucz-wartość i tabel. Jednak można również używać gotowych modeli, np. do klasyfikacji paragonów. Otrzymujemy wtedy posegregowane dane, z odpowiednimi etykietami, nazwami i pewnością odczytanej wartości. Jednak do takiego testu z własnym dokumentem zdecydowanie lepszym rozwiązaniem jest uniwersalne wyszukiwanie, takie jak w powyższym przykładzie.

Drugi test przeprowadzono na dokumencie: https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/fab1c772-2e08-479f-85e3-62e921cbb17a. Wyniki są dobre, przedstawiono je poniżej.

<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/942fbf6e-1543-4ada-92e5-1304f702bc2c" alt="image" style="width:100%;"/>

---

### Ćwiczenie 4

Celem tego ćwiczenia była nauka korzystania z Azure QnA Maker do tworzenia, szkolenia i publikowania inteligentnej bazy wiedzy, która może być wykorzystana do obsługi chatbota.

---

### Realizacja

---

#### Krok 1 i 2: Zasób Azure QnA Maker
  Portal zwrócił ostrzeżenie, że najnowsza wersja tego produktu jest dostępna w zasobie Language po dodaniu opcji na odpowiadanie na pytania niestandardowe. Nie mogłem utworzyć 'starszej' wersji, zatem postąpiłem tak jak wskazywało ostrzeżenie. Konfiguracja poniżej.
   
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/85159a0d-ce50-428a-8b99-5ded4da3b95a" alt="image" style="width:60%;"/>

---

#### Kroki 3-6: Klucz dostępu, endpoint i działanie programu
Pobrano klucz i endpoint z menu zasobu. Zgodnie z https://learn.microsoft.com/pl-pl/azure/ai-services/language-service/question-answering/quickstart/sdk?pivots=programming-language-csharp&tabs=windows rozpoczęto tworzenie aplikacji konsolowej.
Do stworzenia projektu wykorzystano gotowego bota "chitchat" w wersji angielskiej z opcją odpowiedzi "Caring", zatem bot powinien być bardzo miły odpowiadając na pytania z domyślnej bazy. Dodatkowo dodano mu do bazy 4 pytania dotyczące zamówień ze sklepu internetowego. 
Bazę udostępniono i wdrożono do wcześniej utworzonego zasobu. Z wykorzystaniem Azure.AI.Language.QuestionAnswering stworzono prostą aplikację zbierającą pytanie wpisane do konsoli, łączącą się z chatbotem i zwracającą odpowiedź na pytanie. Testy poniżej:

<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/7d73a96b-d896-4b49-a91f-431bde940656" alt="image" style="width:100%;"/>

Powyższe pytanie zostało wprowadzone do bazy przeze mnie. Samo pytanie zostało trochę sparafrazowane, ale i tak bot dał radę na nie odpowiedzieć poprawnie. Następnie postanowiłem przetestować bazę domyślną. Na poniższym screenie można przyjrzeć się wynikom. Bot potrafił odpowiedzieć na pytanie spoza bazy, ale błędnie, aby innym razem poprawnie zorientować się, że nie umie na nie odpowiedzieć.

<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/d1ceb597-6404-4ad2-bae3-943a8fbabb38" alt="image" style="width:90%;"/>

---

### Podsumowanie

Wykonano wszystkie ćwiczenia i wśród nich częściowo wykonano również opcjonalne funkcjonalności. Laboratorium pozwoliło na zapoznanie się z podstawowymi opcjami 4 usług MS Azure. Wszystkie z tych 4 usług mają duży potencjał. Chatbot można bardzo solidnie wytrenować i używać w zewnętrznych aplikacjach. Form Recognizer mógłby znacznie wspomóc i przyspieszyć żmudną pracę osób przepisujących dokumenty papierowe na elektroniczne, a Text to Speech z opcją dodawania własnych próbek głosu aktualnie jest dość często używany do generowania fałszywych filmów informacyjnych w sieci z wykorzystaniem wizerunku osób publicznych.
