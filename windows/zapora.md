---
title: "INF0.2 - Zapora systemu Windows"
---
# INF0.2 - Zapora systemu Windows

> **Powiązane notatki:**
> - [Pulpit zdalny](./INF0.2%20-%20Pulpit%20zdalny%20%28Windows%20Serwer%29.md) — reguła RDP w zaporze
> - [Lokalne zasady grupy](./INF0.2%20-%20Lokalne%20zasady%20grupy%20%28Windows%2010%29.md) — blokowanie/zapora przez GPO

### 1. Co to zapora?
Zapora jest przydatnym narzędziem które blokuje niepożądane pakiety, niestety często nam przeszkadza w na przykład sprawdzeniu połączeń maszyn przez ping

### 2. Konfiguracja
**Zapora Windows Defender > Włącz lub wyłącz zaporę sieciową**

Aby dodać do niej nowe reguły:
**Zapora Windows Defender > Ustawienia zaawansowane**

### 3. Rodzaje reguł
Gdy wejdziemy w ustawienia zaawansowane pokażą się nam foldery z regułami. Dzielą się one na:
- Reguły przychodzące
- Reguły wychodzące

Reguły przychodzące dotyczą ruchu sieciowego który odbieramy z sieci, natomiast wychodzące które wychodzą od nas.
