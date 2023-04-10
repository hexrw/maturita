---
layout: default
title: Záznamová média a zálohování dat, komprimace
permalink: /informatika/zaznamova-media-a-zalohovani-dat-komprimace/
---

## Záznamová média

> Záznamová média (také datová média) je obecné označení pro paměťový nosič datových informací používající k jejich uchování nějaký fyzikální princip. Rozdělujeme je podle principu čtení na magnetická, optická a elektronická.

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

> Záloha nebo záložní kopie je kopie dat uložená na jiném datovém nosiči (nebo i místě). Záložní data jsou využívána v případě ztráty, poškození nebo jiné potřeby práce s daty uloženými v minulosti. Zálohování probíhá nepravidelně (např. v domácnostech) nebo pravidelně podle rozvrhu (např. ve firmách).

Při zálohování většího množství dat se obvykle používá specializovaný program (například i v systému Microsoft Windows je součástí instalace), který celý proces zálohování usnadňuje (viz níže). Pro zálohování většího množství dat je možné použít také specializovaná zařízení (hardware), která pracují poloautomaticky nebo plně automatizovaně. Proces zálohování dat klade velký důraz na rychlou obnovu dat oproti archivaci.

V poslední době je využíváno komplexních zálohovacích systémů, které umožňují efektivně zálohovat mnoho počítačů propojených počítačovou sítí nebo naopak na mnoho počítačů propojených v síti data zálohovat (tzv. úložný cluster).

**Zálohování může probíhat v těchto základních režimech:**
- **Online** – Proces tvorby zálohy počítače za jeho běžného chodu.
- **Offline** – Zálohování je prováděno mimo běžný provoz počítače; obvykle se provádí za pomoci zavedení speciálního média.

### Typy záloh

Pro různé podmínky se používají různé strategie zálohování. Volba správné strategie je závislá na tom, jestli je potřeba se zálohami pracovat velmi často nebo je naopak požadována maximální délka archivace zálohovaných dat. Existují i další kritéria, která odrážejí konkrétní specifické podmínky.

- **Nestrukturovaná**
    - Nestrukturovaným úložištěm může být větší množství disket, CD, DVD medií s minimem informací o záloze. Tento způsob je nejjednodušší, ale není příliš oblíben u větších firem.

- **Úplná + Inkrementální**
    - Tento model má za cíl vytvořit více kopií zálohovaných dat vhodnějším způsobem. Nejdříve je provedena úplná záloha všech dat. Posléze je prováděna inkrementální záloha (ukládány jsou pouze soubory, které se změnily od předešlé úplné nebo inkrementální zálohy). Hlavní nevýhodou je, že při obnovení zálohy je potřeba pracovat s úplnou zálohou a následně se všemi inkrementálními zálohami až k požadovanému okamžiku zálohy, což může být velmi náročné na pracovní prostor.

- **Úplná + Rozdílová**
    - Rozdíl oproti předešlé metodě je v tom, že po úplné záloze se každá částečná záloha zachytí všechny soubory vytvořené nebo změněné od vytvoření úplné zálohy, třebaže některé už jsou obsaženy v předešlé částečné záloze. Výhodou je, že obnova zahrnuje obnovení pouze poslední úplné zálohy, a potom její překrytí poslední rozdílovou zálohou, takže je proces obnovení více odolný vůči defektu média se zálohou.

- **Zrcadlová + Reverzně přírůstková**
    - Tento model obsahuje zrcadlo reflektující stav systému po poslední záloze a historii přírůstkových záloh. Výhodou je, že máme neustále k dispozici aktuální plnou zálohu a ukládáme pouze historii změn. Každé zálohování se automaticky promítá do zrcadla a soubory, které byly změněny, jsou přesunuty do přírůstkové zálohy. Tato metoda se nehodí pro přenosná media, protože každá záloha musí být provedena pomocí srovnání se zrcadlem.

- **Průběžná ochrana dat**
    - Tato metoda využívá místo plánovaných periodických záloh okamžitý zápis každé změny do žurnálu změn (logu). Provádí se ukládáním změněných bajtů nebo celých bloků dat místo ukládání celých změněných souborů. Průběžný záznam změn v žurnálu umožňuje získat obraz dat v minulosti. Naproti tomu prosté zrcadlení dat na druhý disk (např. RAID 1) stav v minulosti nezachycuje.

- **Úplná záloha systému**
    - Metoda zálohuje obvykle celý počítač včetně operačního systému, vytváří obraz disku. K tomuto typu zálohování je třeba specializovaný software, jako je např. Acronis True Image

## Komprimace, dekomprimace

> **Komprimace** je proces, při kterém jsou data (soubory i celé adresáře) převedena (tzv. zkomprimována) do souboru zabírajícího méně místa (proto se tomu někdy říká zabalení).

> **Dekomprimace** je proces opačný zkomprimovaná (zabalená) data se převedou (rozbalí) zpět do původního tvaru

- **formáty bez komprese** - např. BMP – na disku zabere nejvíce místa
- **formáty s bezeztrátovou kompresí** - např. PCX, GIF – obrázek je stále stejný, ale na disku zabere méně místa (např. třetinu)
- **formáty se ztrátovou kompresí** - např. JPG – obrázek se trochu poškodí (což oko nepozná), ale na disku zabere málo místa (např. desetinu)

### Význam a užití

- hlavním důvodem pro komprimaci dat je nedostatečná kapacita paměťových médií (zejména disket)
- typické užití: přenášení dat mezi počítači pomocí disket (pokud se nějaký soubor na disketu nevejde, je nutno ho zkomprimovat)
- dalším užitím je zabalení nepoužívaného SW na pevném disku (až bude potřeba, tak se rozbalí)

### Princip

- v počítači jsou všechny informace kódovány pomocí nul a jedniček – libovolný soubor si lze představit jako posloupnost nul a jedniček (např. 0010111010110001010110 atd.)

- jelikož se v těchto posloupnostech často opakují některé úseky (často se např. může opakovat čtveřice 0011), lze celou posloupnost (celý soubor) překódovat tak, aby byla nakonec kratší (což se právě děje při komprimaci)

### Komprimační programy

> Pro komprimaci a dekomprimaci se používají tzv. komprimační programy.

**Všechny komprimační programy lze hodnotit především podle:**
1. tzv. kompresního poměru
    - udává, jak hodně dokáže komprimační program zmenšit balená data (v průměru)
    - např. poměr 2:1 znamená, že program (v průměru) balí data na poloviční velikost (někdy se komp. poměr udává v % - pak poměr 60 % znamená, že se soubor zmenšil o 60 %)
    - různé typy souborů (texty, obrázky, programy) lze zabalit různě úspěšně (texty lze někdy zmenšit až na jednu desetinu, obrázky někdy nelze zmenšit vůbec)
2. rychlosti práce
    - s komprimací se uživatel nevědomky setkává také při používání grafických programů:
    - obrázky, se kterými grafické programy pracují, zabírají obvykle na disku mnoho místa
    - grafické programy proto umí při ukládání obrázek zabalit - záleží na tom, jaký grafický formát (GIF, PCX, BMP, ..) vyberete – grafické formáty se dělí na:

----------------------

**Zdroje**

- [https://www.maturita.digitalwizard.cz/okruhy/5-zaznamova-media/](https://www.maturita.digitalwizard.cz/okruhy/5-zaznamova-media/)
- [https://cs.wikipedia.org/wiki/Z%C3%A1lohov%C3%A1n%C3%AD_dat](https://cs.wikipedia.org/wiki/Z%C3%A1lohov%C3%A1n%C3%AD_dat)
- [http://www2.ef.jcu.cz/~inrem/edu/it/komprimace/](http://www2.ef.jcu.cz/~inrem/edu/it/komprimace/)
