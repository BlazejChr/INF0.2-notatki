---
title: "INF0.2 - Zarządzanie użytkownikami domenowymi; jednostki organizacyjne, grupy zabezpieczeń"
---
# INF0.2 - Zarządzanie użytkownikami domenowymi; jednostki organizacyjne, grupy zabezpieczeń

> **Powiązane notatki:**
> - [Instalowanie Active Directory](./active-directory.md) — instalacja AD
> - [Domenowe zasady grupy (GPO)](./gpo-domenowe.md) — GPO dla OU

### 1. Czym różni się użytkownik lokalny od domenowego?
**Użytkownik lokalny jest przypisany wyłącznie do jednego komputera, użytkownik domenowy jest za to przypisany do domeny**, dlatego może logować się z każdego urządzenia przypisanego do domeny (poza kontrolerem)

### 2. Dodawanie nowego użytkownika
**Menadżer serwera > Narzędzia > Użytkownicy i komputery usługi Active Directory**

**Users > PPM > Nowy > Użytkownik**

### 3. Grupy w AD
W Active Directory wyróżniamy 2 typy grup.

1. **Grupy zabezpieczeń**
2. **Grupy dystrybucyjne**

Grupy zabezpieczeń służą do zarządzania bezpieczeństwem i dostępem do zasobów komputera, pozwalają na grupowanie użytkowników według ich uprawnień, które mają dostać, np: Administratorzy, księgowi i tak dalej

Grupy dystrybucyjne służą do prostego wysyłania emaili do konkretnych grup użytkowników

Grupy zabezpieczeń mają również możliwość określenia zakresu. Wyróżniamy 3 rodzaje zakresu w grupie zabezpieczeń:
1. **Lokalna w domenie** — dostęp do zasobów lokalnych
2. **Globalne** — użytkownicy z dowolnej domeny w zakresie tego samego lasu
3. **Uniwersalne** — dostęp do dowolnego zasobu w całym lesie

### 4. Tworzenie grup lokalnych w domenie
Aby utworzyć grupę w domenie należy:
**Narzędzia > Użytkownicy i komputery usługi AD > Users (folder) > PPM > Nowy > Grupa**

### 5. Dodanie użytkownika do grupy
Aby dodać użytkownika do grupy należy:
**PPM (na użytkownika w folderze Users) > Właściwości > Członkowie > Dodaj**

### 6. Jednostki organizacyjne
Aby uporządkować wszystkich użytkowników, grupy i tak dalej na pomoc przychodzą nam jednostki organizacyjne (OU).
**Jest to kontener przechowujący użytkowników, grupy i komputery, pozwalając na wygodne pogrupowanie logicznie połączonych elementów, w porównaniu do grup, nie można jej nadać żadnych uprawnień**

### 7. Dodanie jednostki organizacyjnej

Aby dodać jednostkę organizacyjną należy:
**Narzędzia > Użytkownicy i komputery usługi AD > PPM (na domenę) > Nowy > Jednostka organizacyjna**

Żeby można było ją potem usunąć należy wyłączyć opcję "Chroń kontener przed przypadkowym usunięciem"

Jednostka organizacyjna ma kluczowe znaczenie w domenowych zasadach grupy.

### 8. Dodanie użytkownika do jednostki organizacyjnej

**Aby przenieść użytkownika do jednostki organizacyjnej musimy przenieść ikonę danego użytkownika z katalogu "Users" do katalogu naszej jednostki**
