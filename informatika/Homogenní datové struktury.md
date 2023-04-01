---
layout: default
title: Homogenní datové struktury
permalink: /informatika/homogenni-datove-struktury/
---

> Datová struktura: konkrétní způsob organizace dat v paměti počítače, který zajišťuje, aby mohla data být používána efektivně, v počítači jsou reprezentovány datovými typy.  

Homogenní datová struktura: umožňuje uchovávat a zpracovávat množinu dat stejného typu.

## Typy datových struktur 

### Pole (array)

Pole si můžeme představit jako uspořádanou matici prvků určitého datového typu.  Prvky dat jsou uloženy do paměti v navazujících blocích za sebe, a jsou identifikovány pomocí indexu. Pozici prvku v paměti pak lze dopočítat (adresa počátku pole + index * velikost prvku).

- Pole mohou mít libovolný počet rozměrů. Nejjednodušším typem jsou lineární pole
- Přístup k prvkům více rozměrného pole se řeší použitím více indexů podobně jako u matic. 
- **Statická pole** - pole s pevným počtem prvků
- **Dynamická pole** - pole s proměnlivým počtem prvků 

### Spojový seznam (linked list)

Datová struktura určená k ukládání dat předem neznámé délky. Spojové seznamy jsou tvořeny vzájemně propojenými uzly. Každý uzel obsahuje jeden datový prvek a jeden nebo více ukazatelů na další uzly. 

- Na základě použitých ukazatelů rozlišujeme několik druhů spojových seznamů.
    - Jednosměrný
    - Obousměrný 
    - Kruhový

### Fronta (queue)

> Datová struktura s proměnlivým počtem zařazených prvků fungující na principu fifo (first in first out). Prvek uložený ve frontě jako první, je jako první na řadě pro výběr. Fronta aktivně pracuje pouze s prvním a posledním zařazeným prvkem.

- K tomuto účelu používá sadu tří základních operací:
  - Zařazení prvků
    - Vyřazení prvků
    - Test prázdnoty 
- Existují i prioritní fronty, ve kterých se prvky řadí podle priority, z fronty je pak vytáhnut jako první prvek s největší prioritou.

**Mezi další datové struktury patří:**
- Zásobník (stack)
- Stromové struktury (Tree)
- Grafy 
- Hashe
