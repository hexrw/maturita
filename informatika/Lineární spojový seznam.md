---
layout: default
title: Lineární spojový seznam
permalink: /informatika/linearni-spojovy-seznam/
---

Seznam (list), do kterého lze na rozdíl od pole přidávat prvky nebo z
něj prvky mazat, můžeme implementovat pomocí obyčejného pole, ve kterém
jednoduše jen necháme dostatek volného místa.

Druhou možností vytvoření seznamu s proměnným počtem prvků jsou tzv.
spojové seznamy. Ty již s polem vůbec nepracují a jsou založené na
odlišném principu. Jednotlivé prvky v listu jsou v paměti různě
rozházené (již tedy nejsou uložené za sebou) a po sobě jdoucí prvky na
sebe odkazují. Můžeme si to představit jako takový řetězec, kdy 1. prvek
ukazuje na druhý, druhý na třetí a tak dále.

![LSS 1](/assets/lss-1.png)

Takovému spojovému seznamu se říká jednosměrný (Singly Linked List).
Pokud nemáme nějaký vážný důvod šetřit pamětí, obvykle na sebe 2 po
sobě jdoucí prvky ukazují navzájem (tedy i 2. na první a tak dále).
Hovoříme o obousměrném spojovém seznamu (Doubly Linked List). Ten by v
našem případě vypadal nějak takto:

![LSS 2](/assets/lss-2.png)
