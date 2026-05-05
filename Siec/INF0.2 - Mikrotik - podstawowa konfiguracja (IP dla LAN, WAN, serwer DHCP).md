---
title: "INF0.2 - Mikrotik - podstawowa konfiguracja (IP dla LAN, WAN, serwer DHCP)"
---
# INF0.2 - Mikrotik - podstawowa konfiguracja (IP dla LAN, WAN, serwer DHCP)

> **Powiązane notatki:**
> - [Konfiguracja VLANów na Mikrotik](./INF0.2%20-%20Mikrotik%20-%20konfiguracja%20VLAN%C3%B3w.md) — segmentacja sieci
> - [Switch TP-Link](./INF0.2%20-%20Switch%20%28TP%20LINK%20SG%202008%29.md) — VLANy na switchu

Konfiguracja urządzenia Mikrotik pokazana w tym dokumencie będzie robiona w programie WinBox.

### 1. Konfiguracja statycznego adresu IP dla LAN

#### Zmiana nazwy interfejsu
**Interfaces > 2xLPM (ether2 - domyślnie) > LAN**

Interfejs LAN poznamy po tym że będziemy widzieć jego "przesył", dlatego że jesteśmy do niego podłączeni.

#### Dodanie adresów do interface'ów
**IP > Adresses > + > Adres IP (wpisujemy) > Interface: LAN**

W taki sam sposób konfigurujemy WAN, zmieniając tylko Interface na WAN

### 2. Konfiguracja serwera DHCP
**IP > DHCP Server > DHCP Setup**
**LAN > Adres sieci (wpisujemy) > Brama domyślna (IP routera)**

### 3. Konfiguracja bramy domyślnej interfejsu
**IP > Routes > +**

Destination address zostawiamy na 0.0.0.0/0 a w polu „Gateway” wpisujemy podany adres bramy domyślnej, nie wybieramy interfejsu ponieważ doda się on domyślnie
