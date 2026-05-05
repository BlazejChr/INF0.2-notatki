---
title: "INF0.2 - Samba"
---
# INF0.2 - Samba

> **Powiązane notatki:**
> - [Użytkownicy i grupy](./uzytkownicy.md) — tworzenie użytkowników systemowych
> - [Uprawnienia](./uprawnienia.md) — ustawianie uprawnień do katalogów

### 1. Instalacja
```bash
sudo apt install samba
```

### 2. Tworzenie katalogu który będzie udostępniany
```bash
sudo mkdir /srv/zasoby
sudo chmod 775 /srv/zasoby
```

> `chmod 775` jest bezpieczniejszy niż `777` — pozwala na zapis tylko właścicielowi i grupie, a innym tylko na odczyt i wykonanie.

### 3. Konfiguracja dla użytkowników anonimowych
```bash
sudo nano /etc/samba/smb.conf
```

Na końcu pliku dodajemy sekcję:
```ini
[zasoby]
    path = /srv/zasoby
    read only = no
    guest ok = yes
    browseable = yes
    writeable = yes
```

> W pliku `smb.conf` nazwa udziału w nawiasach kwadratowych `[zasoby]` zaczyna się od początku linii, a opcje konfiguracyjne powinny mieć wcięcie (dowolne spacje lub tabulatory — plik nie wymaga konkretnego odstępu).

### 4. Restart
```bash
sudo systemctl restart smbd
```

### 5. Na stacji
Wchodzimy w menadżer plików, klikamy w zakładkę "Inne położenia" i w pasku na dole wpisujemy:
- Na Windows — `\\ip_serwera\nazwa_folderu`
- Na Linux — `smb://ip_serwera/nazwa_folderu`

### 6. Konfiguracja dla użytkowników autoryzowanych

> **Ważne:** Użytkownik Samba musi najpierw istnieć jako użytkownik systemowy. Jeśli go nie ma, utwórz go: `sudo adduser nazwa_uzytkownika`

Dodanie użytkownika Samba (hasło Samba jest niezależne od hasła systemowego):
```bash
sudo smbpasswd -a nazwa_uzytkownika
```

Stworzenie katalogu:
```bash
sudo mkdir /srv/pliki
sudo chmod 775 /srv/pliki
```

Konfiguracja udziału:
```bash
sudo nano /etc/samba/smb.conf
```

```ini
[pliki]
    path = /srv/pliki
    read only = no
    guest ok = no
    valid users = nazwa_uzytkownika
    browseable = yes
    writeable = yes
```

### 7. Restart
```bash
sudo systemctl restart smbd
```

### 8. Sprawdzenie konfiguracji
```bash
testparm
```

To polecenie sprawdzi poprawność pliku `smb.conf` i wypisze ewentualne błędy.
