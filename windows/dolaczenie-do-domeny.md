---
title: "INF0.2 - Przyłączanie stacji roboczej do domeny"
---
# INF0.2 - Przyłączanie stacji roboczej do domeny

> **Powiązane notatki:**
> - [Promowanie serwera do roli kontrolera domeny](./promowanie-domeny.md) — utworzenie domeny
> - [Domenowe zasady grupy (GPO)](./gpo-domenowe.md) — zarządzanie stacjami w domenie

### 1. Dodanie nowej stacji roboczej do domeny
**Narzędzia > Użytkownicy i komputery usługi AD > PPM > Nowy > Komputer**

### 2. Automatyczne dodanie stacji roboczej do domeny
Musimy ustawić stały adres IP w sieci naszego serwera. Bramę domyślną ustawiamy na adres routera/serwera (nie pozostawiamy pustej!), natomiast adresem DNS jest adres naszego serwera (kontrolera domeny).

Gdy nasze komputery się pingują należy:
**PPM (na logo windows) > System > Zaawansowane ustawienia systemu > Nazwa komputera > Zmień > Domena (w polu członek) > Wpisujemy nazwę domeny (nazwa.local).**

Gdy pojawi się nam okienko o wpisanie nazwy użytkownika i hasło to wpisujemy według schematu:
**NAZWA(Domeny)/nazwa_uzytkownika**
**haslo_uzytkownika**

Aby zmiany zostały uwzględnione musimy zrestartować komputer

### 3. Zarządzanie logowania danego użytkownika do różnych stacji
Mamy możliwość ustawienia na jakie komputery może zalogować się dany użytkownik. Robimy to tak:
**PPM (na użytkownika) > Właściwości > Konto > Zaloguj do > Następujące komputery**

### 4. Profil mobilny (roaming profile)
Profil mobilny sprawia, że ustawienia użytkownika (tapeta, dokumenty, konfiguracja aplikacji) są przechowywane na serwerze i dostępne z każdej stacji w domenie.

Na serwerze tworzymy udział sieciowy na profile:
**PPM (na folder) > Właściwości > Udostępnianie > Udostępnianie zaawansowane > Udostępnij ten folder > Nazwa udziału: `profile$`** (znak `$` ukrywa udział)

Nadajemy uprawnienia NTFS:
**Zabezpieczenia > Edytuj > Dodaj > Wpisujemy `Everyone` > Pełna kontrola**

Następnie w AD konfigurujemy profil mobilny dla użytkownika:
**Narzędzia > Użytkownicy i komputery usługi AD > PPM (na użytkownika) > Właściwości > Profil > Ścieżka profilu**

Wpisujemy ścieżkę UNC do udziału:
```
\\NAZWA_SERWERA\profile$\NAZWA_UZYTKOWNIKA
```

Przy pierwszym logowaniu użytkownika na stacji roboczej profil zostanie skopiowany z domyślnego profilu lokalnego na serwer. Przy kolejnych logowaniach ustawienia będą pobierane z serwera.
