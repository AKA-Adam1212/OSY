# Cvičenie: Príkazový riadok OS — `ls`, `cd`, `cp`, `rm`, `mv`

> Vyplň odpovede pod každú otázku. Pri otázkach typu áno/nie zaškrtni `- [x]`. Výstupy z terminálu prilep do code blokov.

---

## Úloha 1 — Orientácia v systéme

### 1.1 Napíš `pwd` a zapíš výstup (absolútna cesta k tvojmu domovu):

```
/home/student
```

---

### 1.2 Napíš `ls`. Vymenuj aspoň 3 položky, ktoré vidíš:

- Documents
- Downloads
- Desktop

---

### 1.3 Napíš `ls -l`. Nájdi:

- **Jeden priečinok** (začína `d`): `drwxr-xr-x Documents`
- **Jeden súbor** (začína `-`): `-rw-r--r-- file.txt`

---

### 1.4 Napíš `ls -a`. Zapíš aspoň 3 skryté položky:

- .bashrc  
- .profile  
- .config  

---

## Úloha 2 — Navigácia po strome

### 2.1 Spusti `cd ~`, potom `pwd`:

```
/home/student
```

---

### 2.2 Spusti `cd ..`, potom `pwd`:

```
/home
```

---

### 2.3 Spusti `cd /`, potom `pwd`:

```
/
```

---

### 2.4 Spusti `cd -`. Čo ti vypíše shell na obrazovku?

```
/home/student
```

---

### 2.5 Ako sa najrýchlejšie vrátiš do svojho domovského adresára? Napíš dva spôsoby:

1. `cd ~`
2. `cd`

---

## Úloha 3 — Kopírovanie

### 3.1 Vytvor štruktúru:

Výstup `ls`:

```
Documents  Downloads  skola  poznamky.txt  uloha.txt
```

---

### 3.2 Skopíruj súbor do priečinka:

Výstup `ls skola/`:

```
poznamky.txt
```

---

### 3.3 Duplikuj súbor pod novým menom:

- [x] áno  
- [ ] nie  

---

### 3.4 Skús skopírovať priečinok BEZ `-r`:

```
cp: -r not specified; omitting directory 'skola'
```

---

### 3.5 Teraz s `-r`:

Výstup `ls`:

```
skola  zaloha_skola  Documents  Downloads
```

---

### 3.6 Prečo `cp` potrebuje `-r` pri priečinkoch?

Pretože priečinok obsahuje ďalšie súbory a podpriečinky, ktoré treba kopírovať rekurzívne.

---

## Úloha 4 — Premenovanie a presun

### 4.1

- [ ] áno — ostal  
- [x] nie — zmizol (premenovaný)

---

### 4.2

```
$ ls
Documents  Downloads  hotovo.txt

$ ls Documents/
(skôr existujúce súbory v Documents)
```

---

### 4.3

- [x] áno  
- [ ] nie  

---

### 4.4 Doplň pravidlo:

- `mv` súbor priečinok/ → **presun**
- `mv` súbor novy_nazov → **premenovanie**

**Ako `mv` rozozná akciu?**  
Podľa toho, či cieľ existuje ako priečinok alebo nie.

---

## Úloha 5 — Mazanie ⚠️

### 5.1

- [ ] áno  
- [x] nie  

---

### 5.2

```
rm: cannot remove 'zaloha_skola': Is a directory
```

---

### 5.3

```
Documents  Downloads
```

---

### 5.4 Kde skončí vymazaný súbor v Linuxe?

Nikde — je okamžite odstránený zo systému (nepoužíva sa kôš ako vo Windows).

---

### 5.5 Prečo je `rm -rf /` nebezpečný?

Pretože bez potvrdenia môže zmazať celý súborový systém vrátane systémových súborov, čím zničí celý operačný systém.

---

## Bonus — tab completion a history

### B.1

Doplnil sa názov priečinka automaticky (Tab completion).

---

### B.2

Zobrazil sa predchádzajúci príkaz.

---

### B.3

Najzaujímavejšie: Tab completion, pretože zrýchľuje prácu a znižuje chyby v písaní príkazov.

---

## Záver

Najužitočnejší príkaz bol `cd`, pretože umožňuje rýchlu navigáciu v systéme.