---
layout: default
title: Algoritmus, vývojové diagramy, deklarace proměnných
permalink: /informatika/algoritmus-vyvojove-diagramy-deklarace-promennych/
---

**Algoritmy**

Algoritmus je přesný návod či postup, kterým lze vyřešit daný typ úlohy. Pojem algoritmus se nejčastěji objevuje při programování, kdy se jím myslí teoretický princip řešení problému (oproti přesnému zápisu v konkrétním programovacím jazyce). Obecně se ale algoritmus může objevit v jakémkoli jiném vědeckém odvětví. Jako jistý druh algoritmu se může chápat i např. kuchařský recept. Zpravidla však na algoritmy klademe určitá omezení.

Z obecného hlediska se jedná o „přesný návod nebo postup pro vyřešení konkrétní úlohy“.

Název je od perského matematika Al-Chorezmí (9. století).

Teoretický princip řešení programu (nejen programu, ale i například skládání rubikovy kostky).

Například kuchařka je též algoritmus pro kuchaře na přípravu jídla.

## **Vlastnosti algoritmu**

**Elementárnost**

Algoritmus se skládá z konečného počtu jednoduchých (elementárních) kroků.

**Konečnost (finitnost)**

Každý algoritmus musí skončit v *konečném* počtu kroků. Tento počet kroků může být libovolně velký (podle rozsahu a hodnot vstupních údajů), ale pro každý jednotlivý vstup musí být konečný. Postupy, které tuto podmínku nesplňují, se mohou nazývat *výpočetní metody*. Speciálním příkladem nekonečné výpočetní metody je *reaktivní proces*, který průběžně reaguje s okolním prostředím. Někteří autoři však mezi algoritmy zahrnují i takovéto postupy.

**Obecnost (univerzálnost, *vstup*)**

Algoritmus neřeší jeden konkrétní problém (např. „jak spočítat 3×7“), ale obecnou třídu obdobných problémů (např. „jak spočítat součin dvou celých čísel“), má širokou množinu možných vstupů.

**Determinovanost**

Algoritmus je determinovaný, pokud za stejných podmínek (pro stejné vstupy) poskytuje stejný výstup. Tato vlastnost je požadována u velké části úloh; existují však úlohy, kdy je naopak vyžadována náhodnost (například simulace vrhu kostkou, míchání karet, generování hesel a šifrovacích klíčů); na standardních počítačích je dosažení náhodnosti obtížné. Pravděpodobnostní algoritmy v sobě mají zahrnutu náhodu a nemusí být determinované.

**Determinismus (určitost)**

Každý krok algoritmu musí být *jednoznačně* a *přesně* definován; v každé situaci musí být naprosto zřejmé, co a jak se má provést, jak má provádění algoritmu pokračovat. Protože [přirozené jazyky](https://cs.wikipedia.org/wiki/Jazyk_\(lingvistika\)) neposkytují naprostou přesnost a jednoznačnost vyjadřování, byly pro zápis algoritmů navrženy [programovací jazyky](https://cs.wikipedia.org/wiki/Programovací_jazyk), ve kterých má každý příkaz jasně definovaný význam. Vyjádření výpočetní metody v programovacím jazyce se nazývá [program](https://cs.wikipedia.org/wiki/Počítačový_program). Některé algoritmy jsou sice determinované, ale nejsou deterministické (například řadící algoritmus [rychlé řazení](https://cs.wikipedia.org/wiki/Rychlé_řazení) s náhodnou volbou pivota).

**Korektnost**

Algoritmus skončí pro libovolná (korektní) data správným výsledkem v konečném množství kroků.

**Výstup**

Algoritmus má alespoň jeden *výstup*, veličinu, která je v požadovaném vztahu k zadaným vstupům, a tím tvoří odpověď na problém, který algoritmus řeší (algoritmus vede od zpracování hodnot k výstupu)
# **Dělení algoritmů**
Jeden algoritmus může patřit zárověň do více skupin; například může být zároveň rekurzivní a genetický.

**Iterativní**

Iterativní algoritmus je takový, který spočívá v opakování určité své části (bloku).

**Rekurzivní**

Rekurzivní algoritmus opakuje kód prostřednictvím volání sebe sama (obvykle na podproblémech menší velikosti). Každý rekurzivní algoritmus lze převést do iterativní podoby. Samotný převod často řeší automaticky kompilátor nebo virtuální stroj daného programovacího jazyka.

Výhoda rekurzivních algoritmů je v jejich snadno čitelném a kompaktním zápisu. Nevýhodou je spotřeba dodatečných systémových prostředků pro udržení jednotlivých rekurzivních volání.

**Pravděpodobnostní (probabilistické)**

Provádějí některá rozhodnutí náhodně či pseudonáhodně.

**Genetický**

Speciální druh algoritmu. Pracuje na základě napodobování biologických evolučních procesů, postupným „pěstováním“ nejlepších řešení pomocí mutací a křížení. V genetickém programování se tento postup aplikuje přímo na algoritmy (resp. programy), které jsou zde chápány jako možná řešení daného problému.

**Heuristický**

Neklade si za cíl nalézt přesné řešení, ale pouze nějaké vhodné přiblížení; používá se v situacích, kdy dostupné zdroje (např. čas) nepostačují na využití exaktních (přesných) algoritmů (nebo pokud nejsou žádné vhodné exaktní algoritmy vůbec známy).

**Deterministický**

Deterministický je takový algoritmus, který má v každém svém kroku právě jednu možnost, jak pokračovat.

**Nedeterministický**

Nedeterministický algoritmus má v každém kroku více možností, jak pokračovat.

**Sériový**

Sériový algorimus vykonává všechy kroky v sérii (jeden po druhém).

**Paralelní**

Paralelní algoritmus vykonává kroky zároveň (ve více vlákech).

**Distribuovaný**

Distribuovaný algoritmus kroky vykonává zároveň na více strojích.

### Složitost algoritmu

Je třeba poznamenat, že abstraktní kritérium konečnosti je pro praktické použití ještě příliš slabé. V praxi je třeba zajistit, aby algoritmus skončil „v rozumném“ čase. Za rozumný čas lze v praxi považovat takový čas, který nám umožní smysluplně využít výsledek.

Např. existuje jednoduchý algoritmus, který dokáže určit, zda v dané šachové pozici může hráč na tahu vynutit vítězství a zároveň dokáže určit nejlepší možný tah. Tento algoritmus se však nedá použít, protože by na svou činnost potřeboval ohromné množství času, jakkoli je toto množství konečné. Mimoto by takový algoritmus spotřeboval ohromné množství paměti, což je další praktický zřetel, který se uplatňuje při volbě algoritmu. I když průměrná počítačová paměť stále narůstá, pro některé algoritmy jí nebude nikdy dost.

Pro vyčíslení výpočetní složitosti algoritmů v závislosti na velikosti vstupních dat se používá asymptotický zápis závislosti výpočetního času na rozsahu úlohy (typicky na počtu vstupních údajů). Například O(log N) znamená, že počet kroků algoritmu závisí logaritmicky na velikosti vstupních dat. Pokud u takového algoritmu zdvojnásobíme rozsah vstupních údajů, doba výpočtu se zvýší o jednu jednotku času, pokud bude vstupních dat čtyřikrát více, doba výpočtu se prodlouží o dvě jednotky času, a tak dále. To je třeba případ nalezení jednoho prvku o určité hodnotě v seznamu prvků seřazeném podle hodnoty (např. nalezení jména v telefonním seznamu).

#### Asymptotická složitost algoritmu

Asymptotická složitost algoritmu charakterizuje počet provedených operací v závislosti na velikosti dat. Například pokud procházíme pole, pak složitost bude lineární (na každý prvek připadá konstantní množství operací), pokud jej ovšem řadíme například bubble sortem, pak složitost bude kvadratická (na *n* prvků bude připadat *n2* operací).

#### Třída složitosti

Třída složitosti stanovuje obtížnost rozhodnutelnosti daného problému na Turingově stroji.

**Třída P**

Obsahuje problémy rozhodnutelné v polynomiálním čase.

*Má daný graf kostru o velikosti maximálně k?*

*Existuje v daném acyklickém grafu mezi uzly a a b cesta, jejíž délka je nejvýše k?*

**Třída NP**

Obsahuje problémy, které jsou rozhodnutelné pomocí nedeterministického Turingova stroje v polynomiálním čase – tzn. jsme schopni ověřit jejich řešení v polynomiálním čase.

*Lze daný graf obarvit maximálně k barvami?*

*Existuje v daném grafu hamiltonovská kružnice?*

*Existuje v daném grafu klika o alespoň k vrcholech?*

*Hierarchie tříd složitosti*

## **Paradigmata návrhu algoritmů**

**Rozděl a panuj**

Klasický případ aplikace postupu odshora dolů. Algoritmy typu rozděl a panuj dělí problém na menší podproblémy, na něž se rekurzivně aplikují (až po triviální podproblémy, které lze vyřešit přímo), po čemž se dílčí řešení vhodným způsobem sloučí.

Zpracovává se množina V složená z n údajů. Tato množina se rozdělí na k disjunktních podmnožin, které se zpracují každá zvlášť. Získané dílčí výsledky se pak spojí a odvodí se z nich řešení pro celou množinu V.

Klasickým případem je binární vyhledávání nebo řadící algoritmus rychlé řazení.

**Hladový algoritmus**

Velice přímočarý přístup k řešení určité třídy optimalizačních úloh.

Zpracovává se množina V složená z n údajů. Úkolem je najít podmnožinu W množiny V, která vyhovuje určitým podmínkám a přitom optimalizuje předepsanou účelovou funkci. Jakákoliv množina W, vyhovující daným podmínkám, se nazývá přípustné řešení. Přípustné řešení, pro které nabývá účelová funkce optimální hodnoty, se nazývá optimální řešení.

Hladový algoritmus se skládá z kroků, které budou procházet jednotlivé prvky z V, a v každém kroku rozhodne, zda se daný prvek hodí do optimálního řešení. Prvky V bude vybírat v pořadí určeném jistou výběrovou procedurou. Výběrová procedura bude založená na nějaké optimalizační míře – funkci, která může být odvozena od účelové funkce. V každém kroku ale musíme dostat přípustné řešení. Jakmile je učiněno takové rozhodnutí, už není dále revidováno. Příkladem je třeba hledání nejkratší cesty grafu.

**Dynamické programování**

Dynamické programování se používá v případech kdy lze optimální řešení složit z řešení jednodušších problémů. Protože se požadavky na řešení jednodušších podproblémů mohou mnohokrát opakovat, je nutné zvolit správné pořadí jejich řešení a výsledky si zapamatovat pro opakované použití.

Opírá se o princip optimality: Optimální posloupnost rozhodnutí má tu vlastnost, že ať je počáteční stav a rozhodnutí jakékoliv, musí být všechna následující rozhodnutí optimální vzhledem k výsledkům rozhodnutí prvního.

Typickým příkladem využití dynamického programování jsou grafové úlohy a a jejich příslušné grafové algoritmy.

**Použití hrubé síly**

U některých úloh nezbývá než postupně probírat všechna možná řešení – tak zvaná metoda hrubé síly – vygenerují se všechny možné posloupnosti a pak se vybere ta nejlepší. V některých případech lze použít metody, které vynechávají popřípadě odkládají procházení možností, které zřejmě nejsou optimální.

**Hledání s návratem (backtracking)**

Hledání s návratem založené na prohledávání stavového prostoru problému. Též se nazývá metoda pokusů a oprav, metoda zpětného sledování, metoda prohledávání do hloubky.

Metodu je možné použít v případě, že řešením je vektor *(x1,...,xn)* jehož jednotlivé složky vybíráme z množiny *Si, xi∈Si*. Zpravidla je třeba najít n-tici, která optimalizuje nějakou účelovou funkci *P(x1,...,xn)*. Mohou se ale také hledat všechny n-tice, které tuto podmínku splňují. Metoda vytváří n-tice jednu složku po druhé. Přitom používá účelovou funkci (nebo nějakou vhodnou pomocnou funkci) a pro každou nově vytvořenou složku testuje, zda by taková n-tice vůbec mohla být optimální nebo splňovat dané podmínky. Jestliže pro nějaké xi žádaný vektor *(x1,...,xi)* nemůže být optimální, není třeba už žádný takový vektor testovat a vezmeme další možnou hodnotu i-té složky. Pokud jsou vyčerpány všechny hodnoty i-té složky, vrátí se metoda zpět o jeden krok a zkouší další možnou hodnotu *xi-1*.

Příkladem je třeba problém osmi dam, nebo chůze koně celou šachovnicí.

**Vývojové diagramy**

Vývojový diagram je druh diagramu, který slouží ke grafickému znázornění jednotlivých kroků algoritmu, pracovního postupu nebo nějakého procesu. Vývojový diagram obsahuje obrazce různého tvaru (obdélníky, kosočtverce, aj.), navzájem propojené pomocí šipek. Obrazce reprezentují jednotlivé kroky, šipky tok řízení. Vývojové diagramy standardně nezobrazují tok dat, ten je zobrazován pomocí data flow diagramů. Vývojové diagramy jsou často využívány v informatice během programování pro analýzu, návrh, dokumentaci nebo řízení procesu.

**Symboly vývojového diagramu**

- šipka — určuje směr zpracování
  - svislé nebo vodorovné čáry
  - mohou se křížit nebo spojovat
  - směr dolů a doprava je prioritní, v tomto případě není nutné použít šipky
  - šipky se používají jenom v případě, že tento směr je jiný, nebo když je třeba směr toku informace zvýraznit, například při znázornění iterace
- obdélník s popisem — definuje dílčí krok zpracování
- kosočtverec — větvení postupu v závislosti na splnění podmínky, viz skok
- obdélník se zaoblenými rohy — počátek nebo ukončení zpracování
- kruh — spojka několika šipek

**Význam a použití symbolů**

Klasický vývojový diagram se skládá z následujících druhů symbolů:

Startovací a ukončovací symboly

Jsou znázorněny pomocí kruhů, oválů či zaoblených obdélníků, obvykle obsahují nápis „Start“ nebo „Konec“, či podobnou frázi určující začátek a konec procesu (např. „Zaslání požadavku“ nebo „Odebrání produktu“).

Šipky

Zobrazují „řídící tok“. Šipka směřující z jednoho symbolu a končící u druhého naznačuje, že řídící tok přechází z jednoho symbolu na druhý.

Dílčí krok algoritmu

Reprezentován pomocí obdélníku. Příklad: „Přičti 1 k X“ nebo „Ulož změny“ apod.

Podprogramy

Jsou zobrazovány pomocí obdélníku se svislými čarami po stranách. Používají se k zobrazení skupiny kroků procesu pomocí jednoho symbolu. Podprogramy jsou takové části algoritmu, které se mohou opakovat a mohly by být tvořeny samostatným vývojovým diagramem.

Vstup/Výstup

K jejich zobrazení se používá rovnoběžníku, v případě uživatelského vstupu se zobrazuje pomocí lichoběžníku. Příklad: „Získej proměnnou X od uživatele; zobraz proměnnou X“.

Podmíněný cyklus

Zobrazen pomocí šestiúhelníku. Cyklus probíhá dokud vyhovuje podmínce, poté přejde k dalšímu kroku algoritmu.

Podmíněný výraz

Je reprezentován kosočtvercem, používá se tam, kde je zapotřebí nějakého rozhodnutí. Má většinou podobu otázky a její odpovědi ve tvaru Ano/Ne nebo Pravda/Nepravda. Ze symbolu podmíněného výrazu vychází dvě a více šipek, každá z šipek může obsahovat odpověď na danou otázku (doporučuje se odpovědi k šipkám nadepisovat).

Spojovací značka

Pro její značení se obvykle používá kruh. Používá se tam, kde je třeba spojit více toků procesu do jednoho toku.

**Druhy vývojových diagramů**

Alan B. Sterneckert (2003) navrhl, že by vývojové diagramy mohly být tvořeny z nezávislého pohledu jiné skupiny uživatelů (např. manažery, systémovými analytiky a úředníky) a díky tomuto návrhu existují čtyři hlavní typy vývojových diagramů:

- Document flowcharts — ukazují řízení toků dokumentů v systému.
- Data flowcharts — ukazují řízení toků dat v systému.
- System flowcharts — ukazují řízení toků fyzické vrstvy nebo vrstvy zdrojů.
- Program flowchart — ukazují řízení toků v programu v rámci systému.

*Příklad vývojového diagramu*

![Vývojový diagram](/assets/vyvojovy-diagram.png)

**Deklarace proměnných**

Deklarace je v informatice zápis, kterým se v počítačovém programu zavádí jméno (identifikátor) a zpravidla určuje jeho datový typ a další aspekty pro proměnné, funkce (procedury), konstanty apod. Překladač je tak informován o příslušném objektu. V jazycích se silnou typovou kontrolou, jako je Pascal, C nebo Ada, je nutné všechny objekty deklarovat dříve, než jsou použity v programu.

**Deklarace a definice**

V některých programovacích jazycích se rozlišuje deklarace a definice. Zatímco v deklaraci se definuje typ deklarované entity, v definici se definuje její obsah (například tělo funkce). V programovacích jazycích typu BCPL jako je C++ a Java, může být při deklaraci zadána také velikost proměnné. Zadání velikosti proměnné se používá k deklaraci vektorů, polí, nebo matic. V této skupině programovacích jazyků mohou být "pravé" deklarace (oznámení o existenci prvku a jeho vlastnostech, tedy jednoduše řečeno "deklarace") a „definice“ (deklarace, které se týkají aktuální implementace, například při deklaraci (definici) funkcí a inicializaci proměnných) vytvářeny nezávisle na sobě.

Deklarace se provádějí především v hlavičkových souborech, které jsou následně vloženy do jiných souborů, které je mohou používat, ale nemají přístup k definicím. Tato struktura umožňuje oddělení rozhraní od implementace. Pokud definovaný typ neodpovídá předchozí deklaraci, překladač ukončí činnost a zahlásí chybu.

V případě proměnných definice přiřazují hodnoty na rezervované místo v paměti během deklarace. V případě funkcí, definice vytvoří její tělo. Zatím co proměnné a funkce mohou být deklarovány mnohokrát za sebou, definovány mohou byt pouze jednou. Dynamické jazyky jako například JavaScript nebo Python umožňují předefinovat funkce.

Deklarace je obvykle používána v případě potřeby přístupu k proměnné, nebo funkci definované v jiném zdrojovém souboru, nebo knihovně.

**Implicitní a Explicitní deklarace**

Explicitní deklarace proměnné se zapisuje před jejím vlastním použitím, zpravidla na začátku procedury události. Deklarace začíná obvykle definováním datového typu.

Implicitní deklarace znamená, že proměnnou během deklarace přímo použijeme v programu (viz příklad). Jedná se tedy o deklaraci proměnné „za běhu“. Implicitní deklarace má výhodu rychlejšího zápisu programového kódu.

**Proměnné**

V některých programovacích jazycích jsou implicitní deklarace vytvořeny při překladu, až když se s nimi překladač poprvé setká. V jiných jazycích je takový postup považovaný za fatální a během diagnostiky je zahlášena chyba. Některé jazyky původně používaly implicitní deklaraci proměnných, ale během jejich vývoje získaly možnost ji vypnout (například v Perlu použitím „use strict“ nebo ve Visual Basicu direktivou Option Explicit“).

----------------

**Zdroje**

- [https://algoritmy.net/](https://algoritmy.net/)
- [https://cs.wikipedia.org/wiki/Algoritmus](https://cs.wikipedia.org/wiki/Algoritmus)
- [https://cs.wikipedia.org/wiki/V%C3%BDvojov%C3%BD_diagram](https://cs.wikipedia.org/wiki/V%C3%BDvojov%C3%BD_diagram)
- [https://popelka.ms.mff.cuni.cz/~lessner/mw/index.php/U%C4%8Debnice/Algoritmus/V%C3%BDvojov%C3%A9_diagramy](https://popelka.ms.mff.cuni.cz/~lessner/mw/index.php/U%C4%8Debnice/Algoritmus/V%C3%BDvojov%C3%A9_diagramy)
- [https://cs.wikipedia.org/wiki/Deklarace_(programov%C3%A1n%C3%AD)](https://cs.wikipedia.org/wiki/Deklarace_(programov%C3%A1n%C3%AD))
