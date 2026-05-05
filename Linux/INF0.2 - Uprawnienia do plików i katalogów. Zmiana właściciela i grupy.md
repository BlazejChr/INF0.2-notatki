---
title: "INF0.2 - Uprawnienia do plików i katalogów. Zmiana właściciela i grupy"
---
# INF0.2 - Uprawnienia do plików i katalogów. Zmiana właściciela i grupy

> **Powiązane notatki:**
> - [Zarządzanie użytkownikami i grupami](./INF0.2%20-%20Zarz%C4%85dzanie%20u%C5%BCytkownikami%20i%20grupami.md) — tworzenie użytkowników i grup
> - [Samba](./INF0.2%20-%20Samba.md) — uprawnienia do udziałów sieciowych
> - [Foldery (Linux)](./Foldery%20%28Linux%29.md) — struktura katalogów

### 1. Wyjaśnienie teoretyczne
Każdy plik i katalog w Linux pozwala edytować uprawnienia dla 3 grup:
1. Właściciel
2. Grupa
3. Pozostali

Każdej z tych 3 grup można przypisać po 3 uprawnienia
1. r - read
2. w - write
3. x - execute

### 2. Sprawdzenie uprawnień
Aby sprawdzić uprawnienia do pliku lub katalogu stosujemy komendę:
```bash
ls -al
```


Ciąg znaków dzielimy na 3 równe części, każda odpowiadająca wymienionym wcześniej (w tej właśnie kolejności) grupom.

### 3. Edycja uprawnień do plików
Uprawnienia edytujemy za pomocą komendy "chmod".
Są dwa sposoby na zmianę uprawnień plików:

#### 1. Znakowy
Wykorzystuje litery:
```text
- u - właściciel
- g - grupa
- o - others
- a - all
oraz operatorów do dodania uprawnień
- +
- -
- =
```

#### 2. Liczbowy
Wykorzystuje 3 cyfrowy kod w którym cyferka odpowiada danemu uprawnieniu
- 1 = x(execute)
- 2 = w(rite)
- 4 = r(ead)

### 4. Zmiana właściciela oraz grupy pliku
```bash
chown nazwa_uzytkownika nazwa_pliku (change owner)
chgrp nazwa_grupy nazwa_pliku (change group)
```

### 5. Składnia
Składnia komendy wygląda tak:
```bash
chmod 777 nazwa_pliku
```

Liczby się sumują, dlatego też 7 oznacza najwyższe uprawnienia do pliku (4+2+1)
