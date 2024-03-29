---
layout: default
title: Cyklus s podmínkou
permalink: /informatika/cyklus-s-podminkou/
---

> Cyklus (smyčka) je typ řídící struktury (control flow statement), který je v informatice konstrukce pro zápis počítačového programu. Cyklus zajišťuje, že se v závislosti na splnění podmínky část programu vykonává vícekrát.

- Cyklus se skládá z posloupnosti příkazu a podmíněného skoku (skok je narušení v normálním čtení programu)

**Existuje několik druhů cyklů:**
- Nekonečný cyklus (za normálních okolností nikdy nekončí)
- Cyklus while-do (cyklus s podmínkou na začátku)
    - Pokud podmínka není splněna cyklus vůbec nezačíná
- Cyklus do-while (cyklus s podmínkou na konci)
    - Tento cyklus začne pracovat a nekončí, dokud není podmínka splněna
- Cyklus s testem podmínky uprostřed posloupnosti příkazu
    - Ne často používán, umožňuje násilné ukončení cyklu, je tedy možné vytvořit nekonečný cyklus, uvnitř tohoto cyklu testovat nějakou podmínku a ve vhodné situaci cyklus přerušit.
- Cyklus for 
    - Speciální verze cyklu s podmínkou na začátku, obvykle používaný pro výčet prvků z množiny prvků (např. interval <1,10>).

## Příklady

### Cyklus while

```py
# Print i as long as i is less than 6
i = 1
while i < 6:
    print(i)
    i += 1
```

**Break** - přeruší cyklus

```py
# Exit the loop when i is 3
i = 1
while i < 6:
    print(i)
    if i == 3:
        break
    i += 1 
```

**Continue** - přeskočí aktuální iteraci

```py
# Continue to the next iteration if i is 3
i = 0
while i < 6:
    i += 1
    if i == 3:
        continue
    print(i)
```
