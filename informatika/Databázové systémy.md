---
layout: default
title: Databázové systémy
permalink: /informatika/databazove-systemy/
---

Databáze (neboli datová základna, též databanka) je systém souborů s pevnou strukturou záznamů. Tyto soubory jsou mezi sebou navzájem propojeny pomocí klíčů. V širším smyslu jsou součástí databáze i softwarové prostředky, které umožňují manipulaci s uloženými daty a přístup k nim. Tento software se v české odborné literatuře nazývá systém řízení báze dat (SŘBD). Běžně se označením databáze – v závislosti na kontextu – myslí jak uložená data, tak i software (SŘBD).

**Co by databázový systém měl umět?**

Protože databázový systém musí dennodenně pracovat s opravdu početným skupenstvím perzistentních dat, tak na něj jsou kladeny jisté nároky, které by měl pro práci s daty snadno zvládat. Jako např.:
- podpora pro definice datového modelu (např. relační nebo logický)
- využití některého z jazyků (SQL, QBE atd.) vyšší úrovně pro manipulaci dat
- správu transakcí
- autentizaci uživatelů a autorizaci operací nad datami
- robustnost a zotavitelnost po chybách bez ztráty dat

## Databázové objekty

Pojem „databáze“ je často zjednodušován na to, co je ve skutečnosti databázový systém (databázový stroj) nebo též systém řízení báze dat. Ten neobsahuje pouze tabulky – ty jsou jedny z mnoha tzv. databázových objektů (někdy též databázových entit). Pokročilejší databázové systémy dále obsahují:

- **pohledy** neboli views – SQL příkazy, pojmenované a uložené v databázovém systému. Lze z nich vybírat (aplikovat na ně příkaz SELECT) jako na ostatní tabulky.
- **indexy** pro každou tabulku. Klíče jsou definovány nad jednotlivými sloupci tabulek (jeden klíč jich může zahrnovat i více) a jejich funkce je vést si v tabulkách rychlé LUT (look-up tables – „pořadníky“) na sloupce, nad nimiž byly definovány, vyloučit duplicitu v záznamech nebo zajišťovat fulltextové vyhledávání.
- **spouštěče** neboli triggers - mechanizmus nad jednotlivými řádkami tabulky (případně samotnou tabulkou), který se vyvolá po změně, odstranění nebo přidání řádky, případně smazání tabulky a provede předprogramovanou akci (například kontrolu integrity dat, doplnění hodnot...)
- **uživatelem definované procedury a funkce** – některé databázové stroje podporují ukládání pojmenovaných kusů kódu, které provedou v databázi nad danými tabulkami určitou sekvenci příkazů (procedury) nebo navíc vrátí nějaký výsledek (uživatelské funkce). Mohou mít parametry, které se většinou dělí na vstupní (IN), výstupní (OUT) a vstupně-výstupní (INOUT).
- **události**, též (počeštěně) „eventy“ – de facto procedury, spouštěné v určitý (uživatelem definovaný) datum a čas nebo opakovaně s definovatelnou periodou. Mohou sloužit k údržbě, promazávání dočasných dat či kontrolování referenční integrity.
- **formuláře** – některé databázové systémy jako např. Microsoft Access umožňuje uživatelům vytvářet vstupní formuláře pro vizuálně přívětivé zadávání hodnot. Uživatel si může např. nadefinovat rozložení jednotlivých vstupních polí z dané tabulky, popisky atd.
- **sestavy** nebo též reporty – podobně jako u formulářů sestavy umožňují uživateli definovat layout s políčky dané tabulky, do kterého se při použití doplní aktuální hodnoty. Používají se pro výstup dat (tisk, prezentaci nebo pouhé zobrazení). Sestavy mohou být např. doplněny o filtry, které vyfiltrují jen kýžené záznamy.
- **uživatelská oprávnění** – u lepších databázových systémů je samozřejmostí nabídnout možnosti, jak oddělit jednotlivé úrovně přístupu k ostatním objektům databáze jejich uživatelům. Možností bývají desítky, s rozlišením na jednotlivé typy příkazů, které ten který uživatel bude nebo nebude mít oprávnění spustit.
- **partitioning** – způsob, jak rozdělit data v tabulce na více pevných disků a tím rozložit zátěž na ni kladenou
- **procesy** – databázové stroje umí podat přehled o procesech, které jejich služeb aktuálně využívají.
- **proměnné** nastavení – typicky desítky proměnných, které lze přenastavovat a tím ovlivňovat chování a výkon databázového stroje jako takového.
- **collation** – MySQL má pokročilé možnosti pro nastavení několika desítek znakových sad a porovnávání, souhrnně nazývané collation. Nastavení collation může být provedeno na jednotlivé textové sloupce, celé tabulky i celé databáze (s kaskádovitou dědičností). Collation ovlivňuje i řazení, například hodnota utf8_czech_ci zajistí správné řazení podle češtiny (tedy včetně diakritiky a včetně ch).
- **vizuální E-R schéma** – (v MySQL INFORMATION.SCHEMA). Vizuální reprezentace vztahů (relací) na sobě závislých polí (cizích klíčů) mezi tabulkami.

## Základní pojmy

### Databázová integrita

Databázová integrita je takový stav, při němž záznamy v celé databázi vyhovují soustavě určitých definovaných pravidel. Tato pravidla obvykle odpovídají vybraným pravidlům z té části světa, pro kterou databáze slouží. Může se jednat například o pravidla stanovující rozsah uložených hodnot, jejich typ nebo vazby mezi nimi.

### Databázová normalizace

Normalizace databáze je v informatice označení postupu, kdy je struktura dat v relační databázi přeorganizována tak, aby využívala výhody relačního modelu dat. Normalizace databáze umožňuje data efektivněji ukládat, prohledávat, třídit i zpracovávat. Při normalizaci jsou v databázi měněny atributy (sloupce) jednotlivých tabulek a zaváděny mezi nimi výhodné vztahy, je omezována redundance uložených dat (vět) a je brán ohled na řešení problému s případnou nekon

### Databázové transakce

Databázová transakce je skupina příkazů, které převedou databázi z jednoho konzistentního stavu do druhého. 

Databázové transakce musí splňovat tzv. vlastnosti ACID:
- atomicitu (angl. atomicity, A);
- konzistenci (angl. consistency, C);
- izolovanost (angl. isolation, I);
- trvalost (angl. durability, D).

## Databázové modely

Z hlediska způsobu ukládání dat a vazeb mezi nimi můžeme rozdělit databáze do základních typů:

### Relační databáze

Relační databáze je databáze založená na relačním modelu. Často se tímto pojmem označuje nejen databáze samotná, ale i její konkrétní softwarové řešení.

Relační databáze je založena na tabulkách, jejichž řádky obvykle chápeme jako záznamy a eventuálně některé sloupce v nich (tzv. cizí klíče) chápeme tak, že uchovávají informace o relacích mezi jednotlivými záznamy v matematickém slova smyslu.

#### Terminologie relačních databází

![DS 1](/assets/ds-1.png)

#### Příklady relační databáze

- MySQL
- SQLite 3
- PostgresSQL
- MariaDB
- Microsoft SQL Server
- Firebird

### Hierarchická databáze

Hierarchická databáze (také hierarchická nebo stromová datová struktura) je datový model, ve kterém jsou data uspořádána ve stromové struktuře. Je to první z datových modelů, který byl v minulosti hojně využíván v praxi. Její vznik se datuje do 60. let minulého století a nejznámějším hierarchickým systémem řízení báze dat byl IMS od společnosti IBM. Hierarchická koncepce ovšem vykazuje jisté nedostatky při modelování reality, a proto bylo od jejího používání upuštěno, kdy byla prvně překonána koncepcí síťovou a v roce 1970 koncepcí relační.

#### Základní konstruktory

1. Věta - obdoba relace v relačním datovém modelu. Každá věta je definována svými atributy. Oproti relačnímu modelu neexistuje omezení při tvorbě atributu - atributy nemusí být atomické (není zde zaveden pojem normalizace datové základny), atributy mohou být i vícerozměrnými strukturami jako jsou například pole apod.
2. Vlastnicko-členský vztah (také vztah rodič - dítě) - vztah kardinality 1:N mezi dvěma větami; věta na straně jedna se nazývá vlastník, věta na straně N se nazývá člen.

#### Vlastnosti

- hierarchické schéma má jeden kořen, který není člen v žádném vztahu
- každá věta, kromě kořene, je členem právě v jednom vztahu
- každá věta může být vlastníkem 1 až n počtu vět
- věta, která není vlastníkem v žádném vztahu, se nazývá list

Z výše uvedených vlastností vyplývá, že hierarchický model je schopen bezproblémově modelovat pouze vztahy kardinality 1:N. Vztahy kardinality M:N je možné modelovat za využití dvou vztahů 1:N za pomocí tzv. směrníkových vět, jedná se o speciální případ "virtuální věty", která obsahuje klíče z obou vztahů 1:N a binární ukazatele na umístění vztahů v hierarchickém schématu.

### Síťová databáze

Síťová databáze je databázový model podobný hierarchickému databázovému modelu, který byl po dlouhou dobu takřka výhradně užívaným databázovým modelem. Na rozdíl od hierarchického databázového modelu poskytuje navíc vztahy více ku více, tedy jedna entita mohla mít více otců. Tato datová koncepce však byla v roce 1970 překonána relační koncepcí databáze. Také navíc umožňuje rekurzi, tedy entita může být otcem svému otci.

Nevýhodou využívání síťové databáze je její nepružnost a z toho vyplývající obtížná změna její struktury.

Z nejznámějších databázových systémů tento systém využíval například RDM Server, Integrated Data Store (IDS) a další.

#### Síťová koncepce

- zdokonalení hierarchické koncepce
- přímá návaznost na hierarchickou koncepci
- naprosto převládala v komerčních databázových systémech 80. let.
- nejznámější produkt byl IDMS od firmy Culliname Corp.
- síťová struktura se modeluje pomocí tzv. Bachmanových diagramů (C. Bachmann tvůrce síťové koncepce)

#### Základní konstruktory

Věta je souhrn vzájemně souvisejících datových položek.

Set je vztah mezi dvěma větami kardinality 1:N.

- je definován jménem, vlastnickou a členskou větou.
- ta na straně 1 se jmenuje věta vlastnická a na straně N věta členská.
- set má své výskyty.
- výskyt setu je dán výskytem konkrétního vlastníka a výskytem jeho členů
- Singulární set – takový set, ve kterém je virtuální vlastník systém a tento set má pouze jeden výskyt členských vět (kompromisní prostředek, který umožňuje vložit do databáze plochou strukturu).
- vícečlenský set – set, který může mít více vět (nikoliv výskytu vět) za své členy
- rekurzivní set – pro řešení tzv. konceptuální smyčky, tzn. že daná věta je současně vlastníkem i členem síťové modelování- 
- 1:n vyjádřeny stavebním prvkem setu
- rekurzivní - nelze modelovat přímo, řeší se pomocí vazební (prázdné) věty
- m:n - se dá vyjádřit pomocí vazební věty

### Objektová databáze

Objektová databáze je databázový řízený systém, ve kterém je informace reprezentována ve formě objektu a používá se v objektově orientovaném programování. Objektové databáze se odlišují od relačních databází, které jsou tabulkové. Také existují objektově relační databáze, které jsou hybridem dvou předchozích přístupů.

První informace o objektových databázích se objevila v polovině 80. let.

Objektově databázový řízený systém (Object-oriented database management systems - OODBMS nebo Object Database Management System - ODBMS) je kombinace databázových možností a objektově orientovaného programování. OODBMS dovoluje objektově orientovaným programátorům vyvíjet produkt, zachovat jako objekt, reduplikovat nebo modifikovat existující objekty. Díky tomu, že je databáze integrovaná (propojená) s programovacím jazykem, může programátor udržovat konzistenci v jednom prostředí. Proto se v OODBMS a programovacím jazyce používá stejný model reprezentace. Relační DBMS projekty proti tomu přísně rozlišují mezi databázovým modelem a aplikací.

Počet web-technologií roste s implementací interních a externích sítí, společnosti mají zájem o OODBMS pro zobrazování svých komplexních dat. Použití DBMS bylo konkrétně určené k ochraně dat hlavně pro společnosti orientované na multimédia a prezentaci a organizaci služeb, jako computer-aided design (CAD).

Některé objektově orientované databáze jsou propojené s objektově orientovanými jazyky, jako Delphi, Ruby, Python, JavaScript, Perl, Java, C#, Visual Basic .NET, C++, Objective-C a Smalltalk; jiné, jako JADE, mají svůj vlastní programovací jazyk. OODBMS používá přesně ten samý model jako objektově orientované jazyky. 

### Objektově relační databáze

Relačně-objektivní databáze (ORDBMS) je databázový systém, který sjednocuje rysy objektově orientované a relační databáze. ORDMBS je specifikována v SQL standardu - SQL3. Příkladem tohoto typu databáze jsou: *Informix*, *IBM*, *Oracle* a *Unisys*.
