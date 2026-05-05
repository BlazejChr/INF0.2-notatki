---
title: "INF0.2 - DHCP (Windows Server)"
---
# INF0.2 - DHCP (Windows Server)

> **Powiązane notatki:**
> - [DNS (Windows Server)](./INF0.2%20-%20DNS%20%28Windows%20Server%29.md) — serwery DNS przydzielane klientom
> - [Routing i dostęp zdalny (NAT)](./INF0.2%20-%20Routing%20i%20dost%C4%99p%20zdalny%20%28NAT%29%20%28Windows%20Serwer%29.md) — współdzielenie internetu

Serwer DHCP odpowiada za przydzielanie IP hostom z danej podsieci, które są do niego podłączone.

> **Ważne:** Serwer DHCP musi mieć **statyczny adres IP** — nie może go pobierać z DHCP. Ustaw go przed instalacją roli.

### 1. Instalacja
**Zarządzaj > Dodaj role i funkcje > Serwer DHCP**

### 2. Autoryzacja serwera DHCP
W środowisku domenowym serwer DHCP musi być **autoryzowany w Active Directory**, inaczej nie będzie działał. Po instalacji pojawi się powiadomienie — kliknij:

**Flaga > Dokończ konfigurację funkcji DHCP > Autoryzuj**

Jeśli serwer nie jest kontrolerem domeny, autoryzacja wymaga uprawnień administratora domeny.

### 3. Konfiguracja zakresu
**Narzędzia > DHCP > Rozwijamy serwer > IPv4 > PPM > Nowy zakres**

Uruchomi się "Kreator nowych zakresów", w którym konfigurujemy:
- Nazwę zakresu
- Zakres adresów IP (od-do)
- Długość maski podsieci
- Adresy wykluczone (jeśli potrzebne)
- Czas dzierżawy
- Opcje: bramę domyślną (router), serwer DNS

### 4. Rezerwacja adresu
Aby zarezerwować stały adres IP dla danego komputera:

**DHCP > IPv4 > Zastrzeżenia > PPM > Nowe zastrzeżenia**

Wypełniamy:
- Nazwa — dowolna opisowa nazwa
- Adres IP — adres do zarezerwowania
- Adres MAC — adres karty sieciowej urządzenia
