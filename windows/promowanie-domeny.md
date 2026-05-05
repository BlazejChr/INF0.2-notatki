---
title: "INF0.2 - Promowanie serwera do roli kontrolera domeny"
---
# INF0.2 - Promowanie serwera do roli kontrolera domeny

> **Powiązane notatki:**
> - [Instalowanie Active Directory](./active-directory.md) — instalacja roli AD DS
> - [Zarządzanie użytkownikami domenowymi](./uzytkownicy-domenowi.md) — zarządzanie po utworzeniu domeny
> - [NIC Teaming](./nic-teaming.md) — łączenie kart sieciowych na serwerze

### 1. Co to domena?
Domena to usługa pozwalająca na korzystanie z komputerów i innych urządzeń w ramach jednego środowiska

### 2. Co to drzewo?
Drzewo to grupa domen połączonych ze sobą w ramach logicznego schematu

### 3. Co to las?
Las to struktura pozwalająca na organizację wielu drzew w jednym miejscu

### 4. Co to kontroler domeny?
Kontroler domeny to serwer zarządzający pracą domeny, to na nim będą zapisywane informacje dotyczące użytkowników i komputerów. Posiadanie kontrolera domeny jest obowiązkowe w każdej domenie

### 5. Instalowanie
Kontroler domeny NIE MOŻE MIEĆ ADRESU POBIERANEGO Z DHCP, musi mieć adres statyczny

**Klikamy flagę > Promuj ten serwer do roli kontrolera domeny**
**Dodaj nowy las > dodajemy nazwę domeny**
**Zainstaluj**

Po zainstalowaniu wyłączamy zaporę sieci, aby nie przeszkadzała w łączeniu ze stacją roboczą
