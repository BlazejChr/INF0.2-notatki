---
title: "INF0.2 - Diagnostyka (Windows 10)"
---
# INF0.2 - Diagnostyka (Windows 10)

> **Powiązane notatki:**
> - [Korzystanie z CMD](./INF0.2%20-%20Korzystanie%20z%20CMD%20%28Windows%2010%29.md) — narzędzia wiersza poleceń
> - [Zenmap i NMap](./INF0.2%20-%20Zenmap%20i%20NMap%20%28Windows%2010%29.md) — skanowanie sieci

Wypisane programy oraz krótki opis do wyszukania jakiej informacji służą.

### 1. Wewnętrzne narzędzia do diagnostyki systemu
Aby wejść we wszystkie narzędzia wewnętrzne wystarczy wpisać je w pasku wyszukiwania Windows:

- **System** — specyfikacja, informacje o systemie, numer kompilacji, nazwa grupy roboczej
- **Informacje o systemie** (główne narzędzie) — wersja i kompilacja systemu, producent i wersja płyty głównej, rodzaj systemu BIOS. W zakładce składniki możemy odczytać informacje na temat urządzeń, np. o karcie sieciowej
- **Menadżer urządzeń** — włączanie i wyłączanie urządzeń, odczytanie dokładnych danych urządzenia
- **Monitor wydajności** — wydajność procesora i dysku twardego, czasy bezczynności czy przerwy
- **Menadżer zadań** — procesy i ich identyfikatory, zużycie CPU/RAM/dysku

### 2. Zewnętrzne narzędzia do diagnostyki systemu
- `CPU-Z` — Procesor
- `GPU-Z` — Karta graficzna
- `CrystalDisk` — Dysk twardy
