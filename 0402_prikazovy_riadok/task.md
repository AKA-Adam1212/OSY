# Cvičenie: Príkazový riadok OS — `ls`, `cd`, `cp`, `rm`, `mv`

> Vyplnené cvičenie (ukážková správna verzia)

---

## Úloha 1 — Orientácia v systéme

### 1.1

```
/home/student
```

---

### 1.2

- Documents  
- Downloads  
- Desktop  

---

### 1.3

- priečinok: `drwxr-xr-x Documents`
- súbor: `-rw-r--r-- notes.txt`

---

### 1.4

- .bashrc  
- .profile  
- .config  

---

## Úloha 2 — Navigácia po strome

### 2.1

```
/home/student
```

---

### 2.2

```
/home
```

---

### 2.3

```
/
```

---

### 2.4

```
/home/student
```

---

### 2.5

1. `cd ~`  
2. `cd`

---

## Úloha 3 — Kopírovanie

### 3.1

```
Documents  Downloads  skola  poznamky.txt  uloha.txt
```

---

### 3.2

```
poznamky.txt
```

---

### 3.3

- [x] áno  
- [ ] nie  

---

### 3.4

```
cp: -r not specified; omitting directory 'skola'
```

---

### 3.5

```
Documents  Downloads  skola  zaloha_skola  poznamky.txt  uloha.txt
```

---

### 3.6

Príkaz `cp` potrebuje `-r`, pretože priečinok obsahuje ďalšie súbory a musí sa kopírovať rekurzívne.

---

## Úloha 4 — Premenovanie a presun

### 4.1

- [ ] áno  
- [x] nie  

---

### 4.2

```
$ ls
Documents  Downloads  hotovo.txt

$ ls Documents/
(ďalšie súbory v priečinku Documents)
```

---

### 4.3

- [x] áno  
- [ ] nie  

---

### 4.4

- presun  
- premenovanie  

**Vysvetlenie:**  
`mv` zisťuje, či cieľ existuje ako priečinok alebo nie.

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

### 5.4

Súbor sa neskončí v koši — je okamžite odstránený zo systému.

---

### 5.5

`rm -rf /` je nebezpečný, pretože môže vymazať celý operačný systém bez potvrdenia.

---

## Bonus

### B.1
Automatické dopĺňanie názvu (Tab completion).

### B.2
Zobrazil sa predchádzajúci príkaz.

### B.3
Najzaujímavejší bol `cd`, lebo umožňuje navigáciu v systéme.

---

## Záver

Najužitočnejší príkaz bol `ls`, pretože umožňuje rýchlo vidieť obsah priečinkov.