---
title: "INF0.2 - Zarządzanie użytkownikami"
---
# INF0.2 - Zarządzanie użytkownikami

> **Powiązane notatki:**
> - [Korzystanie z CMD](./cmd.md) — zarządzanie użytkownikami z linii poleceń
> - [MMC i przystawki](./mmc.md) — lusrmgr.msc jako przystawka

### 1. Dostępne narzędzia
Zarządzanie użytkownikami w Windows jest proste. Pierwsze co przychodzi nam do głowy gdy mamy polecenie "Dodać użytkownika" to ustawienia i zakładka "Użytkownicy", niestety gdy wybierzemy tą opcję będziemy zmuszeni odpowiadać na pytania zabezpieczające Microsoftu i będziemy musieli spełniać wymogi dotyczące haseł itd.

Dlatego mamy inne opcje:

**Zarządzanie komputerem > Użytkownicy i grupy lokalne (nie działa na win11)**
**Win + R > lusrmgr.msc > Użytkownicy (nie działa na win11)**

Aby dodać nowego użytkownika wystarczy
**PPM (folder użytkownicy) > Nowy użytkownik**

Mamy również możliwość utworzenia nowego użytkownika przez CMD:
```batch
net user — wypisuje wszystkich dostępnych użytkowników
net user nazwa_uzytkownika haslo /add — dodaje nowego użytkownika
```

Poza dodaniem użytkownika możemy dodać również grupę:
**Win + R > lusrmgr.msc > Grupy**

Aby dodać nową grupę wystarczy:
**PPM (folder grupy) > Nowa grupa**

Taką samą operację możemy wykonać w CMD:
```batch
net localgroup — lista dostępnych grup
net localgroup nazwa_grupy /add — dodaje nową grupę
net localgroup nazwa_grupy nazwa_uzytkownika /add — dodaje użytkownika do grupy
```

### 2. Przydziały dyskowe
**PPM (na dysk C:) > Właściwości > Przydział > Pokaż ustawienia przydziałów > Włącz zarządzanie przydziałami > Odmów miejsca użytkownikom przekraczających przydział**

Jeśli chcemy ograniczyć przydział dla nowych użytkowników to wybieramy opcję:
- Ogranicz miejsce na dysku do
Jeśli chcemy ograniczyć przydział dla konkretnego użytkownika to:
**Wpisy przydziałów > Przydział > Nowy wpis przydziału > Ogranicz miejsce na dysku**
