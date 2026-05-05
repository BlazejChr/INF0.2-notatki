---
title: "INF0.2 - Instalowanie Active Directory"
---
# INF0.2 - Instalowanie Active Directory

> **Powiązane notatki:**
> - [Promowanie serwera do roli kontrolera domeny](./INF0.2%20-%20Promowanie%20serwera%20do%20roli%20kontrolera%20domeny%20%28Windows%20Serwer%29.md) — dalszy krok po instalacji roli
> - [DNS (Windows Server)](./INF0.2%20-%20DNS%20%28Windows%20Server%29.md) — instaluje się automatycznie z AD

### 1. Co to Active Directory?
Active Directory (AD) to usługa katalogowa Microsoftu działająca na Windows Serverze. Służy do centralnego zarządzania zasobami sieciowymi i pozwala na:
- Centralne zarządzanie użytkownikami, grupami i komputerami w domenie
- Stosowanie mechanizmów zabezpieczeń, takich jak domenowe zasady grupy (GPO)
- Autoryzację i uwierzytelnianie użytkowników w całej domenie
- Zarządzanie domeną, drzewami domen i lasami

> **Ważne:** Przed instalacją Active Directory serwer musi mieć **statyczny adres IP**. AD nie zadziała poprawnie z adresem z DHCP.

### 2. Instalacja
Aby zainstalować AD:

**Menadżer serwera > Zarządzaj > Dodaj role i funkcje > Wybieranie ról serwera > Usługi domenowe Active Directory**

Po instalacji należy jeszcze **promować serwer do kontrolera domeny** — zobacz notatkę: [Promowanie serwera do roli kontrolera domeny](./INF0.2%20-%20Promowanie%20serwera%20do%20roli%20kontrolera%20domeny%20%28Windows%20Serwer%29.md).
