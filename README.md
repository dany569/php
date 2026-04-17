# php
To zadanie polega na przygotowaniu skryptu PHP, który połączy się  bazą danych i pobierze z niej konkretne informacje za pomocą zapytania SELECT z wykorzystaniem relacji 

# 1. Połączenie z bazą danych

## Musisz zacząć od nawiązania połączenia przez mysqli lub PDO. Przykładowo dla bazy gra_rpg:

$conn = new mysqli("localhost", "root", "", "gra_rpg");

# 2. Wykonanie zapytania SQL

## Głównym celem jest sformułowanie zapytania, które połączy tabele. Zapytanie powinno wyglądać mniej więcej tak:

SELECT bóstwa.nazwa, statystyki.nazwa_statystyki 
FROM bóstwa 
JOIN statystyki ON bóstwa.id_statystyki = statystyki.id;

# 3. Wyświetlenie wyników w PHP
## Dane należy "wyjąć" z bazy w pętli i ubrać w czytelną listę lub tabelę HTML:

$result = $conn->query($sql);
while($row = $result->fetch_assoc()) {
    echo "Bóstwo: " . $row['nazwa'] . " - Statystyka: " . $row['nazwa_statystyki'] . "<br>";
}
