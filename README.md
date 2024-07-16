Plik o nazwie "Utworzenie bazy oraz jej obiektów" zawiera w sobie kod SQL tworzący bazę danych, 4 tabele oraz 6 procedur
Plik o nazwie "Skrypt" zawiera skrypt tworzący 100 userów 10 podmiotów oraz 1000 zadań dla każdego użytkownika. 

Baza TaskManagementSystem zawiera 4 tabele:

Tenants - zawierająca listę podmiotów
Users - lista userów w raz z ich rolami oraz przypisaniem przełożonego
Tasks - zadania z informacją o tytule, priorytecie, opisie oraz statusie. 
TaskHistory - zawiera wszelkie zmiany dotyczące zadań

Tabela Tenants, User, Tasks zawiera w sobie kolumną ...IsActive typu BIT (0 - false oraz 1 - true) przechowująca informację że dany rekord nie jest już aktualny. (Jest to sposób na archiwizację, należało by ustawić cyklicznie uruchamianą procedurę która usuwała by rekordy z wartością 0 oraz datą edycji np. dłuższą niż miesiąc temu)

Zostało utworzone 6 procedur:

AddTask - procedura dodająca nowego taska do tabeli Tasks
EditTask - procedura pozwalająca przypisać nowe wartości dla danego taska
DeleteTask - prcedura zmieniająca wartość ..IsActive na 0 (false).
GetUserTasks - zwracająca wszystkie taski przypisane dla wskazanego użytkownika
GetSubordinateManagerTask - zwracająca wszystkie taski dla podległych pracowników wskazanego menadżera
GetStatisticsTask - zwracająca statystyki dotyczące podległych pracowników wskazanego menadżera w podziałem na użytkownika, status oraz miesiąc.
