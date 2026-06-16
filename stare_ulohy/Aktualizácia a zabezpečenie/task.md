# Cvičenie 6: Aktualizácia, zabezpečenie OS Windows a systémové politiky

## Úloha 1: Windows Update

### 1.1 Pojmy

1. Čo je Windows Update a na čo slúži?
- Windows Update je služba, ktorá zabezpečuje aktualizácie systému Windows, ovládačov a bezpečnostných opráv.

2. Čo znamená označenie KB (napr. KB5034441)?
- KB (Knowledge Base) je jedinečné číslo aktualizácie v databáze Microsoftu.

3. Vysvetlite rozdiel medzi aktualizáciou kvality (Quality) a aktualizáciou funkcií (Feature):
- Quality: opravy chýb a bezpečnostné záplaty  
- Feature: nové funkcie a väčšie zmeny systému  

4. Prečo je nebezpečné neaktualizovať systém? Uveďte reálny príklad:
- Systém môže obsahovať zraniteľnosti → napr. ransomware útok (WannaCry)

### 1.2 Praktická časť

**Otvorte Nastavenia → Windows Update:**

| Otázka | Odpoveď |
|--------|--------|
| Je systém aktuálny? | Áno |
| Koľko aktualizácií čaká na inštaláciu? | 0 |
| Dátum poslednej aktualizácie | 10.03.2026 |
| KB číslo poslednej aktualizácie | KB5034441 |

**Spustite v CMD:** `wmic qfe list brief /format:table`

| Otázka | Odpoveď |
|--------|--------|
| Koľko aktualizácií vidíte vo výpise? | 25 |
| HotFixID poslednej aktualizácie | KB5034441 |

**Otvorte** `services.msc` a nájdite službu Windows Update:

| Otázka | Odpoveď |
|--------|--------|
| Stav služby (Spustená/Zastavená) | Spustená |
| Typ spustenia (Automaticky/Ručne/Zakázané) | Automaticky |

5. Čo by sa stalo, keby ste typ spustenia služby Windows Update zmenili na "Zakázané"?
- Aktualizácie by sa nevykonávali a systém by bol nebezpečný.

---

## Úloha 2: Zabezpečenie Windows

### 2.1 Pojmy

1. Čo je Windows Defender?
- Zabudovaný antivírus vo Windows.

2. Aký je rozdiel medzi rýchlym a úplným skenovaním?
- Rýchly: kontrola najdôležitejších častí  
- Úplný: kontrola celého systému  

3. Čo je firewall a na čo slúži? Vysvetlite vlastnými slovami:
- Firewall kontroluje sieťovú komunikáciu a blokuje nebezpečné pripojenia.

4. Windows firewall má 3 profily – vymenujte ich a napíšte, kedy sa ktorý aktivuje:
- **Doménový** – v doménovej sieti  
- **Súkromný** – doma alebo dôveryhodná sieť  
- **Verejný** – verejné WiFi  

5. Čo znamená príkaz `wf.msc` a čo `firewall.cpl`? Aký je medzi nimi rozdiel?
- wf.msc: pokročilé nastavenia firewallu  
- firewall.cpl: základné nastavenia  

### 2.2 Praktická časť

**Otvorte Zabezpečenie systému Windows a zapíšte stav:**

| Komponent | Stav (OK / Varovanie / Chyba) |
|----------|-----------------------------|
| Ochrana pred vírusmi a hrozbami | OK |
| Firewall a ochrana siete | OK |

**Spustite v CMD:** `netsh advfirewall show allprofiles state`

| Profil | Stav (ON/OFF) |
|--------|--------------|
| Doménový | ON |
| Súkromný | ON |
| Verejný | ON |

6. Prečo by ste nemali firewall vypínať, aj keď vám niečo nefunguje? Čo by ste mali urobiť namiesto toho?
- Firewall chráni systém → namiesto vypnutia treba povoliť konkrétnu aplikáciu.

---

## Úloha 3: Lokálne politiky – gpedit.msc

### 3.1 Pojmy

1. Čo je gpedit.msc a na čo slúži?
- Nástroj na správu lokálnych politík systému Windows.

2. Aký je rozdiel medzi lokálnou politikou a doménovou politikou?
- Lokálna: platí pre jeden PC  
- Doménová: platí pre viac PC v sieti  

3. Čo robí príkaz `gpupdate /force`? Kedy ho musíte spustiť?
- Aktualizuje politiky → po zmene nastavení  

4. Čo robí príkaz `gpresult /r`?
- Zobrazí aktuálne aplikované politiky  

5. Vysvetlite, čo je politika uzamknutia účtu a proti akému typu útoku chráni:
- Uzamkne účet po viacerých zlých pokusoch → chráni proti brute-force útoku  

---

### 3.2 Praktická časť – politiky hesiel

**Cesta:**  
Konfigurácia počítača → Nastavenia systému Windows → Nastavenia zabezpečenia → Politiky účtov → Politika hesiel

| Politika | Aktuálna hodnota |
|----------|-----------------|
| Minimálna dĺžka hesla | 8 |
| Maximálny vek hesla | 30 dní |
| Heslo musí spĺňať požiadavky na zložitosť | Zapnuté |
| Vynútiť históriu hesiel | 5 |

6. Prečo je dôležité vynútiť históriu hesiel? Čo by sa stalo bez nej?
- Používateľ by mohol stále používať to isté heslo.

---

### 3.3 Praktická časť – uzamknutie účtu a CMD

**Nastavte politiku uzamknutia účtu:**
1. Prah uzamknutia – 5 pokusov  
2. Doba uzamknutia – 30 minút  
3. Spustite `gpupdate /force`  

- Hotovo

**Vyskúšajte zakázať CMD:**

Cesta:  
Konfigurácia používateľa → Šablóny pre správu → Systém → Zabrániť prístupu k príkazovému riadku

| Otázka | Odpoveď |
|--------|--------|
| Čo sa stalo po pokuse otvoriť CMD? | CMD je zablokované |
| Funguje PowerShell naďalej? (Áno/Nie) | Áno |

**DÔLEŽITÉ:**  
Vráťte politiku späť na "Nekonfigurované" a spustite `gpupdate /force`

- Vrátené

---

## Bonusové scenáre

### Scenár 1: Ransomware útok

1. Čo mal mať zapnuté, aby sa tomu predišlo? (2 veci)
- Antivirus (Defender)  
- Windows Update  

2. Aký typ skenovania by ste spustili?
- Úplné skenovanie  

---

### Scenár 2: Nový zamestnanec

1. Aký nástroj použijete? (____.msc)
- gpedit.msc  

2. Cesta k politike minimálnej dĺžky hesla:
- Konfigurácia počítača → Nastavenia systému Windows → Nastavenia zabezpečenia → Politiky účtov → Politika hesiel  

3. Cesta k politike zakázania CMD:
- Konfigurácia používateľa → Šablóny pre správu → Systém → Zabrániť prístupu k príkazovému riadku  

4. Aký príkaz spustíte po zmene politiky?
- gpupdate /force  

---

### Scenár 3: Podozrivá aktivita

1. O aký typ útoku ide?
- Brute-force útok  

2. Aká politika by tomu zabránila a aké hodnoty by ste nastavili?
- Politika uzamknutia účtu  
- 5 pokusov, 30 minút blokovanie