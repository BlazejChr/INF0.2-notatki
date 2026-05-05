---
title: "INF0.2 - Routing i dostęp zdalny (NAT)"
---
# INF0.2 - Routing i dostęp zdalny (NAT)

> **Powiązane notatki:**
> - [DHCP (Windows Server)](./INF0.2%20-%20DHCP%20%28Windows%20Server%29.md) — przydzielanie adresów w sieci za NAT
> - [DNS (Windows Server)](./INF0.2%20-%20DNS%20%28Windows%20Server%29.md) — rozwiązywanie nazw

### 1. Instalacja
Włączamy na serwerze naszą kartę NAT
**Zmień opcje karty > PPM (na kartę sieciową) > Włącz**

**Zarządzaj > Dodaj role i funkcje > Dostęp zdalny > W "Usługi ról" zaznaczamy Routing**

### 2. Konfiguracja
Po zainstalowaniu klikamy konfigurację:

**Routing i dostęp zdalny > PPM (na serwer) > Konfiguruj i włącz routing i dostęp zdalny**

W kreatorze wybieramy: **NAT** (Nie wybieraj "Wdróż tylko sieć VPN" — to inna usługa).

Następnie konfigurujemy interfejsy:
- Interfejs **WAN** (karta zewnętrzna) — PPM > Właściwości > Zakładka NAT > zaznacz **Połączenie publiczne**
- Interfejs **LAN** (karta wewnętrzna) — PPM > Właściwości > Zakładka NAT > zaznacz **Połączenie prywatne**

### 3. Sprawdzenie działania
Na stacji edytujemy kartę sieciową i dodajemy adres z sieci IP serwera, bramą domyślną jest adres serwera. W DNS również wpisujemy adres serwera.

Aby sprawdzić działanie routingu na stacji roboczej wchodzimy w CMD i pingujemy jakąkolwiek stronę po nazwie
