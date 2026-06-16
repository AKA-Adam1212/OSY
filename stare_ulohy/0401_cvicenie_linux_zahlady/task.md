
> Vyplň odpovede pod každú otázku. Pri otázkach typu áno/nie zaškrtni `- [x]`.  
> Výstupy z terminálu prilep do code blokov.

---

## Úloha 1 — Pojmy GNU a GPL

### 1.1 Rozdiel „free as in freedom" vs. „free as in beer"

**free as in freedom:**  
Softvér je slobodný — môžeš ho používať, upravovať a zdieľať.

**free as in beer:**  
Softvér je zadarmo — nemusíš zaň platiť.

---

### 1.2 Čo znamená skratka GPL (celý anglický názov)?

**GNU General Public License**

---

### 1.3 Prečo sa Linux niekedy označuje ako „GNU/Linux" a nielen „Linux"?

Pretože operačný systém sa skladá z jadra Linux a nástrojov z projektu GNU.  
Spolu tvoria celý systém, preto sa používa názov GNU/Linux.

---

## Úloha 2 — Práca s distrowatch.com

### 2.1 Na akej distribúcii je postavený Linux Mint?

**Ubuntu**

---

### 2.2 Poradie Linux Mint v rebríčku „Page Hit Ranking — Last 6 months"

- **Poradie:** 2  
- **Hodnota (priemerná návštevnosť/deň):** približne 2000

---

### 2.3 Distribúcia z inej rodiny ako Debian

| Položka | Tvoja odpoveď |
|---|---|
| Názov distribúcie | Fedora |
| Rodina (Red Hat / Arch / SUSE / iná) | Red Hat |
| Balíčkovací systém (apt / dnf / pacman / zypper / iný) | dnf |

---

## Úloha 3 — Prihlásenie a odhlásenie

> 1. Menu → **Log Out** (Odhlásiť sa). **Pozor — nie Shut Down!**  
> 2. Po odhlásení sa prihlás späť svojimi údajmi.

### 3.1 Aká obrazovka sa zobrazila po odhlásení? Čo si na nej videl?

Prihlasovacia obrazovka s možnosťou zadať meno používateľa a heslo.

---

### 3.2 Bola plocha po opätovnom prihlásení rovnaká, alebo „čistá" (zatvorené všetky okná)?

- [ ] rovnaká ako predtým  
- [x] čistá (nové okná)

---

## Úloha 4 — Tri spôsoby spustenia konzoly

### 4.1 Menu → Terminal

Aký je presný názov aplikácie v záhlaví okna?

**Terminal**

---

### 4.2 Klávesová skratka `Ctrl + Alt + T`

Otvoril sa rovnaký program ako v 4.1?

- [x] áno  
- [ ] nie  

---

### 4.3 TTY (`Ctrl + Alt + F3`)

> 1. Stlač `Ctrl + Alt + F3` — uvidíš čierny obraz s textom (TTY).  
> 2. Prihlás sa: meno, Enter, heslo (nevidíš ho!), Enter.  
> 3. Napíš `exit` + Enter.  
> 4. Vráť sa späť do GUI: skús `Ctrl + Alt + F7` (alebo F1, F2).

**Aspoň 2 rozdiely medzi TTY a grafickým terminálom:**

1. TTY nemá grafické rozhranie.  
2. Grafický terminál beží v okne na pracovnej ploche.

**Cez ktoré F-tlačidlo si sa vrátil späť do GUI?**

- [ ] F1  
- [ ] F2  
- [x] F7  
- [ ] iné:

---

## Úloha 5 — Čítanie promptu

### 5.1 Výstupy príkazov

Skopíruj výstup z terminálu sem:

```
$ whoami
student

$ hostname
student-virtualbox

$ pwd
/home/student

$ echo $USER
student
```

---

### 5.2 Aký znak je na konci tvojho promptu?

- [x] `$`  
- [ ] `#`  

---

### 5.3 Čo tento znak hovorí o tvojich právach v systéme?

Že používateľ nemá administrátorské (root) práva.

---

### 5.4 Čítanie promptu

Pozri sa na svoj prompt (príklad: `andrej@mint:~$`).  
Vypíš, čo všetko z neho vieš prečítať **bez napísania jediného príkazu**:

- meno používateľa  
- názov počítača  
- aktuálny priečinok  
- typ používateľa (bežný alebo root)

---

## Záver

Čo bolo pre teba dnes nové alebo zaujímavé?

Práca s TTY konzolou a rozdiel medzi používateľom a rootom.