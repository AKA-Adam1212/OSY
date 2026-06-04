````md
# Cvičenie: Súborové systémy + monitorovanie procesov

**Meno:** Adam  
**Dátum:** 04.06.2026

> Vyplň odpovede pod každú otázku. Výstupy z terminálu prilep do code blokov.

---

## Úloha 1 — Pripojené disky

### 1.1 Spusti `mount | grep "^/dev"`. Vymenuj disky, ktoré sú pripojené:

```bash
mount | grep "^/dev"
````

**Výstup:**

```text
/dev/sda3 on / type ext4
/dev/sda2 on /boot/efi type vfat
```

---

### 1.2 Spusti `df -T /`. Aký súborový systém má tvoj koreňový disk?

```bash
df -T /
```

**Odpoveď:**

```text
ext4
```

---

### 1.3 Spusti `cat /etc/fstab`. Koľko trvalých pripojení je tam definovaných?

```bash
cat /etc/fstab | grep -v "^#" | grep -v "^$" | wc -l
```

**Počet:**

```text
3
```

---

### 1.4 Rozdiel medzi `/mnt` a `/media`

`/mnt` sa používa na manuálne dočasné pripájanie diskov, `/media` na automaticky pripájané externé zariadenia (USB, disky).

---

## Úloha 2 — Stav diskov

### 2.1 `df -h` — koreňový disk

```bash
df -h
```

**Výstup pre `/`:**

```text
/dev/sda3  24G  11G  13G  45% /
```

---

### 2.2 Obsadenie `/`

```text
45%
```

---

### 2.3 Domovský adresár

```bash
du -sh ~
```

```text
124M
```

---

### 2.4 Najväčší priečinok v home

```bash
du -sh ~/* 2>/dev/null
```

```text
Všetky priečinky majú 4.0K (žiadny výrazne neprevažuje)
```

---

## Úloha 3 — Procesy

### 3.1 Počet procesov

```bash
ps aux | wc -l
```

```text
201 → 200 procesov (po odpočítaní hlavičky)
```

---

### 3.2 Bash PID

```bash
ps aux | grep bash
```

```text
1730
```

---

### 3.3 PID 1

```bash
ps -p 1
```

```text
systemd
```

---

### 3.4 Top 3 procesy podľa RAM

```bash
ps aux --sort=-%mem | head -3
```

1. firefox (PID 2505)
2. firefox content process (PID 2734)
3. system/hlavička výpisu

---

## Úloha 4 — top

### 4.1 Load average (1 min)

```text
2,01
```

---

### 4.2 Najväčší proces v RAM

```text
Firefox (Isolated Web Content)
```

---

### 4.3 Tasks total

```text
198
```

---

### 4.4 Uptime

```text
12 minút
```

---

## Úloha 5 — Proces sleep

### 5.1 Spustenie

```bash
sleep 600 &
```

```text
[1] 3510
```

---

### 5.2 PID procesu

```text
3510
```

---

### 5.3 Kill

```bash
kill 3510
```

---

### 5.4 Overenie

```bash
ps aux | grep sleep
```

```text
Iba grep proces, sleep už nebeží
```

---

### 5.5 Rozdiel kill vs kill -9

`kill` pošle SIGTERM (korektné ukončenie).
`kill -9` okamžite zabije proces bez možnosti reakcie.

---

## Bonus

### B.1 RAM

```bash
free -h
```

```text
Total: 3.8Gi
Free: 711Mi
```

---

### B.2 Disky

```bash
lsblk
```

```text
sda 25G
├─sda2 /boot/efi
└─sda3 /
```

---

### B.3 Súborové systémy

| Situácia                 | FS    |
| ------------------------ | ----- |
| Linux Mint               | ext4  |
| USB medzi Mac/Windows    | exFAT |
| Externý disk pre Windows | ntfs  |
| NAS so snapshotmi        | btrfs |

---

## Záver

Najviac využijem `df -h`, pretože rýchlo ukazuje stav disku.

Prekvapilo ma, že systém beží s takým veľkým množstvom procesov na pozadí aj pri bežnej práci.

```
```
