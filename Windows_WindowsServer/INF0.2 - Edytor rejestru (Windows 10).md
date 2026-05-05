---
title: "INF0.2 - Edytor rejestru"
---
# INF0.2 - Edytor rejestru

### 1. Co to rejestr systemowy?
Rejestr systemowy pozwala na przechowywanie informacji do których system często wraca lub zasad według których działa

### 2. Konfiguracja
Aby do niego wejść wpisujemy "Edytor rejestru" w pasku wyszukiwania Windows

Po jego otwarciu zobaczymy pare różnych folderów, nas obchodzą tylko 3:
- `HKEY_LOCAL_MACHINE` - przechowuje ustawienia dotyczące naszego komputera
- `HKEY_CURRENT_USER` - zawiera ustawienia dotyczące obecnie zalogowanego użytkownika
- `HKEY_USERS` - posiada informacje do wszystkich użytkowników

Aby edytować klucz rejestru należy:
**2xLPM > Wpisujemy wartość**

### 3. Eksport
Jeśli chcemy wyeksportować dany klucz (jeden folder w tym edytorze):
**PPM (na folder) > Eksportuj**

Aby wyeksportować cały rejestr:
**Plik > Eksportuj**
