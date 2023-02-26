---
layout: default
title: Cyklus s pevným počtem kroků
permalink: /informatika/cyklus-s-pevnym-poctem-kroku/
---

`for` cyklus, cyklus s parametrem, cyklus s řídící proměnnou nebo cyklus s výčtem hodnot

Cykly spolu s podmínkami tvoří základ každého programovacího jazyka.
Jak již slovo cyklus napoví, něco se bude opakovat. Když chceme v programu
něco udělat 100x, jistě nebudeme psát pod sebe 100x ten samý kód, ale
vložíme ho do cyklu. Cyklů máme několik druhů.

Tento cyklus má stanovený pevný počet opakování a
hlavně obsahuje tzv. řídící proměnnou (celočíselnou), ve které se
postupně během běhu cyklu mění hodnoty. Syntaxe (zápis) cyklu
for je následující:
```py
for x in range(n, m)
```

Příklad - vypišme 3x "Hello World!":
```py
print("Hello World!")
print("Hello World!")
print("Hello World!")
```

Nemusíme nic otrocky opisovat:
```py
for x in range(0, 3):
    print("Hello World!")
```

Cyklus proběhne 3x, zpočátku je v proměnné i nula, cyklus
vypíše "Hello World".