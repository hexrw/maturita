---
layout: default
title: Základní metody vyhledávání a třídění
permalink: /informatika/zakladni-metody-vyhledavani-a-trideni/
---

## Vyhledávání

\*složitostí je v následujících textech myšlena [asymptotická složitost](/informatika/algoritmus-vyvojove-diagramy-deklarace-promennych/#asymptotická-složitost-algoritmu)

### Vyhledávání v poli

#### Lineární vyhledávání

*(sekvenční)*

> Nejjednodušší způsob, jak zjistit, jestli se v poli (nebo jiné datové struktuře) nachází hledaný prvek. Princip je triviální, procházíme jeden prvek po druhém a zjišťujeme, jestli to není právě ten, který hledáme. Složitost ***O(n)***.

**Využití** - Lineární vyhledávání použijeme tehdy, pokud nemáme žádné informace o uspořádání prvků struktury nebo pokud nám datová struktura (například spojový seznam) neumožňuje efektivnější způsob vyhledávání.

#### Binární vyhledávání

> Binární vyhledávání (půlení intervalu) je vyhledávací technika, která zjišťuje pozici zadaného prvku v seřazeném poli. Na rozdíl od sekvenčního vyhledávání, které vyžaduje až ***O(n)*** operací, binární vyhledávání pracuje s asymptotickou složitostí ***O(log<sub>2</sub>(n))***.

##### Princip

Mějme sestupně seřazené pole a hledejme v něm prvek ***h***. Binární vyhledávání v každém svém kroku zvolí prostřední prvek pole ***(p)*** a porovná jej s prvkem ***h***. Pokud jsou tyto prvky totožné, tak vrátí index prvku ***p***. Pokud má hledaný prvek vyšší hodnotu než ***p***, tak je zřejmé, že ***h*** se musí nacházet v levé části pole. V opačném případě ***(p > h)*** se hledaný prvek musí nacházet v pravé části pole. Binární vyhledávání proto zavolá sebe sama na příslušnou perspektivní polovinu pole.

Protože dochází v každém kroku k půlení prohledávaného intervalu (a druhá polovina se nezpracovává), tak musí dojít k nalezení (nebo vyvrácení přítomnosti) hledaného prvku nejpozději v ***log<sub>2</sub>(n)*** krocích.

#### Interpolační vyhledávání

> Vylepšení binárního vyhledávání pro případ, kdy víme, že jsou čísla v poli seřazená a rovnoměrně rozložená.

**Princip** - vychází z úvahy, že pokud máme v poli například čísla od 0 do 100 a hledáme číslo 2, tak je nerozumné pole binárně dělit (napřed se podívat na index 50, pak 25, pak 12...), je daleko rozumnějsí se podívat někam kolem indexu 2, kde by se číslo mělo nacházet (vzhledem k rovnoměrnému rozložení). Složitost tohoto přístupu je ***O(log(log(n))***.

#### Prořezávej a hledej

> Prořezávej a hledej (*Prune and search*) je typ algoritmu založený na vyřazování neperspektivních dat – redukci velikosti problému. Toto paradigma je velmi podobné algoritmům typu rozděl a panuj (*divide and conquer*), zásadní rozdíl je ovšem v tom, že při prořezávání neprocházíme všechny větve, ale pouze ty, které pro nás dávají smysl.

**Příklad** - Pokud hledáme ***n***-té nejvyšší číslo v neseřazeném poli, tak by řešením zajisté bylo pole seřadit a podívat se na zadaný index. Toto řešení ovšem není příliš efektivní. Lepším řešením je upravit například Quicksort tak, aby se po rozdělení pole dle pivota prohledávala pouze ta část, která obsahuje řešení - Quicksort v každém svém kroku umístí pivota na korektní místo v seřazeném poli, není proto problém rozhodnout, ve které části se nachází ono hledané číslo.

**Složitost** - Zatímco [asymptotická složitost](/informatika/algoritmus-vyvojove-diagramy-deklarace-promennych/#asymptotická-složitost-algoritmu) Quicksortu je ***O(n<sup>2</sup>)*** a očekáváná ***O(n \* log(n))***, tak díky eliminaci větví, které nemohou obsahovat řešení, je očekávaná složitost prune and search algoritmu ***O(c \* n)***, kde c je malá konstanta.

### Vyhledávání v textu

#### Naivní algoritmus

Slouží k vyhledání výskytu daného vzoru v textu. Prochází jak text, tak vzor zepředu a porovnává, jestli jsou totožné (na ***m*** místech vzoru). Pokud ano, tak byl výskyt nalezen, pokud ne, tak se vzorem posune o 1 místo doprava a postup se opakuje (dokud algoritmus nenarazí na konec textu). Složitost tohoto postupu je ***O(m * n)***, kde ***m*** je délka vzoru a ***n*** je délka textu.

#### Hammingova vzdálenost

Hammingova vzdálenost dvou řetězců značí, na kolika pozicích se liší. Například dvojice slov *(pes les)* má Hammingovu vzdálenost 1, protože se liší pouze v prvním znaku, dvojice *(pes luk)* má Hammingovu vzdálenost 3, protože se liší na všech 3 pozicích.

##### Vyhledávání podřetězců

Problém nalezení všech podřetězců daného textu, které mají určitou maximální Hammingovu vzdálenost od vzoru, se obvykle řeší dynamickým programováním. Jedná se o stavbu jednoduché tabulky, která má počet řádků stejný jako je délka vzoru a počet sloupců rovný délce prohledávaného textu.

Tabulka se vyplňuje následujícím způsobem. Pokud se vzor a text shodují na pozici ***(i, j)***, pak tabulka na této pozici obsahuje stejnou hodnotu, jako na pozici ***(i-1, j-1)***, v opačném případě je tato hodnota inkrementována o 1 (tato změna říká, že aby byly řetězce stejné, tak musí dojít k substituci - Hammingova vzdálenost se proto zvyšuje o 1). Řekneme, že daná pozice je výskytem vzoru, pokud je na posledním řádku odpovídajícího sloupce číslo nižší nebo rovné dané vzdálenosti.

Nyní zbývá jen říci, jaké jsou počáteční hodnoty v tabulce. Nultý sloupec tabulky obsahuje nekonečno (nebo jednodušeji hodnotu vyšší, než je maximální povolená vzdálenost), protože značí situaci, kdy ze vstupního řetězce není ještě přečten žádný znak (Hammingova vzálenost není definována pro "oříznutý" podřetězec). Nultý řádek tabulky obsahuje nuly - tímto se definuje, že budou vyhledávány výskyty na všech pozicích.

#### Levenshteinova vzdálenost

Levenshteinova vzdálenost (Levenshtein distance, editační vzdálenost) je vzdálenost dvou řetězců definovaná jako minimální počet operací vkládání, mazání a substituce takových, aby po jejich provedení byly zadané řetězce totožné. Levenshteinovu vzdálenost zavedl v roce 1965 Vladimir Levenshtein.

**Vyhledávání podřetězců** - Vyhledávání podřetězců v zadané Levenshteinově vzdálenosti funguje na principu dynamického programování, které je velmi podobné vyhledávání podřetězců v dané Hammingově vzdálenosti – jedná se o stavbu tabulky, která má stejný počet počet řádků jako má hledaný vzor písmen a počet sloupců odpovídá délce prohledávaného textu.

## Třídění

#### Bubble sort

Bubble sort (bublinkové řazení) je jednoduchý stabilní řadící algoritmem se složitostí ***O(n<sup>2</sup>)***. Vylepšením bubble sortu je <a href="#shakersort">shakersort</a> (oboustranný bubble sort).

##### Princip

Pokud si představíme řazená čísla jako bublinky, tak ty s menší hodnotou jsou lehčí než ty s vyšší hodnotou a stoupají proto ve vodě rychleji.

Obdobně postupuje také bubble sort. Porovnává dva sousední prvky, a pokud je nižší číslo nalevo od vyššího, tak je prohodí (nižší číslo je lehčí a rychleji stoupá ke konci pole) a se stejnou logikou pokračuje na dalším indexu. Pokud jsou čísla ve správném pořadí, tak je neprohodí – pouze postoupí dále (algoritmus tím našel lehčí bublinku). Na konci iterace se tímto způsobem na konec pole vždy dostane ta nejlehčí bublinka (nejnižší číslo). Nyní algoritmus můžeme pustit znovu na redukovaný problém (na poslední pozici pole je již to správné číslo).

Po ***n-1*** průchodech (poslední bublinka je seřazena triviálně) je pole seřazeno.

**Nevýhody:**
- **Problém želv a zajíců** - Zatímco se aktuálně nejlehčí bublinka může přesunout při své iteraci ve směru řazení i přes celé pole (zajíc), tak se těžké bublinky hnou v každé iteraci maximálně o jednu pozici (želvy).

**Příklad**

```js
(3 2 8 7 6) //zadání pole, řaďmě od největšího k nejmenšímu
(3 2 8 7 6) // 3 a 2 jsou v korektním pořadí, posuňme se o index
(3 2 8 7 6) // 8 > 2, prohoďme je
(3 8 2 7 6) // 7 > 2, prohoďme je (zde je vidět probublávání nejlehčí dvojky vzhůru)
(3 8 7 2 6) // 6 > 2, prohoďme je
(3 8 7 6 2) // nový průchod polem: na posledním místě je nejlehčí prvek, tudíž se nám řazená úloha o jedna zkrátila, 8 > 3, prohoďme je
(8 3 7 6 2) // 7 > 3, prohoďme je
(8 7 3 6 2) // 6 > 3, prohoďme je
(8 7 6 3 2) // seřazeno 
```

![Bubble sort](https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif)

#### Selection sort

Selection sort (řazení výběrem) je jednoduchý nestabilní řadící algoritmus se složitostí ***O(n<sup>2</sup>)***. V porovnání s dalšími kvadratickými algoritmy je selection sort v obecném případě rychlejší než bubble sort, avšak pomalejší než <a href="#insertion-sort">insertion sort</a>. Výhodou selection sortu oproti algoritmům s asymptotickou složitostí ***O(n \* log(n))*** (<a href="#quicksort">quicksort</a>, <a href="#merge-sort">merge sort</a>, <a href="#heapsort">heapsort</a>) je jeho konstantní paměťová složitost.

**Princip** - Selection sort vychází z myšlenky, že pokud řadíme pole od největšího prvku k nejmenšímu, tak první bude nejvyšší prvek, za ním nejvyšší prvek ze zbytku pole atd., čili stačí pouze postupně vybírat nejvyšší prvky z neseřazené části pole a umísťovat je na konec seřazené části.

**Příklad**

```js
(3 2 8 7 6) // zadání pole, řaďmě od největšího k nejmenšímu
(3 2 8 7 6) // nejvyšší číslo je 8, prohoďme ho tedy s číslem 3 na indexu 0
(8 2 3 7 6) // nejvyšší číslo je 7, prohoďme ho tedy s číslem 2 na indexu 1
(8 7 3 2 6) // nejvyšší číslo je 6, prohoďme ho tedy s číslem 3 na indexu 2
(8 7 6 2 3) // nejvyšší číslo je 3, prohoďme ho tedy s číslem 2 na indexu 3
(8 7 6 3 2) // seřazeno 
```

![Selection sort](https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif)

#### Insertion sort

Insertion sort (řazení vkládáním) je stabilní řadící algoritmus založený na principu porovnávání řazených hodnot se složitostí ***O(n<sup>2</sup>)***. Vylepšením Insertion sortu je výkonnější, ale nestabilní, <a href="#shell-sort">shell sort</a>. 

**Princip** - Insertion sort využívá tohoto myšlenkového postupu:
- Mějmě jeden prvek, ten je triviálně seřazen.
- Vezměme následující prvek a zařaďme jej na správné místo v již seřazených prvcích. (Tímto je nyní seřazeno o jeden prvek více než v předchozím kroku.)
- Dokud pole obsahuje nezařazené prvky, tak **GOTO: 2**.

**Výhody Insertion sortu** - Ač se jedná o řazení se složitostí ***O(n<sup>2</sup>)***, tak se u téměř seřazeného pole jeho složitost blíží k ***O(n)*** – nedochází k posunům, pouze k průchodu. Díky k této výkonnostní výhodě je insertion sort a jeho modifikace často používán jako doplněk k řadícím algoritmům typu rozděl a panuj (quicksort, merge sort) pro řazení malých polí (pro ***n &le; 10*** je insertion sort rychlejší než quicksort).

**Příklad**

```js
(3 2 8 7 6) // Zadání, prvek 3 je triviálně seřazen
(3 2 8 7 6) // Vezmeme dvojku a vložíme jí na správné místo (tam už je)
(3 2 8 7 6) // 8 vložíme na první místo, zbytek čísel posuneme
(8 3 2 7 6) // 7 vložíme mezi 8 a 3, 3 a 2 posuneme
(8 7 3 2 6) // 6 vložíme mezi 7 a 3, čísla 3 a 2 posuneme
(8 7 6 3 2) // seřazeno 
```

![Insertion sort](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

#### Quicksort

Quicksort je velmi rychlý nestabilní řadící algoritmus na principu *Divide et Impera* (rozděl a panuj) s asymptotickou složitostí ***O(n<sup>2</sup>)*** a s očekávanou složitostí ***O(n \* log(n))***.

**Princip** - Zvolme v zadaném poli libovolný prvek a říkejme mu pivot. Nyní můžeme pole přeházet tak, aby na jedné straně byly prvky větší než pivot, na druhé menší než pivot a pivot samotný byl umístěn přesně mezi těmito částmi. Tento postup můžeme zopakovat pro obě rozdělené části (bez pivota, ten je již umístěn na správném místě). Proceduru opakujeme tak dlouho, dokud nenarazíme na všechny triviálně řešitelné podproblémy (pole velikosti 1). V tento okamžik je celé pole seřazeno od nejvyššího prvku.

![Quicksort](https://algoritmy.net/image/id/1206)

**Výkonnost quicksortu** je dána především volbou dobrého pivota. Pokud jej volíme ideálně, tak dojde při každém rekurzívním volání k rozpůlení pole a vystačíme si tedy s ***log<sub>2</sub>(n)*** voláními, v nichž popřehazujeme až n prvků. Složitost tohoto případu je proto ***O(n \* log<sub>2</sub>(n))***.

Na druhou stranu, **pokud** nemáme štěstí a **pivota volíme špatně** (tj. nejvyšší nebo nejnižší možný prvek), tak nedojde k žádnému dělení podproblému, pouze dojde vždy k zařazení pivota na správné místo. Při každém z n volání procedury spotřebujeme až n operací na ověření pořadí, případně na přesun prvků. Složitost tohoto patologického případu je proto ***O(n<sup>2</sup>)***.

##### Volba pivota

Pro volbu pivota existuje mnoho strategií. Jednou z nich je volba fixního prvku (tj. prvního, posledního...). Tento postup je problematický na částečně uspořádaných polích, případně na polích s nějakou strukturou, kde nedochází k optimálnímu dělení problému a složitost narůstá až k ***n<sup>2</sup>***. Tomuto chování se lze vyhnout volbou mediánu prvního, posledního a prostředního prvku řazeného úseku pole.

Druhou populární strategii je volba náhodného prvku. Zde je problémem již zajištění samotné náhodnosti volby, respektive opakující se vzory v chování generátoru čísel (v extrémním případě může strategie degradovat až k poněkud komplikovanější volbě fixního prvku). V praxi se ale ukazuje, že bohatě postačí i pseudonáhodné generátory.

![Quicksort](https://upload.wikimedia.org/wikipedia/commons/6/6a/Sorting_quicksort_anim.gif)

#### Merge sort

Mergesort je stabilní řadicí algoritmus typu rozděl a panuj s asymptotickou složitostí ***O(n \* log(n))***. Merge sort pracuje na bázi slévání již seřazených částí pole za pomoci dodatečného pole velikosti n.

**Operace:**

- **Slévání (merge)** dvou seřazených polí do jednoho pole
    - Slévá vždy dvě sousední části pole. Drží si dva ukazatele, každý na první prvek seznamu a po každém porovnání přesune jeden z prvků do pomocného pole a posune příslušný ukazatel o jedno místo (címž se dostane na nový nejvyšší prvek příslušného seznamu). Poté, co zkopíruje všechny prvky obou seznamů do pomocného pole, tak celé původní pole přepíše seřazeným seznamem (pomocným polem).
- **Dělení** - Dosud jsme nezmínili, jak algoritmus získá dvě seřazená sousední pole. Dělicí část merge sortu má na svém vstupu celé pole. Pokud je pole sudé délky, tak jej rozdělí na dvě stejně velké části. Má-li pole lichou délku, tak bude jedna část obsahovat o prvek více než druhá. V každém případě pak algoritmus nově vzniklé části dále rekurzivně dělí. V okamžiku, kdy rekurze narazí na seznamy jednotkové velikosti, tak se zastaví. Nyní má algorimus v každé větvi k dispozici dva sousední seznamy, které obsahují jeden prvek a jsou tedy triviálně seřazeny.
- **Řazení** - Merge sort se tedy začne navracet z rekurze a při každém návratu sleje dva seznamy pomocí výše zmíněné procedury slévání. Algoritmus má jistotu, že buď slévá triviálně seřazené prvky nebo seznamy, které již byly slity. V okamžiku, kdy se merge sort plně navrátí z rekurze, tak terminuje. Pole je seřazeno od nevyšší hodnoty.

![Merge sort](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif)

#### Heapsort

Heapsort (řazení haldou) je jedním z nejefektivnějších řadících algoritmů založených na porovnávání prvků s asymptotickou složitostí ***O(n \* log(n))***. Jelikož je tato složitost zaručená, tak je heapsort vhodnější pro použití v real-time systémech než v průměrném případě rychlejší quicksort, jenž však může dosahovat složitosti v nejhorším případě až O(n^{2}).

Základem heapsortu je binární halda, jejíž základní vlastností je, že se chová jako prioritní fronta. Pokud z prioritní fronty postupně odebíráme prvky, tak je zřejmé, že tím dochází k jejich řazení. **Celý postup se skládá z následujících kroků:**

1. Postavme haldu nad zadaným polem.
2. Utrhněme vrchol haldy (prvek s nejvyšší prioritou - nejvyšší nebo nejnižší prvek dle způsobu řazení).
3. Prohoďme utržený prvek s posledním prvkem haldy.
4. Zmenšeme haldu o 1 (prvky řazené dle priority na konci pole jsou již seřazené).
5. Opravme haldu tak, aby splňovala požadované vlastnosti (přestaly platit v momentě prohození prvků).
6. Dokud má halda prvky **GOTO: 2**.
7. Pole je seřazené v opačném pořadí, než je priorita prvků.

![Heapsort](https://upload.wikimedia.org/wikipedia/commons/4/4d/Heapsort-example.gif)

#### Shaker sort

Shaker sort (shake sort, cocktail sort) je stabilní řadící algoritmus s asymptotickou složitostí ***O(n<sup>2</sup>)***. Shakersort je vylepšením <a href="#bubble-sort">bubble sortu</a>, narozdíl od něj neřadí pole pouze jedním směrem, ale oběma. Každá iterace algoritmu se tedy skládá z dvou fází - při dopředné stoupá nejlehčí bublinka vzhůru, pří zpětné klesá nejtěžší bublinka ke dnu. Tímto postupem se předejde nedostatku bubble sortu tzv. problému želv a zajíců, který spočívá v tom, že vysoké hodnoty probublají na konec pole rychle, ale ty nízké postupují na začátek velmi pomalu.

#### Counting sort

Counting sort (ultra sort, math sort) je výkonný stabilní řadící algoritmus se složitostí ***O(n + k)***. Counting sort nepracuje narozdíl od bubble sortu nebo quicksortu na principu porovnávání jednotlivých hodnot, ale na bázi výčtu jejich výskytů.

##### Princip

Counting sort využívá znalosti maximální a minimální řazené hodnoty . Díky může vytvořit pole četností hodnot (kolikrát je daná hodnota zastoupena v řazeném poli) a toto pole posléze přepočítat na pole posledních indexů (index i značí pozici posledního výskytu daného prvku v seřazeném poli).

Řazení probíhá jedním průchodem řazeného pole (zprava doleva) a ukládáním hodnot na správné místo v seřazeném poli (které známe díky poli indexů).

**Výhody:**
- složitost ***O(n+k)***, kde ***n*** je velikost řazeného pole a ***k*** je velikost pole indexů (rozsah různých hodnot)

**Nevýhody:**
- v případě řazení struktur potřebuje ke své práci nejen pomocné pole indexů, ale také dodatečné pole
- dají se ním řadit pouze diskrétní hodnoty (tj. nelze s ním řadit například reálná čísla)

#### Radix sort

Radix sort (přihrádkové řazení) je stabilní řadící algoritmus používaný především k **řazení řetězců totožné délky**. Asymptotická složitost radix sortu je ***O(m \* C(n))***, kde ***m*** je počet znaků řazených řetězců, ***n*** je velikost dat a ***C(n)*** je složitost vnitřního stabilního řadícího algoritmu (za tímto účelem je často použit counting sort).

Princip radix sortu vychází přímo z definice stabilního řazení – řadicí algoritmus je stabilní, pokud zachovává pořadí klíčů, které mají stejnou hodnotu (tj. pokud stuktury seřadíme napřed dle klíče **A**, poté podle klíče **B**, tak jsou seřazeny podle **B**, a kde jsou si hodnoty **B** rovny, tam jsou struktury v pořadí daném klíčem **A**).

Radix sort řadí řetězce totožné délky tak, že nad každým znakem od konce těchto řetězců zavolá stabilní řadicí algoritmus (seřadí řetězce podle posledního znaku, poté podle předposledního...). Po ***n***-tém průchodu jsou řetězce seřazeny dle všech pozic znaků.

#### Bucket sort

*(bin sort)*

Stabilní řadicí algoritmus založení na rozdělení vstupního pole do několika částí – **bucketů** (přihrádek) – a seřazení těchto částí pomocí jiného stabilního řadicího algoritmu. Složitost bucket sortu je ***O(m \* C(n/m))***, kde ***m*** je počet přihrádek, ***n*** je velikost vstupního pole a ***C(x)*** je složitost vnitřního řadicího algoritmu.

**Princip:**
1. Rozdělí vstupní pole do několika bucketů. Každý bucket reprezentuje určitý rozsah vstupních dat – data by měla být v optimálním případě rovnoměrně rozdělena, aby nedocházelo k situaci, kdy je jedna bucket přeplněn a další je prázdný.
2. Zavolá na každý z bucketů stabilní řadicí algoritmus, případně rekurzivně sám sebe.
3. Nakopíruje postupně všechny seřazené buckety do výstupního pole.

**Využití** - Bucket sort se dá využít pro řazení obrovských dat, která by nemohl načíst klasický ***O(n \* log(n))*** algoritmus najednou.

#### Shell sort

Kvadratický řadící algoritmus podobný <a href="#insertion-sort">insertion sortu</a>. Ačkoliv má složitost ***Ο(n<sup>2</sup>)***, je z algoritmů této třídy nejvýkonnější.

Shell sort využívá tzv. snižující se přírůstek. Neřadí prvky, které jsou přímo vedle sebe, ale prvky, mezi nimiž je určitá mezera (tj. první a pátý, pátý a devátý, druhý a šestý...). V každém kroku je pak mezera mezi prvky zmenšena. V okamžiku, kdy se velikost mezery sníží na 1, dojde k řazení sousedních prvků – algoritmus degeneruje na běžný <a href="#insertion-sort">insertion sort</a>.

**Výhody:**
- asymptotická složitost ***Ο(n<sup>2</sup>)***, ale v praxi je rychlejší než insertion sort
- prvky vysokých a nízkých hodnot velmi rychle přemístěny na odpovídající stranu pole

**Nevýhody:**
- problém volby ideální vzdálenosti pro porovnávání jednotlivých prvků

![Shell sort](https://upload.wikimedia.org/wikipedia/commons/d/d8/Sorting_shellsort_anim.gif)

#### Bogosort

*(stupid sort, slowsort)*

Slouží k demonstraci nejhoršího možného postupu při řazení prvků. Jedná se pouze o teoretický algoritmus, jenž nemá kromě demonstrace samotné žádné praktické uplatnění. Princip je triviální – v každém svém kroku zkontroluje, jestli vstupní seznam není již seřazený. Pokud je seřazen, tak terminuje. V opačném případě promíchá seznam a vrátí se do prvního kroku. Složitost je ***O(n!)***, což je největší možná složitost.

#### Comb sort

Comb sort je řadicí algoritmus, který lze považovat za vylepšení bubble sortu. Ačkoliv má, stejně jako bubble sort, kvadratickou asymptotickou složitost ***O(n<sup>2</sup>)***, tak je díky eliminaci problému želv a zajíců v praxi rychlejší.

Obdobně jako Shell sort zavádí do řazení tzv. snižující se přírůstek. To znamená, že v každé iteraci jsou porovnávány prvky mezi nimiž je určitý přírůstek (1. se 4., 2. s 5., 3. se 6. atp.). Přírůstek se s každou iterací postupně snižuje, dokud není 1 (poslední iterace). Jednotkový přírůstek značí, že dojde k degradaci na prostý <a href="#bubble-sort">bubble sort</a> – tj. jsou porovnávány sousední prvky. Díky tomuto jednoduchému triku se mohou v úvodních iteracích i těžké prvky – želvy – velmi rychle přesunout na správnou stranu pole.

**Volba správné mezery** - Velmi dobré výsledky dává mezera, která se vypočte postupným dělením délky pole číslem ***4/3***.

![Comb sort](https://upload.wikimedia.org/wikipedia/commons/4/46/Comb_sort_demo.gif)

#### DropSort

Rychlý řadící algoritmus s jedním průchodem, vhodný pro různá nasazení. Spouští se na řazení seznamu čísel, které prozkoumává v sekvenci, počínaje druhým číslem ze seznamu. Pokud je číslo menší než předcházející, pak jej ze seznamu odstraní. V opačném případě je ve správném pořadí, takže jej ponechá. Pak se přesune na další číslo. Po jednom průchodu algoritmem obsahuje seznam pouze čísla, která jsou alespoň tak velká jako předchozí číslo v seznamu, tedy je setříděn. Složitost ***O(n)***.

#### Block Merge Sort

*(WikiSort)*

Rychlý a stabilní ***O(n \* log(n))*** řadící algoritmus, který používá ***O(1)*** paměti.

Algoritmus je ještě rychlejší, je-li vstup částečně setříděn, nebo může-li použít větší pole. Může být také modifikován tak, aby použil další dodatečnou paměť a tím zvýšil svou rychlost.

Block Merge Sort jak název napovídá se skládá z rozložení daného seznamu prvků do bloků, jejich setřídění a následnému slévání zpět. Aby dosáhl složitosti ***O(n \* log(n))***, kombinuje vždy alespoň 2 operace Merge sort a Insertion sort. Své jméno tedy dostal z porovnání dvou setříděných seznamů **A** a **B**, což je ve skutečnosti ekvivalentní rozložení seznamu **A** na rovnoměrné části nazývané Bloky, vložení každého bloku **A** do **B** dle speciálních pravidel a slévání (merge) párů **AB** (sort).

**Výhody:**
- nevyžaduje dodatečnou počítačovou paměť

**Nevýhody:**
- nevyužívá řazených rozsahů tak efektivně jako jiné algoritmy
