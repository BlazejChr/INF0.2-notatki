---
title: "INF0.2 - Domenowe zasady grupy (GPO)"
---
# INF0.2 - Domenowe zasady grupy (GPO)

> **Powiązane notatki:**
> - [Lokalne zasady grupy (Windows 10)](./gpo-lokalne.md) — GPO dla pojedynczego komputera
> - [Zarządzanie użytkownikami domenowymi](./uzytkownicy-domenowi.md) — OU i grupy zabezpieczeń

### 1. Dodanie domenowych zasad grupy
Aby dodać domenową zasadę grupy należy:
**Narzędzia > Zarządzanie zasadami grupy > Rozwijamy domenę > Wybieramy do jakiej OU chcemy dodać zasadę**

(Zasady grup dodajemy do jednostek organizacyjnych)

**PPM (na OU) > Utwórz obiekt zasad grupy w tej domenie**

### 2. Edytowanie domenowych zasad grupy
Aby edytować te zasady, klikamy na nie **PPM > Edytuj**

### 3. Zakładki
- **Zakładka "Konfiguracja komputera"** — dotyczy tylko stacji roboczych w jednostce organizacyjnej
- **Zakładka "Konfiguracja użytkownika"** — dotyczy tylko użytkowników

### 4. Kolejność przetwarzania GPO
GPO przetwarzane są w kolejności LSDOU:
1. **L**ocal (zasady lokalne)
2. **S**ite (zasady witryny)
3. **D**omain (zasady domeny)
4. **O**U (zasady jednostki organizacyjnej)

Każda kolejna zasada nadpisuje poprzednie (chyba że ustawiono "Wymuś" / Enforced).
