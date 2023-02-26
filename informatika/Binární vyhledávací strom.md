---
layout: default
title: Binární vyhledávací strom
permalink: /informatika/binarni-vyhledavaci-strom/
---

Binární vyhledávací strom (BST – z angl. Binary Search Tree) je datová struktura založená na binárním stromu, v němž jsou jednotlivé prvky (uzly) uspořádány tak, aby v tomto stromu bylo možné rychle vyhledávat danou hodnotu. To zajišťují tyto vlastnosti:

- Jedná se o binární strom, každý uzel tedy má nanejvýš dva potomky – levého a pravého.
- Každému uzlu je přiřazen určitý klíč. Podle hodnot těchto klíčů jsou uzly uspořádány.
- Levý podstrom uzlu obsahuje pouze klíče menší než je klíč tohoto uzlu.
- Pravý podstrom uzlu obsahuje pouze klíče větší než je klíč tohoto uzlu.

Hlavní výhodou binárních vyhledávacích stromů je vysoká efektivita vyhledávání hodnot v nich, byť proti hašovací tabulce je pomalejší. Lze je využít při dobré implementaci také k efektivnímu řazení hodnot – in-order průchod binárním vyhledávacím stromem vydá seznam uložených hodnot uspořádaný podle velikosti. Ale důležitější jsou na tom postavené intervalové dotazy a průběžné udržování uspořádaných klíčů, protože řadit na místě, tj. efektivněji, umí spousta jiných algoritmů.

Binární vyhledávací stromy jsou zásadní datovou strukturou při konstrukci daleko abstraktnějších datových struktur jako jsou množiny, multimnožiny a asociativní pole.

Pokud BST neumožňuje duplicity hodnot, pak se jedná o strom s unikátními hodnotami, stejně jako matematická množina. Stromy bez duplicit využívají ostrou nerovnost, tedy hodnoty uzlů levého podstromu jsou menší než je hodnota uzlu a pravý podstrom obsahuje pouze hodnoty větší než je hodnota uzlu.

Pokud BST umožňuje duplicity hodnot, pak představuje multimnožinu. Tento typ stromu využívá neostrou nerovnost. Všechny hodnoty uzlů v levém podstromu uzlu jsou menší než je hodnota uzlu, ale všechny hodnoty v pravém podstromu jsou buď větší, nebo shodné s hodnotou uzlu.

Uložení duplicitních hodnot právě v pravém podstromu není povinné. Stejně tak je lze uchovávat i v levém podstromu. Lze též užít neostrou nerovnost v obou podstromech, což usnadní vyvážení stromu obsahujícího mnoho duplicit, ale utrpí efektivita vyhledávání.

Strom se mnohem častěji než na množiny a multimnožiny používá pro asociativní paměť (nepřesně asociativní pole), kde se podle klíče hledá přidružená hodnota. Vyhledávací stromy (včetně nebinárních) mají mnoho implementačních variant (majících vlastní jména a články) případně i s lepšími vlastnostmi. Na druhé straně pro asociativní pole se dají použít i jiné konkrétní datové struktury.

BST Vyhledávací stromy slouží jako ideový základ pro konstrukci složitějších vyhledávacích datových struktur, konkrétně pro složené klíče a dotazy s částečně zadanými klíči.

Složitost operací je, zjednodušeně řečeno, při dobré implementaci logaritmická a obecně lineární vzhledem k počtu reprezentovaných prvků.

### Binární vyhledávání

Stejně jako minule máme obrovské pole setříděných záznamů, třeba identifikačních čísel studentů nejmenované univerzity (záznamy však nemusí být čísla, stačí, když jsou navzájem porovnatelné). Naším úkolem je najít záznam z v poli s N záznamy x1 < x2 < … < xN.

Při použití binárního vyhledávání neboli půlení intervalu se podíváme na prostřední záznam xm a porovnáme s ním naše z. Pokud z&gt;xm, víme, že se z nemůže vyskytovat „napravo“ od xm, protože tam jsou všechny záznamy větší než xm, a tím spíše než z. Analogicky pokud z&lt;xm, nemůže se z vyskytovat v první polovině pole. V obou případech nám zbude jedna polovina a v ní budeme pokračovat stejným způsobem. Tak budeme postupně půlit interval, ve kterém se z může nacházet, až buďto z najdeme, nebo vyloučíme všechny prvky, kde by mohlo být.

Tento algoritmus můžeme naprogramovat buďto rekurzivně, nebo pomocí cyklu, v němž si budeme udržovat interval &gt;l,r&lt;, ve kterém se hledaný prvek ještě může nacházet. My si ukážeme přístup s cyklem:

```py
def bin_najdi(z):
    levy = 0
    pravy = N
    while levy <= pravy:
        median = (levy+pravy)/2
        # hledaná hodnota je vlevo
        if z < x[median]:
        pravy = median - 1
        # je vpravo
        elif z > x[median]:
        levy = median+1
        # našli jsme přímo hodnotu
        else:
        return median
        # hledaná hodnota nebyla nikde
        return -1
```

Samozřejmě bychom při vyhledávání záznamu mohli být ještě chytřejší. Víme-li třeba, že čísla jsou z rozsahu 1 až 1000 a dostaneme číslo 900, můžeme se napřed podívat do devíti desetin pole místo do poloviny. Obecně se tedy snažíme odhadovat, kde bude záznam v rámci pole podle jeho hodnoty. Tomuto přístupu se říká interpolační vyhledávání a v průměru je lepší než binární (průměrná časová složitost je O(log log N)), byť v nejhorším případě je lineární.

Binární vyhledávání je velmi rychlé, pokud máme možnost si data předem setřídit. Jakmile ale potřebujeme za běhu programu přidávat a odebírat záznamy, se zlou se potážeme. Buďto budeme mít záznamy uložené v poli a pak nezbývá než při zatřiďování nového prvku ostatní „rozhrnout“, což může trvat až N kroků, anebo si je budeme udržovat v nějakém seznamu, do kterého dokážeme přidávat v konstantním čase, jenže pak pro změnu nebudeme při vyhledávání schopni najít tolik potřebnou polovinu.

Zkusme ale provést jednoduchý myšlenkový pokus:

### Vyhledávací stromy

Představme si, jakými všemi možnými cestami se může v našem poli binární vyhledávání ubírat. Na začátku porovnáváme s prostředním prvkem a podle výsledku se vydáme jednou ze dvou možných cest (nebo rovnou zjistíme, že se jedná o hledaný prvek, ale to není moc zajímavý případ). Na každé cestě nás zase čeká porovnání se středem příslušného intervalu a to nás opět pošle jednou ze dvou dalších cest atd. To si můžeme přehledně popsat pomocí stromu:

![Vyhledávací strom 1](/assets/binarni-vyhledavaci-strom.png)

Jeden vrchol stromu prohlásíme za kořen a ten bude odpovídat celému poli (a jeho prostřednímu prvku). K němu budou připojené vrcholy obou polovin pole (opět obsahující příslušné prostřední prvky) a tak dále. Ovšem jakmile známe tento strom, můžeme náš půlící algoritmus provádět přímo podle stromu (ani k tomu nepotřebujeme vidět původní pole a umět v něm hledat poloviny): začneme v kořeni, porovnáme a podle výsledku se buďto přesuneme do levého, nebo pravého podstromu, a tak dále. Každý průběh algoritmu bude tedy odpovídat nějaké cestě z kořene stromu do hledaného vrcholu.

Teď si ale všimněte, že aby hledání hodnoty podle stromu fungovalo, strom vůbec nemusel vzniknout půlením intervalu – stačilo, aby v každém vrcholu platilo, že všechny hodnoty v levém podstromu jsou menší než tento vrchol a naopak hodnoty v pravém podstromu větší. Hledání v témže poli by také popisovaly následující stromy (např.):

![Vyhledávací strom 2](/assets/binarni-vyhledavaci-strom-2.png)

Hledací algoritmus podle jiných stromů samozřejmě už nemusí mít pěknou logaritmickou složitost (kdybychom hledali podle „degenerovaného“ stromu z pravého obrázku, trvalo by to dokonce lineárně). Důležité ale je, že takovéto stromy se dají poměrně snadno modifikovat a že je při troše šikovnosti můžeme udržet dostatečně podobné ideálnímu půlení intervalu. Pak bude hloubka stromu stále O(log N), tím pádem i časová složitost hledání, a jak za chvilku uvidíme, i mnohých dalších operací.

### Definice

Zkusme si tedy pořádně nadefinovat to, co jsme právě vymysleli:

Binární vyhledávací strom (podomácku BVS) je buď prázdná množina, nebo kořen obsahující jednu hodnotu a mající dva podstromy (levý a pravý). Tyto podstromy jsou opět BVS, ovšem takové, že všechny hodnoty uložené v levém podstromu jsou menší než hodnota v kořeni, a ta je naopak menší než všechny hodnoty uložené v pravém podstromu.

Úmluva: Pokud x je kořen a Lx a Rx jeho levý a pravý podstrom, pak kořenům těchto podstromů (pokud nejsou prázdné) budeme říkat levý a pravý syn vrcholu x a naopak vrcholu x budeme říkat otec těchto synů. Pokud je některý z podstromů prázdný, pak vrchol x příslušného syna nemá. Vrcholu, který nemá žádné syny, budeme říkat list vyhledávacího stromu. Všimněte si, že pokud x má jen jediného syna, musíme stále rozlišovat, je-li to syn levý, nebo pravý, protože potřebujeme udržet správné uspořádání hodnot. Také si všimněte, že pokud známe syny každého vrcholu, můžeme již rekonstruovat všechny podstromy.

Každý BVS také můžeme popsat velmi jednoduchou strukturou v paměti:

```py
class Vrchol:
    self.levy = None
    self.pravy = None
    self.x = None
```

Pokud některý ze synů neexistuje, zapíšeme do příslušné položky hodnotu NULL.

### Hledání

V řeči BVS můžeme přeformulovat náš vyhledávací algoritmus takto:

```py
# Dostane kořen stromu a hodnotu. Vrátí vrchol,
# ve kterém se hodnota nachází, nebo None, když
# ve stromu není.
def strom_najdi(vrchol, x):
    while (v != None) and (vrchol.x != x):
        if x < vrchol.x:
            vrchol = vrchol.levy
        else:
            vrchol = vrchol.pravy
        return vrchol
```

Funkce strom_najdi bude pracovat v čase O(h), kde h je hloubka stromu, protože začíná v kořeni a v každém průchodu cyklem postoupí o jednu hladinu níže.

### Vkládání

Co kdybychom chtěli do stromu vložit novou hodnotu (aniž bychom se teď starali o to, zda tím strom nemůže degenerovat)? Stačí zkusit hodnotu najít, a pokud tam ještě nebyla, určitě při hledání narazíme na odbočku, která je NULL. A přesně na toto místo připojíme nově vytvořený vrchol, aby byl správně uspořádán vzhledem k ostatním vrcholům (že tomu tak je, plyne z toho, že při hledání jsme postupně vyloučili všechna ostatní místa, kde nová hodnota být nemohla). Naprogramujeme opět snadno, tentokráte si ukážeme rekurzivní zacházení se stromy:

```py
# Dostane kořen stromu a hodnotu ke vložení,
# vrátí nový kořen
def strom_vloz(vrchol, x):
    # prázdný strom
    if vrchol is None:
        # založíme nový kořen
        vrchol = Vrchol()
        vrchol.levy = None
        vrchol.pravy = None
        vrchol.x = x
    elif x < vrchol.x
        # vkládáme vlevo
        vrchol.levy = strom_vloz(vrchol.levy, x)
    elif x > vrchol.x:
        # vkládáme vpravo
        vrchol.pravy = strom_vloz(vrchol.pravy, x)
    return vrchol
```

### Mazání

Mazání bude o kousíček pracnější, musíme totiž rozlišit tři případy: Pokud je mazaný vrchol list, stačí ho vyměnit za NULL. Pokud má právě jednoho syna, stačí náš vrchol v ze stromu odstranit a syna přepojit k otci v. Ale pokud má syny dva, najdeme největší hodnotu v levém podstromu (tu najdeme tak, že půjdeme jednou doleva a pak pořád doprava), umístíme ji do stromu namísto mazaného vrcholu a v levém podstromu ji pak smažeme (což už umíme, protože má 1 nebo 0 synů). Program následuje:

def strom_vymaz(vrchol, x):
    if vrchol is None:
        # prázdný strom
        return vrchol
    elif x < vrchol.x:
        # hledáme x
        vrchol.levy = strom_vymaz(vrchol.levy, x)
    elif x > vrchol.x:
        vrchol.pravy = strom_vymaz(vrchol.pravy, x)
    else:
        # našli jsme x, jaké má syny?
        if (vrchol.levy is None) and (vrchol.pravy is None):
            return None
        elif vrchol.levy is None:
            # má jen pravého syna
            return vrchol.pravy
        elif vrchol.pravy is None:
            # má jen levého syna
            return vrchol.levy
        else:
            # má oba syny
            w = vrchol.levy
            while not w.pravy is None:
                w = w.pravy
            vrchol.x = w.x    # prohazujeme
            # mažeme původní max(L)
            vrchol.levy=strom_vymaz(vrchol.levy, w.x)
    return v

Když do stromu z našeho prvního obrázku zkusíme přidávat nebo z něj odebírat prvky, dopadne to takto:

![Vyhledávací strom 3](/assets/binarni-vyhledavaci-strom-3.png)

Jak vkládání, tak mazání opět budou trvat O(h), kde h je hloubka stromu. Ale pozor, jejich používáním může h nekontrolovatelně růst (v závislosti na počtu prvků ve stromu).

### Procházení stromu

Pokud bychom chtěli všechny hodnoty ve stromu vypsat, stačí strom rekurzivně projít a sama definice uspořádání hodnot ve stromu nám zajistí, že hodnoty vypíšeme ve vzestupném pořadí: nejdříve levý podstrom, pak kořen a pak podstrom pravý. Časová složitost je, jak se snadno nahlédne, lineární, protože strávíme konstantní čas vypisováním každého prvku a prvků je právě N. Program bude opět přímočarý: 

```py
def strom_ukaz(vrchol):
    if vrchol is None:
        return
    print("({}){}({})".format(
        strom_ukaz(vrchol.levy),
        vrchol.x,
        strom_ukaz(vrchol.pravy)
    ))
```
