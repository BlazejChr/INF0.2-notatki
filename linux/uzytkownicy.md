---
title: "INF0.2 - Zarządzanie użytkownikami i grupami"
---
# INF0.2 - Zarządzanie użytkownikami i grupami

> **Powiązane notatki:**
> - [Uprawnienia](./uprawnienia.md) — ustawianie uprawnień plików
> - [Samba](./samba.md) — konta Samba bazują na użytkownikach systemowych

### 1. Zarządzanie użytkownikiem
- `sudo adduser nazwa_uzytkownika` — dodanie nowego użytkownika (interaktywnie, z pytaniem o hasło i dane)
- `sudo deluser nazwa_uzytkownika` — usunięcie użytkownika (bez kasowania katalogu domowego)
- `sudo deluser --remove-home nazwa_uzytkownika` — usunięcie użytkownika wraz z katalogiem domowym
- `sudo adduser --home /sciezka nazwa_uzytkownika` — ustawienie niestandardowego katalogu domowego
- `sudo adduser --uid numer nazwa_uzytkownika` — ustawienie identyfikatora użytkownika (UID)
- `sudo adduser --disabled-login nazwa_uzytkownika` — utworzenie konta bez możliwości logowania hasłem (tylko np. klucz SSH, konto usługowe)
- `sudo adduser --shell /sciezka_do_powloki nazwa_uzytkownika` — ustawienie innej powłoki (domyślnie `/bin/bash`)
- `sudo usermod -e RRRR-MM-DD nazwa_uzytkownika` — ustawienie daty wygaśnięcia konta
- `sudo passwd nazwa_uzytkownika` — zmiana hasła użytkownika
- `sudo usermod -L nazwa_uzytkownika` — zablokowanie konta
- `sudo usermod -U nazwa_uzytkownika` — odblokowanie konta

### 2. Zarządzanie grupami
- `sudo addgroup nazwa_grupy` — dodanie nowej grupy
- `sudo usermod -aG nazwa_grupy nazwa_uzytkownika` — dodanie użytkownika do grupy
- `sudo delgroup nazwa_grupy` — usunięcie grupy
- `groups nazwa_uzytkownika` — sprawdzenie w jakich grupach jest dany użytkownik
- `id nazwa_uzytkownika` — wyświetlenie UID, GID i grup użytkownika
