---
title: "INF0.2 - DNS (Windows Server)"
---
# INF0.2 - DNS (Windows Server)

> **Powiązane notatki:**
> - [Promowanie serwera do roli kontrolera domeny](./promowanie-domeny.md) — DNS instaluje się razem z AD DS
> - [DHCP](./dhcp-windows.md) — przydzielanie adresów IP

Serwer DNS instaluje się w chwili promowania serwera do kontrolera domeny.

### 1. Instalacja
**Narzędzia > DNS**

### 2. Konfiguracja
Mamy tutaj możliwość stworzenia strefy wyszukiwania w przód, która odpowiada za zamianę słownej nazwy domeny na adres IP.

Strefa wyszukiwania w tył robi to samo ale na odwrót, zamienia adres IP na nazwę słowną

#### Wyszukiwanie w przód
Aby stworzyć nową stronę wyszukiwania w przód należy:
**PPM (Strefy wyszukiwania do przodu) > Nowa strefa > Podajemy adres po którym mamy wyszukiwać**

Po utworzeniu nowej strefy musimy stworzyć nowego wirtualnego hosta aby móc pingować serwer za pomocą nazwy a nie IP

**PPM (Na nową strefę wyszukiwania jako podfolder) > Nowy host**

Adres IP to jest adres naszego serwera, nazwą może być po prostu „serwer”

#### Wyszukiwanie w tył
Strefę wyszukiwania w wstecz tworzymy analogicznie
**PPM (Strefy wyszukiwania w wstecz > Nowa strefa > Identyfikator sieci (Tutaj podajemy pierwsze 3 oktety naszego serwera)**

Aby przetestować działanie tej strefy musimy dodać wskaźnik PTR na adres serwera

**PPM (Na nową strefę wyszukiwania wstecznego) > Nowy wskaźnik (PTR) > W adresie IP hosta podajemy adres IP serwera**

**Nazwa hosta > DESKTOP (nazwa komputera) > Strefy wyszukiwania... > Nazwa (ze strefy wyszukiwania w przód) > Serwer**

### 3. Sprawdzenie działania
Na stacji roboczej (stacja musi mieć ustawiony DNS na adres naszego serwera):

Dla wyszukiwania w przód:
```bash
ping serwer.zszz.local
```

Dla wyszukiwania w tył (odpytanie o nazwę na podstawie IP):
```bash
nslookup 192.168.19.1
```

nslookup automatycznie wykona zapytanie PTR do strefy wstecznej.
