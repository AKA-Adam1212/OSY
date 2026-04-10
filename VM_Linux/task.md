# Prehľad možností spustenia Linuxu na mojom PC



Poznámka: Windows Subsystem for Linux (WSL) mi nefunguje, pretože nemám funkčný Windows Update, ktorý je potrebný na jeho inštaláciu a správne fungovanie.

---

## Lokálne virtualizačné riešenia

| Riešenie | Funguje | Odôvodnenie |
|----------|---------|--------------|
| Oracle VM VirtualBox | ÁNO | Funguje bez potreby Windows Update. Limitom je 4 GB RAM, čo spôsobuje nízky výkon a obmedzenú použiteľnosť Linux VM. |
| VMware Workstation Player | ÁNO | Stabilnejšie riešenie ako VirtualBox, ale stále limitované nízkou RAM, čo spôsobuje pomalší chod systému. |
| Windows Subsystem for Linux (WSL) | NIE | Nejde nainštalovať kvôli nefunkčnému Windows Update, ktorý je potrebný pre aktiváciu WSL komponentov. |
| QEMU | NIE | Príliš vysoké nároky na výkon CPU a RAM v mojom systéme, bez akcelerácie je použitie neefektívne. |
| Hyper-V | NIE | Aj keby bolo dostupné, 4 GB RAM nestačí na plynulú virtualizáciu. |
| Proxmox VE | NIE | Ide o serverové riešenie vyžadujúce samostatný operačný systém, nie použitie vo Windows prostredí. |

---

## Webové (prehliadačové) riešenia

| Riešenie | Funguje | Odôvodnenie |
|----------|---------|--------------|
| DistroSea | ÁNO | Linux beží priamo v prehliadači bez inštalácie. Nevýhodou je závislosť na internete a dočasnosť prostredia. |
| JSLinux | ÁNO | Emulovaný Linux v prehliadači, vhodný na základné testovanie, ale veľmi nízky výkon. |
| WebVM | ÁNO | Linux beží cez WebAssembly v prehliadači. Bez inštalácie, ale s obmedzeným výkonom. |
| Cloud VM (AWS / Azure / GCP) | ÁNO | Linux beží na vzdialenom serveri, PC slúži iba ako klient. Môže byť však platený a závislý od internetu. |

---

## Záver

Na mojom počítači je najpraktickejšie používať:
- DistroSea na rýchle testovanie Linuxu bez inštalácie
- VirtualBox alebo VMware na základnú virtualizáciu
- Live USB Linux pre plný výkon systému

WSL nie je v mojom prípade použiteľné kvôli nefunkčnému Windows Update a obmedzeniam systému.