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
   Z pomocą https://learn.microsoft.com/en-us/azure/azure-sql/database/azure-sql-dotnet-entity-framework-core-quickstart?view=azuresql&tabs=visual-studio%2Cazure-portal%2Cportal (chociaż część dotycząca jsona z connection stringiem jest niepoprawna -- musiałem ją poprawiać) stworzono lokalną obsługę metod POST i GET, którą następnie opublikowano w chmurze.
