---
title: "INF0.2 - Zabezpieczenia do folderów (dziedziczne) (ACL) (Windows 10)"
---
# INF0.2 - Zabezpieczenia do folderów (dziedziczne) (ACL) (Windows 10)

### 1. Konfiguracja (podstawowa)
**PPM (na folder) > Właściwości > Zabezpieczenia > Edytuj**
Możemy teraz wybierać konkretne uprawnienia dla konkretnych grup i użytkowników, takie jak odczyt, zapis czy wyświetlanie zawartości folderu.
Aby nadać użytkownikowi uprawnienia tylko do odczytu musimy mu najpierw wszystko zablokować, a następnie pozwolić na odczyt. Tylko wtedy to zadziała ze względu na dziedziczenie

### 2. Konfiguracja (zaawansowana)
**PPM (na folder) > Właściwości > Zabezpieczenia > Zaawansowane**
W przypadku ustawień zaawansowanych mamy o wiele więcej opcji dotyczących uprawnień, możemy przez to być bardziej skrupulatni.

**Dodaj > Uprawnienia (już tutaj jesteśmy w stanie zmienić bardzo wygodnie nasze uprawnienia)**

Teraz możemy odczytać uprawnienia dla użytkownika w zakładce "Dostęp czynny"
**Dostęp czynny > Wybierz użytkownika**

Możemy wtedy zobaczyć że pomimo dania użytkownikowi uprawnienia tylko do odczytu, on i tak może np: zapisywać. Wynika to z tego że grupa w jakiej jest nadal ma większe uprawnienia. Aby to naprawić musimy dodać zasadę odmowy:
**Dodaj > Odmów**

### 3. Szyfrowanie plików — EFS (Encrypting File System)
EFS pozwala szyfrować pojedyncze pliki i foldery na poziomie systemu plików NTFS. Tylko użytkownik, który zaszyfrował plik, może go otworzyć.

Szyfrowanie pliku:
**PPM (na plik/folder) > Właściwości > Ogólne > Zaawansowane > Szyfruj zawartość, aby zabezpieczyć dane**

Po zaszyfrowaniu plik wyświetla się z zieloną nazwą w Eksploratorze.

**Ważne:**
- EFS działa tylko na partycjach NTFS
- Jeśli zaszyfrujesz plik i skopiujesz go na partycję FAT/exFAT/USB — szyfrowanie zostanie usunięte
- Aby przenieść zaszyfrowany plik na inny komputer, trzeba najpierw wyeksportować certyfikat EFS
- Administrator może odzyskać zaszyfrowane pliki, jeśli ma skonfigurowanego agenta odzyskiwania (EFS Recovery Agent)

Kopia zapasowa certyfikatu EFS (zalecane po pierwszym zaszyfrowaniu):
**Wyszukaj `certmgr.msc` > Certyfikaty — bieżący użytkownik > Osobiste > Certyfikaty > PPM (na certyfikat EFS) > Wszystkie zadania > Eksportuj**

Aby odszyfrować plik: odznacz "Szyfruj zawartość" we właściwościach pliku (dostępne tylko dla właściciela pliku).
