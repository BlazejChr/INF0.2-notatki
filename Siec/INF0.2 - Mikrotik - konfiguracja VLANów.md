---
title: "INF0.2 - Mikrotik - konfiguracja VLANów"
---
# INF0.2 - Mikrotik - konfiguracja VLANów

> **Powiązane notatki:**
> - [Podstawowa konfiguracja Mikrotik](./INF0.2%20-%20Mikrotik%20-%20podstawowa%20konfiguracja%20%28IP%20dla%20LAN,%20WAN,%20serwer%20DHCP%29.md) — DHCP, IP, trasa domyślna
> - [Switch TP-Link](./INF0.2%20-%20Switch%20%28TP%20LINK%20SG%202008%29.md) — VLANy na switchu

Konfiguracja VLAN'ów na urządzeniach Łotewskiej firmy MikroTik bardzo różni się od konfiguracji na zwykłych routerach

### 1. Tworzenie nowego Bridge'a
**Bridge > +**

### 2. Tworzenie interfejsu VLAN'ów
**Interfaces > VLAN > Interface (zaznaczamy bridge który stworzyliśmy wcześniej)**

### 3. Tworzenie IP odpowiednim VLAN'om
**IP > Addresses > +**

Tutaj ustawiamy IP tak samo jak w przypadku WAN czy LAN, jedyną zmianą jest to że w zakładce "interface" wybieramy odpowiedni, wcześniej przez nas utworzony VLAN

### 4. Konfiguracja interfejsów
**Bridge > Ports > +**

Dla każdego portu który ma być **untagged** (np. port do komputera końcowego) należy ustawić **PVID** na numer odpowiedniego VLANu. Bez tego port untagged nie będzie wiedział do którego VLANu przypisać ruch i urządzenie nie dostanie adresu IP.

**Bridge > Ports > 2xLPM (na port) > PVID (wpisujemy numer VLANu)**

### 5. Dodanie logiki naszym VLAN'om na Bridge'u
**Bridge > VLANs > +**

W tym miejscu wybieramy które porty mają być tagowane a które nie

### 6. Filtrowanie VLAN
**Bridge > 2xLPM > VLAN > VLAN Filtering (zaznaczamy)**
