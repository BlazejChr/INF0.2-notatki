---
title: "INF0.2 - WWW (IIS)"
---
# INF0.2 - WWW (IIS)

> **Powiązane notatki:**
> - [FTP (IIS)](./INF0.2%20-%20FTP%20%28IIS%29%20%28Windows%20Serwer%29.md) — instalacja FTP jako usługa roli WWW
> - [DNS (Windows Server)](./INF0.2%20-%20DNS%20%28Windows%20Server%29.md) — rozwiązywanie nazw witryn

Dzięki IIS jesteśmy w stanie stworzyć stronę internetową i wyświetlić ją w przeglądarce na stacji roboczej.

### 1. Instalacja
**Zarządzanie > Dodaj role i funkcje > Serwer sieci WEB**

### 2. Konfiguracja
Po poprawnej instalacji usługi na naszym dysku pojawi się folder "**inetpub**" w którym znajduje się "**wwwroot**" — **domyślny folder serwera** z gotową, przykładową stroną.

**Narzędzia > Menadżer internetowych usług informacyjnych (IIS) > Rozwijamy opcję "Witryny"** — tam znajdziemy stronę.

Aby zobaczyć stronę, klikamy na nią **dwa razy LPM i wybieramy opcję "Przeglądaj"**.

### 3. Zastąpienie witryny
Aby dodać własną witrynę musimy **usunąć obecną**. **Klikamy na nią PPM > Usuń**.

Po stworzeniu swojego własnego folderu wewnątrz inetpub wraz z plikiem index.html klikamy:
**PPM (Witryny) > Dodaj witrynę sieci Web**

W "Ścieżka fizyczna" wybieramy nasz folder z plikiem i nie zmieniamy nic więcej. W polu nazwa możemy ją zmienić, żeby w IIS inaczej się wyświetlała witryna.

Aby zobaczyć stronę na stacji roboczej należy wpisać `http://nazwa_domeny.local`

### 4. Zmiana nazwy pliku
Aby zmienić nazwę pliku z index.html na jakikolwiek inny musimy **kliknąć dwa razy na naszą stronę (w Menadżerze IIS) > Dokument domyślny > Dodaj > "nowa_nazwa_pliku".html**

**Ważne: ta reguła powinna być na samej górze — wtedy ma najwyższy priorytet.**
