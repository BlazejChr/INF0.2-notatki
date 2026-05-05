---
title: "INF0.2 - FTP (IIS)"
---
# INF0.2 - FTP (IIS)

> **Powiązane notatki:**
> - [WWW (IIS)](./iis.md) — instalacja FTP jako usługa roli WWW
> - [Zarządzanie użytkownikami (Windows 10)](./uzytkownicy.md) — tworzenie kont użytkowników

### 1. Instalacja
FTP instalujemy wraz z serwerem **WWW** w opcjach **„Usługi ról” wybieramy FTP**

### 2. Konfiguracja
Tak samo jak w WWW **tworzymy osobny folder do udostępniania plików** w **C:/inetpub**
Zmieniamy w nim uprawnienia tak, aby zwykły użytkownik mógł tworzyć w nim pliki. Tworzymy w nim przykładowy plik TXT

### 3. Dodanie nowej witryny FTP
**Menadżer serwera > Narzędzia > Menadżer internetowych usług informacyjnych**

Aby dodać nową witrynę FTP klikamy:
**PPM > Dodaj witrynę FTP**

Tak samo jak w WWW **wybieramy ścieżkę do folderu z plikiem**

Następnie wybieramy adres IP, jeśli mamy dwie karty sieciowe wybieramy **jakikolwiek**

### 4. Logowanie do FTP na stacji roboczej (Anonymous)
Do serwera FTP na stacji roboczej możemy dostać się jedynie za pomocą CMD:
**ftp nazwa_serwera_FTP**

Gdy pobierzemy plik (za pomocą get) to będzie on w naszym folderze użytkownika. Umieścić plik możemy za pomocą komendy put.

### 5. Logowanie uwierzytelnione
Aby zmienić ustawienia FTP z logowania użytkownika anonimowego na użytkownika **uwierzytelnionego** należy:

**Witryna FTP > Uwierzytelnianie > PPM (na uwierzytelnianie anonimowe) > Wyłącz**

I analogicznie

**PPM (na uwierzytelnianie podstawowe) > Włącz**

Następnie:

**Reguły autoryzacji FTP > Usuwamy starą regułę > Dodaj regułę zezwalaj**

Możemy użyć zarówno użytkowników lokalnych, jak i domenowych (o ile serwer jest kontrolerem domeny).

**Określeni użytkownicy > Wybieramy użytkownika (Administrator lub inny) > Odczyt i Zapis**

**Uruchamiamy ponownie** witrynę FTP
