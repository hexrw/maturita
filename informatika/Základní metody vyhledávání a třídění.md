---
layout: default
title: Základní metody vyhledávání a třídění
permalink: /informatika/zakladni-metody-vyhledavani-a-trideni/
---

## Vyhledávání

### Vyhledávání v poli

#### Lineární vyhledávání

> Lineární (sekvenční) vyhledávání je nejjednodušším způsobem, jak zjistit, jestli se v poli (nebo jiné datové struktuře) nachází námi hledaný prvek. Princip je zcela triviální, procházíme jeden prvek po druhém a zjišťujeme, jestli to není právě ten, který hledáme. Z tohoto vyplývá složitost tohoto postupu - ***O(n)***.

**Využití** - Lineární vyhledávání použijeme tehdy, pokud nemáme žádné informace o uspořádání prvků struktury nebo pokud nám datová struktura (například spojový seznam) neumožňuje efektivnější způsob vyhledávání.

#### Binární vyhledávání

> Binární vyhledávání (půlení intervalu) je vyhledávací technika, která zjišťuje pozici zadaného prvku v seřazeném poli. Na rozdíl od sekvenčního vyhledávání, které vyžaduje až O(n) operací, binární vyhledávání pracuje s asymptotickou složitostí ***O(log<sub>2</sub>(n))***.

##### Princip

Mějme sestupně seřazené pole a hledejme v něm prvek h. Binární vyhledávání v každém svém kroku zvolí prostřední prvek pole ***(p)*** a porovná jej s prvkem h. Pokud jsou tyto prvky totožné, tak vrátí index prvku p. Pokud má hledaný prvek vyšší hodnotu než ***p***, tak je zřejmé, že h se musí nacházet v levé části pole. V opačném případě ***(p > h)*** se hledaný prvek musí nacházet v pravé části pole. Binární vyhledávání proto zavolá sebe sama na příslušnou perspektivní polovinu pole.

Protože dochází v každém kroku k půlení prohledávaného intervalu (a druhá polovina se nezpracovává), tak musí dojít k nalezení (nebo vyvrácení přítomnosti) hledaného prvku nejpozději v ***log<sub>2</sub>(n)*** krocích.

#### Interpolační vyhledávání

> Interpolační vyhledávání je vylepšením binárního vyhledávání pro případ, kdy víme, že jsou čísla v poli nejen seřazená, ale také rovnoměrně rozložená.

**Princip** - Interpolační vyhledávání vychází z úvahy, že pokud máme v poli například čísla od 0 do 100 a hledáme číslo 2, tak je přinejmenším nerozumné pole binárně dělit (napřed se podívat na index 50, pak 25, pak 12...), ale je daleko rozumnějsí se podívat někam kolem indexu 2, kde by se číslo mělo nacházet (vzhledem k rovnoměrnému rozložení). Složitost tohoto přístupu je ***O(log(log(n))***.

#### Prořezávej a hledej

> Prořezávej a hledej (*Prune and search*) je typ algoritmu založený na vyřazování neperspektivních dat – redukci velikosti problému. Toto paradigma je velmi podobné algoritmům typu rozděl a panuj (*divide and conquer*), zásadní rozdíl je ovšem v tom, že při prořezávání neprocházíme všechny větve, ale pouze ty, které pro nás dávají smysl.

**Příklad** - Pokud hledáme n-té nejvyšší číslo v neseřazeném poli, tak by řešením zajisté bylo pole seřadit a podívat se na zadaný index. Toto řešení ovšem není příliš efektivní. Lepším řešením je upravit například Quicksort tak, aby se po rozdělení pole dle pivota prohledávala pouze ta část, která obsahuje řešení - Quicksort v každém svém kroku umístí pivota na korektní místo v seřazeném poli, není proto problém rozhodnout, ve které části se nachází ono hledané číslo.

**Složitost** - Zatímco [asymptotická složitost](/informatika/algoritmus-vyvojove-diagramy-deklarace-promennych/#asymptotická-složitost-algoritmu) Quicksortu je ***O(n<sup>2</sup>)*** a očekáváná ***O(n \* log(n))***, tak díky eliminaci větví, které nemohou obsahovat řešení, je očekávaná složitost prune and search algoritmu ***O(c \* n)***, kde c je malá konstanta.

### Vyhledávání v textu

#### Naivní algoritmus

#### Hammingova vzdálenost

#### Levenshteinova vzdálenost

## Třídění

#### Bubble sort


#### Selection sort


#### Insertion sort


#### Quicksort


#### Merge sort


#### Heapsort


#### Shaker sort


#### Counting sort


#### Radix sort


#### Bucket sort


#### Shell sort


#### Bogosort


#### Comb sort


#### DropSort


#### Block Merge Sort


