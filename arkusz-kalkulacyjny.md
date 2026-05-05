---
title: "INF0.2 - Arkusz kalkulacyjny (Excel / LibreOffice Calc)"
---
# INF0.2 - Arkusz kalkulacyjny (Excel / LibreOffice Calc)

> **Powiązane notatki:**
> - [Diagnostyka podzespołów (Linux)](./linux/diagnostyka.md) — dane do harmonogramu
> - [Zarządzanie użytkownikami (Windows 10)](./windows/uzytkownicy.md) — dane do kosztorysu

### 1. Podstawowe formuły
| Zadanie | Formuła | Opis |
|---------|---------|------|
| Suma | `=SUMA(A1:A10)` | Sumuje wartości z zakresu |
| Średnia | `=ŚREDNIA(A1:A10)` | Oblicza średnią |
| Iloczyn | `=ILOCZYN(A1;B1)` | Mnoży wartości z komórek |
| Maksimum | `=MAX(A1:A10)` | Największa wartość |
| Minimum | `=MIN(A1:A10)` | Najmniejsza wartość |
| Warunek | `=JEŻELI(A1>0;"Tak";"Nie")` | Jeśli warunek spełniony, zwraca pierwszą wartość, jeśli nie — drugą |

### 2. Harmonogram prac (suma czasu)
Na egzaminie często pojawia się zadanie z harmonogramem — oblicz łączny czas prac:

1. W kolumnie wpisz czasy trwania poszczególnych zadań (np. `1:30`, `0:45`, `2:00`)
2. W komórce podsumowania wpisz: `=SUMA(B2:B10)`
3. **Formatowanie czasu** — jeśli suma przekracza 24h, kliknij PPM na komórkę sumy > Formatuj komórki > Liczby > Niestandardowe > Wpisz: `[g]:mm` (nawias kwadratowy zapobiega resetowaniu po 24h)

### 3. Kosztorys (kwoty brutto)
Typowe zadanie: tabela z usługami, stawką VAT, ceną netto i brutto:

| Usługa | Ilość | Cena netto | VAT | Brutto |
|--------|-------|------------|-----|--------|
| Montaż | 2 | 100 | 23% | `=C2*(1+D2)` |
| Konfiguracja | 1 | 150 | 23% | `=C3*(1+D3)` |
| **SUMA** | | | | `=SUMA(E2:E3)` |

**VAT jako ułamek:** jeśli VAT jest wpisany jako `23%`, arkusz traktuje go jako `0,23`. Formuła: `cena_netto * (1 + VAT)`.

### 4. Formatowanie warunkowe
Formatowanie warunkowe zmienia kolor/tło komórki w zależności od jej wartości:

1. Zaznacz komórki, które chcesz sformatować
2. **Strona główna > Formatowanie warunkowe > Nowa reguła**
3. Wybierz typ reguły:
   - **Komórka jest większa niż** → wpisz wartość → wybierz format (np. czerwone tło)
   - **Komórka jest mniejsza niż** → analogicznie
   - **Formuła** → wpisz formułę (np. `=E2>1000`) → wybierz format
4. Kliknij **OK**

Typowe zastosowanie na egzaminie:
- **Czerwone tło** jeśli łączny czas pracy przekracza 8h
- **Zielone tło** jeśli koszt jest poniżej budżetu
- **Pogrubienie** jeśli wartość jest najwyższa w kolumnie

### 5. Sprawdzanie brakujących danych (JEŻELI)
Na egzaminie może pojawić się formuła weryfikująca, czy wszystkie pola są wypełnione:

```
=JEŻELI(CZYSTA.PUSTA(A2);"Brak danych";A2)
```

Lub prostszy wariant — sprawdzenie czy ilość jest wpisana:
```
=JEŻELI(B2=0;"Uzupełnij ilość";B2*C2*(1+D2))
```

### 6. Zapisywanie pliku
Na egzaminie **zawsze zapisz plik w miejscu podanym w zadaniu** (zazwyczaj pendrive lub konkretny folder):
- **Plik > Zapisz jako** → wskaż lokalizację → wpisz nazwę pliku (np. `harmonogram.xlsx`)

Nazwy plików i lokalizacje są **ściśle określone** w zadaniu egzaminacyjnym — nie zmieniaj ich.
