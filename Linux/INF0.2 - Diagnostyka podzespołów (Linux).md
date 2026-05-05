---
title: "INF0.2 - Diagnostyka podzespołów (Linux)"
---
# INF0.2 - Diagnostyka podzespołów (Linux)

> **Powiązane notatki:**
> - [Foldery (Linux)](./Foldery%20%28Linux%29.md) — struktura katalogów
> - [Zarządzanie użytkownikami i grupami](./INF0.2%20-%20Zarz%C4%85dzanie%20u%C5%BCytkownikami%20i%20grupami.md) — informacje o użytkownikach

Komendy pozwalające na diagnostykę można podzielić na dwie grupy

### 1. Informacje o systemie
- `hostnamectl` — nazwa komputera, system operacyjny, wersja jądra, architektura
- `uname -a` — dane jądra (kernel version, architektura)
- `w` — lista obecnie zalogowanych użytkowników, powłoka, czas zalogowania
- `whoami` — nazwa obecnie zalogowanego użytkownika
- `id` — identyfikator użytkownika (uid) i grupy (gid)
- `umask` — maska uprawnień
- `top` — menedżer zadań (procesy, CPU, RAM)
- `htop` — ulepszony menedżer zadań (jeśli zainstalowany)
- `du -sh /sciezka_folderu/` — rozmiar danego folderu
- `df -h` — zajętość dysków twardych (ludzko-czytelny format)
- `free -h` — zużycie pamięci RAM i swap

### 2. Informacje o podzespołach
- `sudo lshw` — szczegółowe informacje na temat wszystkich podzespołów
  - `lshw -C cpu` — zawężone informacje o CPU
  - `lshw -C memory` — zawężone informacje o pamięci (RAM)
  - `lshw -C disk` — zawężone informacje o dysku twardym
  - `lshw -C display` — zawężone informacje o karcie graficznej
  - `lshw -C network` — zawężone informacje o karcie sieciowej
- `lscpu` — informacje o CPU
- `lsblk` — lista urządzeń blokowych (dyski, partycje)
- `lspci` — lista urządzeń PCI (karty graficzne, sieciowe itp.)
- `lsusb` — lista urządzeń USB
- `sudo dmidecode -t typ` — szczegółowe informacje o sprzęcie
  - `dmidecode -t memory` — informacje o pamięci RAM
  - `dmidecode -t processor` — informacje o procesorze
  - `dmidecode -t bios` — informacje o BIOS/UEFI
  - `dmidecode -t system` — informacje o płycie głównej i systemie
  - (bez `-t` wyświetlą się opcje do wyboru)

### 3. Diagnostyka sieci
- `ip addr` — adresy IP interfejsów sieciowych
- `ip route` — tabela routingu
- `ip link` — stan interfejsów sieciowych
- `ss -tlnp` — nasłuchujące porty i usługi
- `ping adres_IP` — test połączenia
