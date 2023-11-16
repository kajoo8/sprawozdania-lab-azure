## Sprawozdanie z Laboratorium 1 - Baza danych MS SQL Server w Azure

---

### Wprowadzenie

Celem tego ćwiczenia było zaznajomienie się z podstawami usługi Azure SQL Database oraz praktyczne zastosowanie nabytych umiejętności poprzez stworzenie bazy danych, połączenie się z nią oraz wykonanie operacji na danych.

---

### Realizacja

---

#### Krok 1: Konto Azure
   Konto zostało utworzone z wykorzystaniem maila uczelnianego w formie sukskrypcji akademickiej oferującej 100 dolarów na 12 miesięcy oraz pakiet popularnych serwisów za darmo.

---

#### Krok 2 i 3: Utworzenie instancji Azure SQL Database
   Dokonano konfiguracji zgodnie z poniższymi zrzutami ekranu.
   
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/e5b59d56-d433-4aa5-bda5-7893ecdffd7d" alt="image" style="width:80%;"/>
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/5ed307c1-d456-417f-8d4e-f8cd652a0808" alt="image" style="width:80%;"/>
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/14ad9598-3b41-41e8-a876-3c2ac112e37a" alt="image" style="width:80%;"/>
  
   Zakładkę z zabezpieczeniami zostawiono na ustawieniach domyślnych, a jako źródło danych użyto przykładowej bazy AdventureWorksLT. Po pomyślnym wdrożeniu testowo wyświetlono zawartość jednego z widoków dostępnych w przykładowej bazie.
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/2142f32c-75ca-4d2e-ae53-24060d7b5ecd" alt="image" style="width:90%;"/>

---

#### Krok 4: Połączenie z bazą danych
   Dokonano połączenia zarówno poprzez SSMS jak i Azure Data Studio, co przedstawiono na dwóch poniższych zrzutach ekranu.
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/f549f941-fd0f-4c1a-968f-e565843de726" alt="image" style="width:90%;"/>
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/38a317dd-e074-447d-89f8-0213bfe40bd2" alt="image" style="width:90%;"/>

---

#### Krok 5: Tworzenie aplikacji
   Z pomocą poradników ścieżki learningowej Microsoftu i poradników na YouTube stworzono lokalną obsługę operacji CRUD w Swaggerze dla tabeli Customer. Dodano również IP do firewalla, aby zautoryzować dostęp do aplikacji. Na screenie widać poprawność rekordu z id=5 zwracanego przez API.
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/cad2f5c3-b622-41fb-9c15-026bafd54c1d" alt="image" style="width:90%;"/>
   
   Usunięto również klientów z id=1 i id=200 i sprawdzono wykonując zapytanie na bazie, czy poprawnie usunięto dane. Jak widać, brak id 1 i 200.
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/775682c4-34c0-4318-94b7-7fa95091b047" alt="image" style="width:90%;"/>

---

#### Krok 6: Wirtualna maszyna z SQL Server
   Utworzono wirtualną maszynę z SQL Server, natomiast dwukrotnie jej deploy nie udał się. Po włączeniu maszyny i ustawieniu publicznego adresu połączenia nie udało się połączyć do serwera poprzez SSMS. Postępowano zgodnie z https://learn.microsoft.com/en-us/sql/ssms/quickstarts/ssms-connect-query-sql-server-azure-vm?view=sql-server-ver16

---

#### Krok 7: Azure Table Storage
   Utworzono Azure Table Storage, a następnie prostym programem konsolowym dodano encję, usunięto encję i wyświetlono inną encję na ekranie. Poniżej znajdują się zrzuty ekranu użyte do tych działań.
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/b9ac589e-84aa-4d80-a1b3-db638dacefb8" alt="image" style="width:90%;"/>
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/103c58b9-afa6-4bab-b9a5-1ef59c2567c0" alt="image" style="width:90%;"/>
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/e0c47ce3-16c8-475c-a7fa-8b65a9c9ef7b" alt="image" style="width:90%;"/>

   
