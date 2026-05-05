---
title: "INF0.2 - FTP (vsftpd)"
---
# INF0.2 - FTP (vsftpd)

> **Powiązane notatki:**
> - [Użytkownicy i grupy](./uzytkownicy.md) — tworzenie użytkowników systemowych
> - [Uprawnienia](./uprawnienia.md) — ustawianie uprawnień do katalogów

### 1. Instalacja
```bash
sudo apt install vsftpd
```

### 2. Kopia zapasowa oryginalnego pliku konfiguracyjnego
```bash
sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.old
```

### 3. Konfiguracja dla użytkownika anonimowego
Tworzymy katalog i ustawiamy uprawnienia:
```bash
sudo mkdir -p /srv/ftp/pliki
sudo chmod 755 /srv/ftp/pliki
```

Edycja konfiguracji:
```bash
sudo nano /etc/vsftpd.conf
```

Upewnij się, że te opcje są ustawione:
```ini
anonymous_enable=YES
write_enable=YES
anon_upload_enable=YES
anon_mkdir_write_enable=YES
anon_root=/srv/ftp
```

Restart usługi:
```bash
sudo systemctl restart vsftpd
```

### 4. Połączenie z FTP jako użytkownik anonimowy
```bash
ftp 192.168.19.1
```
- Login: `anonymous`
- Hasło: (puste lub dowolny email)

### 5. Konfiguracja dla użytkowników autoryzowanych

> **Ważne:** Użytkownik musi najpierw istnieć jako użytkownik systemowy (`sudo adduser nazwa_uzytkownika`). Logowanie odbywa się przy użyciu hasła systemowego — nie ma osobnego hasła FTP.

Edycja konfiguracji:
```bash
sudo nano /etc/vsftpd.conf
```

```ini
write_enable=YES
local_enable=YES
chroot_local_user=YES
allow_writeable_chroot=YES
```

> **Uwaga:** `allow_writeable_chroot=YES` pozwala na zapis w katalogu domowym użytkownika mimo chroot. Jest to potencjalne zagrożenie bezpieczeństwa — w środowisku produkcyjnym lepiej stworzyć podkatalog z zapisem (np. `~/upload`) z uprawnieniami do zapisu, a katalog domowy pozostawić tylko do odczytu.

Restart usługi:
```bash
sudo systemctl restart vsftpd
```

### 6. Połączenie jako użytkownik autoryzowany
```bash
ftp 192.168.19.1
```
- Login: `nazwa_uzytkownika`
- Hasło: hasło użytkownika systemowego

### 7. Firewall — otwarcie portów FTP
FTP używa portów 20 (dane) i 21 (sterowanie). Otwórz je w zaporze:
```bash
sudo ufw allow 20/tcp
sudo ufw allow 21/tcp
sudo ufw reload
```
