# Cvičenie: Štruktúra adresárov v Linuxe + POSIX

> Vyplnené ako príklad z bežnej inštalácie VirtualBoxu s Ubuntu Linuxom.
> Hodnoty sa môžu mierne líšiť podľa tvojej virtuálnej mašiny.

---

## Úloha 1 — Programy v systéme

### 1.1 Spusti `ls /bin | head` a vymenuj **5 príkazov**, ktoré poznáš:

- ls
- cat
- cp
- mv
- mkdir

### 1.2 Spusti `which ls`. Kde reálne leží `ls`?

```bash
/usr/bin/ls
```

### 1.3 Spusti `which` s nejakým iným programom (napr. `python3`, `nano`, `firefox`):

```bash
which python3
```

**Výstup:**

```bash
/usr/bin/python3
```

### 1.4 Aký je rozdiel medzi `/bin` a `/sbin`?

> `/bin` obsahuje bežné príkazy pre všetkých používateľov, zatiaľ čo `/sbin` obsahuje systémové nástroje určené hlavne pre správcu systému (roota).

---

## Úloha 2 — Konfigurácie a používatelia

### 2.1 Spusti `cat /etc/hostname`. Ako sa volá tvoj počítač?

```bash
adam-VirtualBox
```

### 2.2 Spusti `cat /etc/passwd | grep $USER`. Skopíruj **celý riadok**:

```bash
adam:x:1000:1000:Adam:/home/adam:/bin/bash
```

### 2.3 Z tohto riadku zisti:

- **UID** (tretie pole, oddelené `:`): 1000
- **Shell** (posledné pole): /bin/bash
- **Domov** (predposledné pole): /home/student

### 2.4 Aké **používateľské meno** má UID 0?

> root

---

## Úloha 3 — Prieskum systému

> Pre tieto úlohy nepotrebuješ `sudo` — všetko je verejne čitateľné.

### 3.1 Aký máš procesor? Spusti:

```bash
cat /proc/cpuinfo | grep "model name" | head -1
```

```bash
model name : 12th Gen Intel(R) Core(TM) i5-12400F
```

### 3.2 Koľko máš RAM? Spusti:

```bash
cat /proc/meminfo | head -3
```

```bash
MemTotal:        4010532 kB
MemFree:          2481752 kB
MemAvailable:    2965240 kB
```

### 3.3 Ako dlho beží systém? Spusti `uptime`:

```bash
14:29:30 up 26 min, 1 user, load average: 0.01, 0.01, 0.02
```

### 3.4 Vymenuj **3 logy**, ktoré nájdeš v `/var/log/`:

```bash
ls /var/log/ | head
```

- alternatives.log
- auth.log
- boot.log

### 3.5 Aké disky / partície máš? Spusti:

```bash
ls /dev | grep sd
```

```bash
sda
sda1
sda2
sda3
```

### 3.6 Bonus — spusti `uname -a` a zapíš výstup:

```bash
Linux adam-VirtualBox 6.14.0-37-generic #37~24.04.1-Ubuntu SMP PREEMPT_DYNAMIC Thu Nov 20 10:25:38 UTC 2 x86_64 x86_64 x86_64 GNU/Linux
```

---

## Úloha 4 — POSIX v praxi

### 4.1 Funguje `ls -la` aj na macOS?

- [x] áno
- [ ] nie

### 4.2 Funguje `ls -la` v CMD na Windowse (bez WSL)?

- [ ] áno
- [x] nie

### 4.3 Prečo rovnaký bash skript beží na Linuxe aj na MacBooku?

> Pretože oba systémy podporujú POSIX štandard a používajú podobné shellové príkazy a systémové rozhrania.

### 4.4 Vymenuj **2 OS**, ktoré sú POSIX-kompatibilné (okrem Linuxu):

1. macOS
2. FreeBSD

### 4.5 Čo treba nainštalovať na Windows, aby si tam mohol spúšťať Linuxové príkazy?

> WSL (Windows Subsystem for Linux)

---

## Úloha 5 — Orientácia v cudzom systéme

> Predstav si, že ti práve dali SSH prístup na neznámy server. Bez toho, aby si čokoľvek menil, zisti tieto informácie.

### 5.1 Aká je distribúcia? Spusti:

```bash
cat /etc/os-release | head -3
```

```bash
NAME="Linux Mint"
VERSION="22.3 (Zena)"
ID=linuxmint
```

### 5.2 Si root alebo bežný používateľ? Spusti `whoami`:

```bash
adam
```

### 5.3 Koľko používateľov má účet v `/home`? Spusti `ls /home`:

```bash
adam
```

### 5.4 Aká verzia jadra beží? Spusti `uname -r`:

```bash
6.14.0-37-generic
```

### 5.5 Vlastnými slovami: aké **3 príkazy** spustíš ako prvé na novom Linuxe, aby si zistil, kde si?

1. pwd
2. whoami
3. uname -a

---

