---
title: "INF0.2 - Switch"
---
# INF0.2 - Switch

> **Powiązane notatki:**
> - [Mikrotik - konfiguracja VLANów](./INF0.2%20-%20Mikrotik%20-%20konfiguracja%20VLAN%C3%B3w.md) — VLANy na routerze
> - [Mikrotik - podstawowa konfiguracja](./INF0.2%20-%20Mikrotik%20-%20podstawowa%20konfiguracja%20%28IP%20dla%20LAN,%20WAN,%20serwer%20DHCP%29.md) — DHCP, IP, trasa domyślna
> - [Zaciskanie kabli sieciowych](./INF0.2%20-%20Zaciskanie%20kabli%20sieciowych.md) — fizyczne połączenia kablowe

Konfiguracja w tym dokumencie będzie dla urządzenia TP-LINK SG-2008, inne switche będą miały inne interfejsy, pomimo tego że dane ustawienia da się znaleźć w podobnych zakładkach

### 1. Zamiana adresu IP
**L3 Features > Interface > Edit IPv4**

**Static (IP address mode) > Wpisujemy tutaj adres i maskę podsieci**

### 2. Tworzenie VLAN
**L2 Features > VLAN > 802.1Q VLAN**
Tak jak w routerach, będzie tu już istnieć VLAN o ID 1 (systemowy)

W tym interfejsie możemy edytować istniejące VLAN'y. Wybieramy tagowane i nie tagowane porty

Aby dodać nowy VLAN klikamy "Add" i tak samo jak wcześniej, podajemy ID i konfigurujemy
