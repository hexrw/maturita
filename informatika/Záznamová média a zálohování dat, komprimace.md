---
layout: default
title: Záznamová média a zálohování dat, komprimace
permalink: /informatika/zaznamova-media-a-zalohovani-dat-komprimace/
---

## Záznamová média

*Záznamová média (také datová média) je obecné označení pro paměťový nosič datových informací používající k jejich uchování nějaký fyzikální princip. Rozdělujeme je podle principu čtení na magnetická, optická a elektronická.*

Ještě před magnetickými záznamovými médii se používaly jednorázové děrné štítky, do kterých se kód fyzicky vyrazil v podobě děr. Za předchůdce můžeme považovat také hliněné destičky, pergamen a papír.

### Magnetická záznamová média

- **Disketa (=floppy disk)**
    - byla rozšířená díky nízké výrobní ceně
    - malá rychlost, nízká životnost, nespolehlivost, malá kapacita (cca 1.5 MB)
    - pro čtení slouží disketová mechanika, informace jsou uloženy v soustředných kruzích nazývaných stopy, ty jsou rozděleny na sektory
- **Pevný disk (HDD)**
    - HDD = hard disk drive
    - funguje na principu magnetické indukce, data jsou uložena na disku za pomoci cívky a elektrického proudu
    - hlava zapisuje na diskové plotny
    - data jsou na disku organizována do soustředných kružnic (=stop)
    - nevolatilní paměť, data zůstanou zapsaná i po vypnutí proudu
    - rozhraní připojení k počítači:
        - ATA: dříve rozšířené, jednoduché, levné
        - SATA: dnes, vyšší rychlost, inteligentnější řadič
    - diskové pole (RAID)
        - Redundant Array of Independent Disks – vícenásobné diskové pole nezávislých disků, dříve inexpensive disks
        - metoda zabezpečení dat proti selhání pevného disku, které je realizováno specifickým ukládáním dat na více nezávislých disků, kdy jsou uložená data zachována i při selhání některého z nich
        - často používán na serverech, nenahrazuje však plnohodnotně zálohování dat
    - souborové systémy
- **Magnetická páska**
    audiokazety, videokazety
    funguje na principu magnetické vrstvy nanesené na plastovém pásku

### Optická záznamová média

- **Compact Disk (CD – ROM)**
    - data nejsou zapisována do soustředných kružnic, ale do jedné spirály, zápis začíná ve středu a pokračuje k okraji
    - pro čtení se využívá laserové světlo
    - záznam dat je přístupný pouze z jedné strany
    - obvykle kapacita 700 MB
    - nevadí magnetické pole, hrozí však poškrábání
- **Digital Video Disc (DVD)**
    - optický datový nosič obsahující videa ve vysoké kvalitě
    - podobný CD disku
    - mohou být oboustranné nebo vícevrstvé, kapacita do 20 GB
    - různé typy:
        - DVD R = recordable
        - DVD R/RW = recordable, rewritable
        - DVD R DL = dual layer
- **High Definition Digital Video Disc (HD DVD)**
    - třetí generace optických disků
    - vyšší kapacita, vyšší kvalita
    - vyvíjela Toshiba
- **Blu-ray Disc**
    - třetí generace optických disků
    - Sony ve spolupráci s Philips, konkurence HD DVD
    - název odkazuje na modrý paprsek užívaný ke čtení
    - kapacita až 130 GB
    - “Blu-ray” je ochranná známka

### Elektronická záznamová média

**flash paměť**
    - paměť stálá (nevolatilní), energeticky nenáročná
    - vyšší rychlost a odolnost (neobsahuje žádné pohyblivé součástky)
    - horší poměr kapacita / cena oproti HDD
    - omezená životnost 

**USB Flash Disk**
    - malé, kompaktní, ve fromě přívěsků na klíče
    - nahrávání dat do paměti přes sběrnici USB
    - rychlost zápisu/čtení ovlivněna verzí USB, rychlostí hardwarové sběrnice, rychlostí čtení dané jednotky USB disku
**SSD (=solid-state drive)**
    - používají stejná rozhraní SATA jako pevné disky
    - oproti HDD tiché, rychlý start, rychlejší čtení a zápis, nižší spotřeba energie, vyšší odolnost daná absencí pohyblivých částí) 
**paměťové karty**
    - elektronické zařízení pro ukládání dat
    - využití ve fotoaparátech, mobilních telefonech
    - určeny pro uchování dat, ne pro přenos
    - různé rozměry, např.: miniSD, microSD
    - základní typy:
        - SD = secure digital
            - mají postranní vypínač, který umožňuje kartu zamknout proti - nechtěnému zápisu, pozice “lock” neumožňuje data přepisovat, mazat nebo přidávat
            - novější verze SDHC (SD 2.0) a SDXC (SD 3.0)
        - MMC = multimedia card
            - nemá funkci “lock/open”

## Zálohování dat


## Komprimace
