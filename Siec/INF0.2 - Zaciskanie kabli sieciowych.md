---
title: "INF0.2 - Zaciskanie kabli sieciowych"
---
# INF0.2 - Zaciskanie kabli sieciowych

> **Powiązane notatki:**
> - [Mikrotik - podstawowa konfiguracja](./INF0.2%20-%20Mikrotik%20-%20podstawowa%20konfiguracja%20%28IP%20dla%20LAN,%20WAN,%20serwer%20DHCP%29.md) — router i konfiguracja sieci
> - [Switch (TP LINK SG 2008)](./INF0.2%20-%20Switch%20%28TP%20LINK%20SG%202008%29.md) — przełącznik w sieci

### 1. Standardy okablowania
Kabel U/UTP (skrętka) składa się z 4 par przewodów (8 żył). Na egzaminie stosujemy standard **T568B** (rzadziej T568A).

#### T568B (najczęściej używany)
Od lewej do prawej (zatrzask złącza 8P8C na dole):

| Pin | Kolor |
|-----|-------|
| 1 | biało-pomarańczowy |
| 2 | pomarańczowy |
| 3 | biało-zielony |
| 4 | niebieski |
| 5 | biało-niebieski |
| 6 | zielony |
| 7 | biało-brązowy |
| 8 | brązowy |

#### T568A
Różni się zamianą par pomarańczowej i zielonej:

| Pin | Kolor |
|-----|-------|
| 1 | biało-zielony |
| 2 | zielony |
| 3 | biało-pomarańczowy |
| 4 | niebieski |
| 5 | biało-niebieski |
| 6 | pomarańczowy |
| 7 | biało-brązowy |
| 8 | brązowy |

### 2. Typy kabli
- **Kabel prosty** — oba końce w tym samym standardzie (T568B ↔ T568B)
  - PC ↔ switch, PC ↔ router, router ↔ switch
- **Kabel skrosowany (crossover)** — jeden koniec T568B, drugi T568A
  - PC ↔ PC, switch ↔ switch, router ↔ router
  - W praktyce współczesne urządzenia z Auto-MDI/MDIX radzą sobie z każdym kablem

### 3. Zaciskanie kabla — krok po kroku
1. **Zdejmij izolację** — użyj narzędzia do zdejmowania izolacji (~2-3 cm)
2. **Rozpleć i wyprostuj** żyły
3. **Ułóż w kolejności** zgodnej z wybranym standardem (T568B)
4. **Przetnij** żyły na równą długość (~1 cm wystających przewodów)
5. **Włóż do wtyku 8P8C (RJ-45)** — zatrzask na dole, piny od lewej, każdy przewód musi sięgać końca wtyku
6. **Zaciśnij** zaciskarką — piny przebijają izolację i stykają się z przewodami
7. **Sprawdź testerem** — diody na testerze zapalają się po kolei (1-8) na obu końcach

### 4. Podłączanie do panelu krosowego
Panel krosowy ma wyprowadzone pary przewodów zgodnie z kolorami (oznaczenia A/B):

1. **Zdejmij izolację** z kabla (~3-4 cm)
2. **Rozpleć żyły** i ułóż zgodnie z oznaczeniem **B** (T568B) na panelu
3. **Włóż żyły w szczeliny** — każda w kolorowe oznaczenie
4. **Dopchnij narzędziem** (impact tool) lub zamknij pokrywę modułu — noże w panelu przebijają izolację
5. **Odetnij wystające końce** przewodów
6. **Podłącz patchcordem** do switcha

### 5. Testowanie
Użyj testera kabli:
- Podłącz oba końce kabla do testera (główny + zdalny moduł)
- Włącz tester — diody **1-8 powinny zapalać się po kolei** na obu modułach
- Jeśli któraś dioda się nie zapala lub zapala się w złej kolejności — kabel jest źle zaciśnięty

### 6. Kategorie kabli
| Kategoria | Przepustowość | Zastosowanie |
|-----------|--------------|--------------|
| Cat 5e | 1 Gb/s (100 m) | Najczęściej używana na egzaminie |
| Cat 6 | 1 Gb/s (100 m) / 10 Gb/s (55 m) | Nowe instalacje |
| Cat 6a | 10 Gb/s (100 m) | Wysokie przepustowości |
| Cat 7 | 10 Gb/s (100 m) | Ekranowany, rzadziej spotykany |

Na egzaminie wystarczy znać **Cat 5e** i **Cat 6**.
