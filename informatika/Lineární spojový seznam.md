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

U spojových seznamů jsme přišli o možnost rychle přistoupit k prvku
podle jeho indexu a to kvůli tomu, že prvky již nejsou v paměti za sebou.
Neexistuje způsob, jak efektivně přeskočit rovnou např. na 100. prvek a
přečíst jeho hodnotu. Když chceme k 100. prvku přistoupit, musíme z
prvního prvku na druhý, z druhého na třetí a tak dále až do stovky.
Časová složitost čtení a zápisu na index tedy záleží na počtu
prvků v listu.

Někdy však nepotřebujeme prvky indexovat a v tu chvíli se tato kolekce
stává velmi výhodnou. Již na začátku jsme si řekli, že s polem vůbec
nepracujeme. Již nejsme nijak omezeni délkou seznamu a položky můžeme za
běhu programu přidávat a mazat tak dlouho, dokud nám bude stačit paměť.
Poměrně dobře můžeme i mazat prvky uprostřed seznamu nebo vkládat nové
prvky mezi existující. U pole bylo vložení prvku možné pouze tak, že jsme
všechny prvky napravo posunuli a vytvořili tak místo pro nový prvek. To nás
stálo nemalý výpočetní čas, který byl závislý na počtu prvků.
Ve spojovém seznamu nový prvek pouze naodkazujeme mezi 2 existující,
ostatních prvků se změna nedotkne.

Máme tedy efektivní vkládání a mazání prvků na úkor
neefektivního přístupu na indexy. Tak už to u datových struktur a
algoritmů bývá, něco za něco.

Vidíme, že spojový seznam a seznam přes pole se velmi liší. Pokud
budeme často přistupovat k prvkům pomocí indexu, byl by spojový seznam
katastrofou. Pokud budeme naopak prvky často vkládat nebo mazat uprostřed
kolekce, spojový seznam si s tím hravě poradí a list s polem by byl
extrémně pomalý.

| Operace                 | Složitost   |
|------------------------:|-------------|
| Najdi prvek             | O(n)        |
| Přidej prvek na začátek | O(1)        |
| Přidej prvek na konec   | O(1)\*      |
| Přidej prvek někam      | O(n)        |
| Smaž prvek              | O(n)        |
| Smaž začátek            | O(1)        |
| Najdi následníka        | O(n)        |
| Najdi předka            | nemožné\*\* |

\*Pokud si držíme informaci o tom, kde je konec, jinak O(n).

\*\*Samozřejmě nic nebrání tomu, abyste si do této struktury přidali další pointer na svého předka. Tím pádem z jednoduchého seznamu uděláte obousměrný a množina operací se ještě zvýší, např. "najdi předka".

### Nebezpečí

Má to ale háček, pointery samostatné. Jsou vynikajícím nástrojem pro programátora, ale jsou natolik silné, že můžou natropit pořádnou paseku. Asi jako byste si chtěli krájet chleba motorovou pilou. V moderních jazycích jako např. Java proto pointery nejsou, jsou tu pouze tzv. reference. Reference je něco jako pointer, ale vy s tím pointerem nemůžete přímo pracovat a tím způsobit např. poškození jiné části paměti. Více o pointerech se dozvíme v seriálu Principy fungování počítačů.

Spojový seznam se často používá pro implementaci datových struktur
fronty a zásobníku.

----------------

**Zdroje**

- [https://www.itnetwork.cz/algoritmy/datove-struktury/spojovy-seznam](https://www.itnetwork.cz/algoritmy/datove-struktury/spojovy-seznam)
