## Sprawozdanie z Laboratorium 1 - Baza danych MS SQL Server w Azure

---

### Wprowadzenie

Celem tego ćwiczenia było zaznajomienie się z podstawami usługi Azure SQL Database oraz praktyczne zastosowanie nabytych umiejętności poprzez stworzenie bazy danych, połączenie się z nią oraz wykonanie operacji na danych.

---

### Realizacja

---

#### Krok 1: Konto Azure
   Konto zostało utworzone z wykorzystaniem maila z domeny PW w formie subskrypcji akademickiej oferującej 100 dolarów na 12 miesięcy.

---

#### Krok 2 i 3: Utworzenie instancji Azure SQL Database
   Dokonano konfiguracji zgodnie z poniższymi zrzutami ekranu.
   
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/e5b59d56-d433-4aa5-bda5-7893ecdffd7d" alt="image" style="width:80%;"/>
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/5ed307c1-d456-417f-8d4e-f8cd652a0808" alt="image" style="width:80%;"/>
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/14ad9598-3b41-41e8-a876-3c2ac112e37a" alt="image" style="width:80%;"/>
  
   Zakładkę z zabezpieczeniami zostawiono na ustawieniach domyślnych, a jako źródło danych użyto przykładowej bazy AdventureWorksLT. Po pomyślnym wdrożeniu testowo wyświetlono zawartość jednego z widoków dostępnych w przykładowej bazie.
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/2142f32c-75ca-4d2e-ae53-24060d7b5ecd" alt="image" style="width:80%;"/>

---

#### Krok 4: Połączenie z bazą danych
   Dokonano połączenia zarówno poprzez SSMS jak i Azure Data Studio, co przedstawiono na dwóch poniższych zrzutach ekranu.
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/f549f941-fd0f-4c1a-968f-e565843de726" alt="image" style="width:80%;"/>
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/38a317dd-e074-447d-89f8-0213bfe40bd2" alt="image" style="width:80%;"/>

---

#### Krok 5: Tworzenie aplikacji
   Z pomocą poradników ścieżki learningowej Microsoftu i poradników na YouTube stworzono lokalną obsługę operacji CRUD w Swaggerze dla tabeli Customer. Dodano również IP do firewalla, aby zautoryzować dostęp do aplikacji. Na screenie widać poprawność rekordu z id=5 zwracanego przez API.
   
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/cad2f5c3-b622-41fb-9c15-026bafd54c1d" alt="image" style="width:80%;"/>
   
   Usunięto również klientów z id=1 i id=200 i sprawdzono wykonując zapytanie na bazie, czy poprawnie usunięto dane. Jak widać, brak id 1 i 200. API dla tych ID również zwraca brak rekordu.
   <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/775682c4-34c0-4318-94b7-7fa95091b047" alt="image" style="width:80%;"/>

---

#### Krok 6: Wirtualna maszyna z SQL Server
   Utworzono wirtualną maszynę z SQL Server, natomiast dwukrotnie jej deploy nie udał się. Po włączeniu maszyny i ustawieniu publicznego adresu połączenia nie udało się połączyć do serwera poprzez SSMS. Postępowano zgodnie z https://learn.microsoft.com/en-us/sql/ssms/quickstarts/ssms-connect-query-sql-server-azure-vm?view=sql-server-ver16

---

#### Krok 7: Azure Table Storage
   Utworzono Azure Table Storage, a następnie prostym programem konsolowym dodano encję, usunięto encję i wyświetlono atrybuty innej encji na ekranie. Poniżej znajdują się zrzuty ekranu kodów użytych do tych działań.
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/b9ac589e-84aa-4d80-a1b3-db638dacefb8" alt="image" style="width:80%;"/>
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/103c58b9-afa6-4bab-b9a5-1ef59c2567c0" alt="image" style="width:80%;"/>
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/e0c47ce3-16c8-475c-a7fa-8b65a9c9ef7b" alt="image" style="width:80%;"/>

---

#### Krok 8: Azure CosmosDB
   Utworzono domyślną bazę danych i kontener "Products" zgodnie z interfejsem wyświetlającym się po wybraniu "Launch quick start". Dodano 4 proste dokumenty z wykorzystaniem Data Explorer. Jego struktura przedstawiona jest na zrzucie poniżej, partycjonowanie jest po id (czyli w sumie mamy item i parition_key taki sam, ale trudno).
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/bdfef4fc-9c81-4cde-94a6-7c6af8d8286a" alt="image" style="width:80%;"/>

Wykonano dwa proste zapytania, które przedstawią pełną strukturę dokumentu json oraz sprawdzą działanie klauzuli WHERE.
<div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/05c38c99-01e8-4a52-83d9-8e2b37bcd64e" alt="image" width="45%" height="400px">
    <img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/8230ac12-4196-445f-9154-aa9e49d7095c" alt="image" width="45%" height="400px">
</div>

W zakładce Insights można monitorować wykorzystanie zasobów bazy.
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/5c68a462-1636-4648-840b-09368e3fb5ab" alt="image" style="width:80%;"/>

Tym razem operacje na danych wykonano w Pythonie z uwagi na to, że jest to dla mnie bardziej komfortowy język i ścieżka learningowa Microsoftu oferuje dobry materiał (https://learn.microsoft.com/en-us/azure/cosmos-db/nosql/quickstart-python?tabs=azure-portal%2Cconnection-string%2Cwindows%2Csign-in-azure-cli%2Csync). Na poniższym screenie przedstawiono konsolowy program, w którym dodano nowy item do kontenera i wydrukowano go na ekranie. Dodany item również jest dostępny w Data Explorer.
<img src="https://github.com/kajoo8/sprawozdania-lab-azure/assets/87271512/6847f239-ee44-457f-ba80-92c9bd154d8a" alt="image" style="width:80%;"/>

Z wykorzystaniem metody delete_item, która również przyjmuje item i klucz jako argument usunięto dane z bazy. Sprawdzono w Data Explorer i operacja powiodła się.

---

### Podsumowanie

Wykonano wszystkie ćwiczenia, jednak nie udało się w pełni wykonać ćwiczenia z wirtualną maszyną z zainstalowanym SQL Server. W trakcie ćwiczeń zapoznano się z rozwiązaniami Azure zarówno w kontekście baz relacyjnych jak i nierelacyjnych.
