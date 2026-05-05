---
title: "INF0.2 - SSH (openssh-server; sshd)"
---
# INF0.2 - SSH (openssh-server; sshd)

> **Powiązane notatki:**
> - [Użytkownicy i grupy](./uzytkownicy.md) — zarządzanie kontami użytkowników
> - [Uprawnienia](./uprawnienia.md) — uprawnienia plików na serwerze

### 1. Instalacja
```bash
sudo apt install openssh-server
```

### 2. Konfiguracja
```bash
sudo nano /etc/ssh/sshd_config
```

Najważniejsze opcje:
```text
ListenAddress 192.168.19.1
```

Restart usługi:
```bash
sudo systemctl restart sshd
```

### 3. Połączenie z poziomu stacji roboczej
```bash
ssh nazwa_uzytkownika@adres_serwera
```

Jeśli serwer używa niestandardowego portu:
```bash
ssh -p numer_portu nazwa_uzytkownika@adres_serwera
```

### 4. Dodatkowa konfiguracja sshd_config
Ograniczenie dostępu do wybranych użytkowników:
```text
AllowUsers nazwa_uzytkownika1 nazwa_uzytkownika2
```

Blokada dostępu dla wybranych użytkowników:
```text
DenyUsers nazwa_uzytkownika
```

### 5. Uwierzytelnianie kluczami SSH (zalecane)
**Na stacji roboczej** generujemy parę kluczy:
```bash
ssh-keygen -t ed25519
```
(lub `ssh-keygen -t rsa -b 4096` dla starszych systemów)

**Kopiujemy klucz publiczny na serwer:**
```bash
ssh-copy-id nazwa_uzytkownika@adres_serwera
```

**Na serwerze** w `sshd_config` można wyłączyć logowanie hasłem (opcjonalnie, po upewnieniu się że klucze działają):
```text
PasswordAuthentication no
```

Restart usługi po każdej zmianie konfiguracji:
```bash
sudo systemctl restart sshd
```
