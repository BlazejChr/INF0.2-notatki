---
title: "Foldery i pliki - Linux"
---
# Foldery i pliki - Linux

> **Powiązane notatki:**
> - [Uprawnienia](./INF0.2%20-%20Uprawnienia%20do%20plik%C3%B3w%20i%20katalog%C3%B3w.%20Zmiana%20w%C5%82a%C5%9Bciciela%20i%20grupy.md) — uprawnienia do katalogów
> - [Diagnostyka podzespołów](./INF0.2%20-%20Diagnostyka%20podzespo%C5%82%C3%B3w%20%28Linux%29.md) — informacje o systemie

### 1. Wstęp
Hierarchia folderów w Linux opiera się na FHS (Filesystem Hierarchy Standard). Ten standard mówi o tym jaki foldery mają być posegregowane i jakie pliki mają do nich należeć.

Hierarchia plików jest obecna na wszystkich systemach z rodziny UNIX, czyli np: MacOS

Wszystko w Linux jest plikiem, nawet komendy czy podzespoły.

### 2. Drzewo
W odróżnieniu od systemów Windows’o podobnych wszystkie foldery w Linux tworzą „drzewo” - pochodzą z folderu „root” który jest oznaczony „/”, to z niego rozchodzą się główne katalogi (Top-level directories):

- /`bin` - binarne, albo egzekwowalne programy
- /`etc` - folder plików konfiguracyjnych
- /`home` - katalog domowy, domyślny - obecny
- /`opt` - oprogramowanie opcjonalne albo oprogramowanie firm trzecich
- /`tmp` - pliki tymczasowe (tworzone przez aplikacje i użytkowników); czyszczony przy restarcie
- /`usr` - Unix System Resources; aplikacje, biblioteki współdzielone, dokumentacja — pliki dostępne dla wszystkich użytkowników
- /`var` - pliki zmienne (variable): logi (`/var/log`), kolejki wydruku, cache, bazy danych, strony www

Te foldery pomagają w funkcjonowaniu głównych procesów systemu, dostępności podzespołów i operacji na poziomie systemu w Linux

- /`boot` - pliki potrzebne do uruchomienia systemu: jądro (`vmlinuz`), initramfs (`initrd.img`), konfiguracja GRUBa (`/boot/grub/`)
- /`dev` - pliki urządzeń (urządzenia blokowe, znakowe) takie jak `/dev/sda2`, `/dev/null`, `/dev/zero`
- /`lib` - moduły kernela (`/lib/modules`) i współdzielone biblioteki systemowe (`*.so`)
- /`lost+found` - katalog używany przez fsck (sprawdzanie systemu plików) do odzyskiwania uszkodzonych fragmentów plików po awarii
- /`media` - automatyczne punkty montowania dla nośników wymiennych (pendrive, płyty CD/DVD)
- /`mnt` - ręczne punkty montowania dla tymczasowego montowania systemów plików
- /`proc` - wirtualny system plików (procfs) z informacjami o procesach (`/proc/PID`) i parametrach kernela (`/proc/sys`)
- /`run` - pliki runtime (dane procesów uruchomionych od ostatniego startu): PID, sockety; czyszczony przy restarcie (w przeciwieństwie do `/tmp` — tylko dla procesów systemowych)
- /`sbin` - binarne, wykonywalne programy dla administratora (system administration)
- /`srv` - dane serwerów udostępniane przez system (np. strony www, pliki FTP)
- /`sys` - wirtualny system plików (sysfs) — interfejs do urządzeń podłączonych do systemu i parametrów kernela
