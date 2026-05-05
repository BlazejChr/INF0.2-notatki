---
title: "INF0.2 - Serwer plików i tworzenie udziałów"
---
# INF0.2 - Serwer plików i tworzenie udziałów

> **Powiązane notatki:**
> - [Zarządzanie użytkownikami domenowymi](./INF0.2%20-%20Zarz%C4%85dzanie%20u%C5%BCytkownikami%20domenowymi%3B%20jednostki%20organizacyjne,%20grupy%20zabezpiecze%C5%84%20%28Windows%20Serwer%29.md) — uprawnienia NTFS i udziały
> - [Przyłączanie stacji roboczej do domeny](./INF0.2%20-%20Przy%C5%82%C4%85czanie%20stacji%20roboczej%20do%20domeny%20%28Windows%20Serwer%29.md) — dostęp z poziomu klienta

### 1. Instalacja
**Zarządzaj > Dodaj nowe role i funkcje > Usługi plików i magazynowania > Menadżer zasobów serwera plików**

### 2. Tworzenie udziału
Aby stworzyć nowy udział:
**Tworzymy nowy folder > Usługi plików i magazynowania (po lewej w menadżerze serwera) > Udziały > PPM > Nowy udział > Udział SMB - szybkie > Wpisz ścieżkę niestandardową (wybierasz folder)**

Na stacji roboczej możemy otworzyć ten folder za pomocą eksploratora plików wpisując w nim:

`\\domena.local\nazwa_folderu`
