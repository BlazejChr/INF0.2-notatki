---
title: "INF0.2 - Serwer WWW (Apache2)"
---
# INF0.2 - Serwer WWW (Apache2)

> **Powiązane notatki:**
> - [DNS (BIND9)](./INF0.2%20-%20DNS%20-%20nie%20dzia%C5%82a.md) — rozwiązywanie nazw wirtualnych hostów
> - [SSH](./INF0.2%20-%20SSH%20%28openssh-server%3B%20sshd%29.md) — zdalna administracja serwerem

### 1. Instalacja
```bash
sudo apt install apache2
```

### 2. Sprawdzanie zapory
```bash
sudo ufw app list
```
Jeśli będzie Apache to dobrze, jeśli nie to: `sudo ufw allow 'Apache'`

### 3. Sprawdzanie działania
Wpisz w stacji adres ip twojego serwera, powinna wyświetlić się strona Ubuntu

### 4. Tworzenie katalogów
```bash
sudo mkdir -p /var/www/informatyk.local/public_html
sudo mkdir -p /var/www/elektryk.local/public_html
```

### 5. Nadanie uprawnień (bez tego nie zadziała)
```bash
sudo chmod -R 755 /var/www/informatyk.local
sudo chmod -R 755 /var/www/elektryk.local
```

### 6. Tworzenie stron
```bash
sudo nano /var/www/informatyk.local/public_html/index.html
sudo nano /var/www/elektryk.local/public_html/index.html
```
W plikach "index.html" wpisujesz prosty kod w HTML'u z tytułem i nagłówkiem

### 7. Konfiguracja wirtualnych hostów
Apache używa plików konfiguracyjnych wirtualnych hostów do obsługi wielu domen na jednym serwerze.

Domyślny plik to `000-default.conf` znajdujący się w `/etc/apache2/sites-available/`. Użyjemy go jako szablonu.

#### Dla informatyków
`sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/informatyk.local.conf`

Najważniejsze zmiany jakie musisz wprowadzić w skopiowanym pliku to:

`ServerName` — ustaw na `informatyk.local`.

`ServerAlias` — opcjonalnie, alias dla domeny (np. `www.informatyk.local`).

`DocumentRoot` — ścieżka do katalogu z plikami strony (`/var/www/informatyk.local/public_html`).

`ErrorLog` i `CustomLog` — definiują pliki logów dla tej konkretnej witryny.

#### Dla elektryków
```bash
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/elektryk.local.conf
sudo nano /etc/apache2/sites-available/elektryk.local.conf
```

### 8. Włączenie nowych konfiguracji
```bash
sudo a2ensite informatyk.local.conf
sudo a2ensite elektryk.local.conf
sudo a2dissite 000-default.conf
```

### 9. Sprawdzenie konfiguracji Apache
`sudo apachectl configtest`

Jeśli wyskakuje błąd `Could not reliably determine the server's fully qualified domain name`, należy utworzyć:
```bash
sudo nano /etc/apache2/conf-available/servername.conf
```

i wpisać:
```text
ServerName localhost
```

Następnie:
```bash
sudo a2enconf servername
sudo systemctl reload apache2
sudo apachectl configtest
```

Powinno być bez błędu: `Syntax OK`

### 10. Ponowne uruchomienie serwera
`sudo systemctl restart apache2`

### 11. Konfigurowanie serwera (DNS lokalny)
Apache musi mieć możliwość rozwiązania nazw wirtualnych hostów. Dodajemy wpisy w `/etc/hosts` **na serwerze**:
```bash
sudo nano /etc/hosts
```

Dodajemy:
```text
192.168.19.1 informatyk.local
192.168.19.1 www.informatyk.local
192.168.19.1 elektryk.local
192.168.19.1 www.elektryk.local
```

### 12. Konfigurowanie stacji roboczej
Na stacji roboczej dodajemy te same wpisy:
```bash
sudo nano /etc/hosts
```

W ostatniej linii:
```text
192.168.1.100 informatyk.local
192.168.1.100 www.informatyk.local
192.168.1.100 elektryk.local
192.168.1.100 www.elektryk.local
```

Następnie:
```bash
sudo systemctl restart systemd-resolved.service
```

Na Windows na stacji roboczej edytujemy `C:\Windows\System32\drivers\etc\hosts` (jako Administrator).
