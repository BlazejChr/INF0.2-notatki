---
title: "INF0.2 - NIC Teaming (Windows Server)"
---
# INF0.2 - NIC Teaming (Windows Server)

> **Powiązane notatki:**
> - [Konfiguracja interfejsów sieciowych (Windows 10)](./konfiguracja-sieci.md) — konfiguracja pojedynczych interfejsów
> - [Promowanie serwera do roli kontrolera domeny](./promowanie-domeny.md) — konfiguracja serwera przed AD

### 1. Co to NIC Teaming?
NIC Teaming (zwany też LBFO — Load Balancing and Failover) pozwala połączyć wiele kart sieciowych w jeden logiczny interfejs. Zapewnia to:
- **Równoważenie obciążenia** (Load Balancing) — ruch jest rozkładany na wszystkie karty
- **Tolerancję błędów** (Failover) — jeśli jedna karta padnie, pozostałe przejmują ruch

### 2. Tworzenie zespołu kart (GUI)
**Menadżer serwera > Serwer lokalny > NIC Teaming > Zadania > Utwórz nowy zespół**

1. Zaznacz karty, które chcesz połączyć
2. **Nazwa zespołu** — wpisz własną nazwę (np. `LAN12`)
3. **Tryb teamingu** — wybierz:
   - **Przełącznik niezależny** (Switch Independent) — switch nie musi wiedzieć o teamingu (najczęstszy wybór na egzaminie)
   - **Przełącznik zależny** (Switch Dependent) — switch musi być skonfigurowany (LAG/802.3ad)
4. **Tryb równoważenia obciążenia** — wybierz:
   - **Adres dynamiczny** (Dynamic) — rozkładanie na podstawie adresu IP i portu TCP/UDP (zalecany)
   - **Adres hiperportowy** (Hyper-V Port) — dla wirtualizacji
   - **Adres MAC** — rozkładanie na podstawie adresu MAC
5. Kliknij **OK**

### 3. Konfiguracja adresu IP zespołu
Po utworzeniu zespołu pojawia się nowy interfejs sieciowy w **Połączenia sieciowe**. Konfigurujemy go jak zwykły interfejs:
**PPM (na zespół) > Właściwości > Protokół internetowy w wersji 4 (TCP/IPv4) > Ustaw statyczne IP**

### 4. NIC Teaming z wiersza poleceń (PowerShell)
Wyświetlenie dostępnych interfejsów:
```powershell
Get-NetAdapter
```

Utworzenie zespołu:
```powershell
New-NetLbfoTeam -Name "LAN12" -TeamMembers "Ethernet","Ethernet 2" -TeamingMode SwitchIndependent -LoadBalancingAlgorithm Dynamic
```

Sprawdzenie statusu zespołu:
```powershell
Get-NetLbfoTeam
```

Usunięcie zespołu:
```powershell
Remove-NetLbfoTeam -Name "LAN12"
```

### 5. Ważne uwagi
- Na egzaminie najczęściej używaj trybu **Switch Independent** z równoważeniem **Dynamic**
- Po utworzeniu zespołu oryginalne interfejsy znikają z widoku — pracujesz tylko na interfejsie zespołowym
- Adres IP konfigurujesz na zespole, nie na poszczególnych kartach
- Minimalnie 2 karty sieciowe są potrzebne do utworzenia zespołu
