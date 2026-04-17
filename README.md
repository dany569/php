# php
To zadanie polega na przygotowaniu skryptu PHP, który połączy się z Twoją wcześniejszą bazą danych (SQL) i pobierze z niej konkretne informacje za pomocą zapytania SELECT z wykorzystaniem relacji (często wymagających operatora JOIN).
Oto jak podejść do tego zadania krok po kroku:
1. Połączenie z bazą danych
Musisz zacząć od nawiązania połączenia przez mysqli lub PDO. Przykładowo dla bazy gra_rpg:
php
$conn = new mysqli("localhost", "root", "", "gra_rpg");
Używaj kodu z rozwagą.
2. Wykonanie zapytania SQL
W zależności od wybranego tematu, Twoim głównym celem jest sformułowanie zapytania, które połączy tabele. Jeśli nie masz własnej bazy i wybierasz gra_rpg, zapytanie powinno wyglądać mniej więcej tak:
sql
SELECT bóstwa.nazwa, statystyki.nazwa_statystyki 
FROM bóstwa 
JOIN statystyki ON bóstwa.id_statystyki = statystyki.id;
Używaj kodu z rozwagą.
3. Wyświetlenie wyników w PHP
Dane należy "wyjąć" z bazy w pętli (np. while) i ubrać w czytelną listę lub tabelę HTML:
php
$result = $conn->query($sql);
while($row = $result->fetch_assoc()) {
    echo "Bóstwo: " . $row['nazwa'] . " - Statystyka: " . $row['nazwa_statystyki'] . "<br>";
}
