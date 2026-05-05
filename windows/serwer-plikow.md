---
title: "INF0.2 - Serwer plików i tworzenie udziałów"
---
# INF0.2 - Serwer plików i tworzenie udziałów

> **Powiązane notatki:**
> - [Zarządzanie użytkownikami domenowymi](./uzytkownicy-domenowi.md) — uprawnienia NTFS i udziały
> - [Przyłączanie stacji roboczej do domeny](./dolaczenie-do-domeny.md) — dostęp z poziomu klienta

### 1. Instalacja
**Zarządzaj > Dodaj nowe role i funkcje > Usługi plików i magazynowania > Menadżer zasobów serwera plików**

### 2. Tworzenie udziału
Aby stworzyć nowy udział:
**Tworzymy nowy folder > Usługi plików i magazynowania (po lewej w menadżerze serwera) > Udziały > PPM > Nowy udział > Udział SMB - szybkie > Wpisz ścieżkę niestandardową (wybierasz folder)**

Na stacji roboczej możemy otworzyć ten folder za pomocą eksploratora plików wpisując w nim:

`\\domena.local\nazwa_folderu`
