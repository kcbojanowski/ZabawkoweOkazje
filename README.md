# Zabawkowe Okazje
## Opis
Projekt "Zabawkowe Okazje" ma na celu zbudowanie aplikacji webowej, która ma ułatwić zakupy internetowe. Użytkownik po wprowadzeniu danych ręcznie bądź importując plik wyszukuje przedmiotów. Jeżeli przedmioty, których szukał nie były jednoznaczne to aplikacja zasugeruje różne propozycje, na które użytkownik może się zdecydować. Po dokonaniu wyboru strona ponownie wyszuka podanych przedmiotów. Wyniki wyszukiwania zostaną przepuszczone przez algorytm, który wybierze przedmioty najtańsze oraz te z najmniejszej ilości sklepów. Użytkownik będzie mógł pobrać posortowane wyniki, a dodatkowo (jeżeli będzie zalogowany) zobaczyć historię wyszukiwania.

## Description
The project "Zabawkowe Okazje" aims to build a web application to facilitate online shopping. The user, after entering data manually or by importing a file, searches for items. If the items he or she was looking for were not explicit, the application will suggest different suggestions that the user can decide on. Once the selection has been made, the website will search for the specified items again. The search results will be run through an algorithm that will select the cheapest items and those from the least number of shops. The user will be able to download the sorted results and, in addition (if logged in), see the search history.

### UML działania aplikacji
#### Wyszukiwanie
![image](https://user-images.githubusercontent.com/48855984/215847556-b299c87f-0cb5-4b90-83d3-e166f2bd02ba.png)

#### Rejestracja i Logowanie
![image](https://user-images.githubusercontent.com/48855984/215851448-87b2ff7a-3c43-4966-af90-ee63149c1ce4.png)

### przedmioty.json
```
{
 "id"               :"int"
 "nazwa"            :"string",
 "cena"             :"float",
 "cena_dostawy"     :"float",
 "sklep"            :"string",
 "link"             :"string"
}
```

### nazwy.txt
```txt
nazwa1
nazwa2
nazwa3
.
.
nazwan
```

### lokalna baza danych
![image](https://user-images.githubusercontent.com/48855984/214115030-ef674153-a5af-438d-8e5b-31c1d2ed717c.png)

### zasada działania (wstępna)
Otrzymujemy pliki.json, łączymy w megaliste, wyniki wyświetlamy domyślnie posortowane po cenie (osobno różne typy zabawek), jeżeli będzie sortowanie po dostawcy to wyniki od tych samych dostawców się mergują.

## How to start

Aby uruchomić aplikację, potrzebujesz dockera.

```bash
  docker compose up -d
```

Powyższa komenda automatycznie buduje i uruchamia kontener aplikacji i bazę danych

## Dokumentacja
### stronka
Folder, w którym znajduje się kod źródłowy strony.
### ceneo
Folder, w którym znajduje się mechanizm pobierający dane na serwisie ceneo. 
Pliki:
- chromedriver - silnik wyszukiwarki chrome dla urządzeń Linux
- chromedriver.exe - silnik wyszukiwarki chrome dla urządzeń Windows
- `main.py`, `my_ceneo.py` - moduły w których napisany jest mechanizm szukający

### static i templates
Foldery, w których napisany jest frontend strony. Zawiera:
- css
- html
- obrazki
- pliki wysłane na serwer

### Moduły:
- `algorithmSort.py` - algorytm który jest używany do dobierania najtańszych produktów i produktów z najmniejszej ilości sklepów
- `forms.py` - formularze używane do logowania i rejestracji
- `models.py` - architektura bazy danych
- `routes.py` - warstwa komunikacji frontendu z backendem
- `sendmail.py` - moduł wysyłający mail potwierdzający
