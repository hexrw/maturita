---
layout: default
title: Vektorová počítačová grafika
permalink: /informatika/vektorova-pocitacova-grafika/
---

*Vektorová grafika je jeden ze dvou základních způsobů reprezentace obrazových informací v počítačové grafice. Zatímco v rastrové grafice je celý obrázek popsán pomocí hodnot jednotlivých barevných bodů (pixelů) uspořádaných do pravoúhlé mřížky, vektorový obrázek je složen ze základních, přesně definovaných útvarů, jako jsou body, přímky, křivky a mnohoúhelníky.*

### Výhody

Vektorová grafika má proti rastrové grafice některé výhody:

- Je v ní možné libovolné zmenšování nebo zvětšování obrázku beze ztráty kvality (viz ukázka v úvodu článku).
- Je možné pracovat s každým objektem v obrázku odděleně.
- Výsledná paměťová náročnost obrázku je u jednolitých barevných obrázků menší, než při použití rastrového zápisu (Např. černé kolečko se zapíše jako kruh o daném poloměru vyplněný černou barvou – tedy 3 informace, zatímco u bitmapy by bylo zapotřebí definovat každý pixel zvlášť, přitom pořád dokola téměř stejnou informací – pixel barvy #000000 o souřadnici [x,y], pixel barvy #000000 o souřadnici [x+1,y], pixel barvy #000000 o souřadnici [x+2,y], atd.)

### Nevýhody

- Oproti rastrové grafice zpravidla složitější pořízení obrázku. V rastrové grafice lze obrázek snadno pořídit pomocí fotoaparátu nebo skeneru.
- Překročí-li složitost grafického objektu určitou mez, začne být vektorová grafika náročnější na operační paměť a procesor než grafika bitmapová.
- Nehodí se na zápis složitých barevných ploch, například fotografie.

### Použití

Vektorová grafika se používá zejména pro počítačovou sazbu, tvorbu ilustrací, diagramů, logotypů, nebo při tvorbě flashových animací. Pro práci s vektorovou grafikou se používají vektorové editory (např. Adobe Illustrator, CorelDRAW, Inkscape nebo Zoner Callisto 5).

### Bézierova křivka

Teoretickým základem vektorové grafiky je analytická geometrie. Obrázek není složen z jednotlivých bodů, ale z křivek – vektorů. Křivky spojují jednotlivé kotevní body a mohou mít definovanou výplň (barevná plocha nebo barevný přechod). Tyto čáry se nazývají Bézierovy křivky.

Francouzský matematik Pierre Bézier vyvinul metodu, díky které je schopen popsat pomocí čtyř bodů libovolný úsek křivky. Křivka je popsána pomocí dvou krajních bodů (tzv. kotevní body) a dvou bodů, které určují tvar křivky (tzv. kontrolní body). Spojnice mezi kontrolním bodem a kotevním bodem je tečnou k výsledné křivce. 

### Formáty vektorové grafiky

- Scalable Vector Graphics (.SVG)
- Encapsulated PostScript (.EPS)
- CorelDRAW Files (.CDR)
- Adobe Illustrator Files (.AI)
- Portable Document Format (.PDF)

### Operace s vektory

Vektorové grafické editory obvykle umožňují translaci, rotaci, zrcadlení, roztažení, zkosení, afinní transformace, změnu z-pořadí (volně řečeno, co je před čím) a kombinaci primitiv do složitějších objektů. Mezi složitější transformace patří množinové operace na uzavřených tvarech (sjednocení, rozdíl, průnik atd.). V SVG jsou kompoziční operace založeny na alfa kompozici.

Vektorová grafika je ideální pro jednoduché nebo složené kresby, které musí být nezávislé na zařízení nebo nepotřebují dosáhnout fotorealismu. Vektorový grafický model používají například jazyky pro popis stránek PostScript a PDF.
