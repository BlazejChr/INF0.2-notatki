---
title: "INF0.2 - Lokalne zasady grupy"
---
# INF0.2 - Lokalne zasady grupy

> **Powiązane notatki:**
> - [Domenowe zasady grupy (GPO)](./INF0.2%20-%20Domenowe%20zasady%20grupy%20%28GPO%29%20%28Windows%20Serwer%29.md) — GPO dla całej domeny
> - [MMC i przystawki](./INF0.2%20-%20MMC%20%28Microsoft%20Management%20Console%29%20i%20przystawki%20%28Windows%2010%29.md) — tworzenie własnych konsoli

### 1. Czym są zasady grupy
Zasady grupy to reguły określane przez system według których musi poruszać się użytkownik. Innymi słowy, są to pewne przepisy, których musi przestrzegać user lokalnie lub w domenie.

### 2. Podział zasad grupy
Istnieją dwa rodzaje zasad grupy:
1. Lokalne — dotyczą wyłącznie komputera i użytkowników lokalnych
2. Domenowe — dotyczą wszystkich komputerów w domenie i użytkowników domenowych

### 3. Konfiguracja
Aby wejść w edytor zasad grupy należy:
**Win + R > gpedit.msc**

Zakładka "Konfiguracja komputera" dotyczy całego komputera (wszyscy użytkownicy).
Zakładka "Konfiguracja użytkownika" dotyczy tylko zalogowanego użytkownika.

### 4. Polityka haseł
Aby zmienić politykę haseł musimy wejść w:
**Konfiguracja komputera > Ustawienia systemu Windows > Ustawienia zabezpieczeń > Zasady konta > Zasady haseł**

### 5. Blokowanie dostępu i prawa użytkowników
**Konfiguracja użytkownika > Szablony administracyjne**

Tutaj pomimo tego że jesteśmy administratorem, nakładają się na nas zasady grupy. Jak tego uniknąć i konfigurować ustawienia tylko jednego użytkownika? Możemy skorzystać z MMC:

**Plik > Dodaj / Usuń przystawkę > Edytor obiektów zasad grupy > Przeglądaj > Użytkownicy**

I teraz po rozwinięciu folderu z nazwą wybranego użytkownika możemy edytować jego uprawnienia bez skutków dla innych użytkowników.

Aby zablokować dostęp do określonych aplikacji musimy:
**Konfiguracja użytkownika > System > Nie uruchamiaj określonych aplikacji systemu Windows (po prawo).**
