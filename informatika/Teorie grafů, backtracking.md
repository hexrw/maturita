---
layout: default
title: Teorie grafů, backtracking
permalink: /informatika/teorie-grafu-backtracking/
---

## Teorie grafů

> Teorie grafů je obor diskrétní matematiky, který zkoumá vlastnosti takzvaných grafů.

Původ teorie grafů sahá až do 18. století, kdy její zakladatel Leonhard Euler řešil úlohu sedm mostů města Královce.

V roce 1845 publikoval Gustav Kirchhoff zákony, které platí v elektrických obvodech a slouží k výpočtu napětí a proudu v jednotlivých větvích obvodu. V teorii grafů našly své uplatnění při studiu tzv. toků v sítích.

Jedním z hlavních cílů teorie grafů je poskytnout aparát, jímž je možné vyjadřovat vzájemné „vzdálenosti“ (vzdálenosti v širším slova smyslu) jednotlivých dvojic vrcholů. Výsledkem je model reálné sítě.

Na problém teorie grafů lze formalizovat problémy z nejrůznějších vědních oborů i praktického života. Příkladem z první kategorie je analýza dopravy nebo provozu v počítačových sítích, z druhéhou soudku lze uvést kupř. strukturu vzájemného propojení článků Wikipedie – jednotlivé články jsou vrcholy grafu a odkaz z článku A na článek B je orientovanou hranou mezi vrcholy A a B.

### Grafy

> Graf je základním objektem teorie grafů. Jedná se o reprezentaci množiny objektů, u které chceme znázornit, že některé prvky jsou propojeny. Objektům se přiřadí vrcholy a jejich propojení značí hrany mezi nimi. Významově se tak překrývá s pojmem binární relace, o grafech se ale mluví hlavně v kontextu relací nad konečnými množinami. Grafy slouží jako abstrakce mnoha různých problémů. Často se jedná o zjednodušený model nějaké skutečné sítě (například dopravní), který zdůrazňuje topologické vlastnosti objektů (vrcholů) a zanedbává geometrické vlastnosti, například přesnou polohu. Může jít ale o v podstatě jakékoliv dobře definované vztahy mezi objekty, například na sociální síti můžeme studovat graf uživatelů (vrcholy) a jejich vzájemná propojení (hrany).



#### Orientovaný graf

Graf je orientovaný, pokud je každá hrana spojující vrcholy v a u taková, že v je předchůdcem u.

#### Neorientovaný graf

Graf je neorientovaný, pokud hrany nejsou orientované.

#### Hranatý graf

Graf je hranatý, pokud každá hrana má jinou barvu.

#### Graf s hranami s váhou

Graf je graf s hranami s váhou, pokud každá hrana má přiřazenou číselnou hodnotu.

## Backtracking

Backtracking (česky zpětné vyhledávání, metoda pokusů a oprav, metoda zpětného sledování, metoda prohledávání do hloubky) je způsob řešení algoritmických problémů založený na prohledávání stavového prostoru problému. Jedná se o vylepšení hledání řešení hrubou silou v tom, že velké množství potenciálních řešení může být vyloučeno bez přímého vyzkoušení. Algoritmus je založen na prohledávání do hloubky možných řešení.

Algoritmus je možné použít pro řešení velkého množství problémů, nicméně díky jeho (obecně) exponenciální časové složitosti se používá jen tehdy, kdy není znám efektivnější algoritmus (polynomiální) nebo je použit pro data malé velikosti, popřípadě pro něj existuje dobrá heuristika. 

Algoritmus backtracking pracuje tak, že postupně prozkoumává všechna možná řešení, dokud nenajde platné řešení nebo dokud nevyčerpá všechny možnosti.

Při zkoumání kandidátního řešení algoritmus testuje, zda je platné, nebo ne. Pokud není platné, vrátí se zpět a vyzkouší jiné kandidátské řešení.

Algoritmy pro zpětné vyhledávání často využívají rekurzi k prozkoumání prostoru řešení. Každé rekurzivní volání prozkoumá podmnožinu prostoru řešení, a pokud tato podmnožina neobsahuje platné řešení, algoritmus se vrátí zpět a vyzkouší jinou podmnožinu.

Mezi příklady problémů, které lze řešit pomocí zpětného vyhledávání, patří problém N-dvojic, hádanky Sudoku a problém Knight's Tour.

Algoritmy pro zpětné hledání mohou být časově a paměťově náročné, zejména při zkoumání velkého prostoru řešení. Pro optimalizaci výkonu lze použít různé techniky prořezávání, které eliminují části prostoru řešení, o nichž je známo, že jsou neplatné.

Navzdory svým omezením je backtracking výkonnou technikou řešení problémů, která byla použita k řešení široké škály problémů v informatice, matematice a dalších oborech.

---------------------

**Zdroje**

- [https://teorie-grafu.cz/](https://teorie-grafu.cz/)
- [https://cs.wikipedia.org/wiki/Teorie_graf%C5%AF](https://cs.wikipedia.org/wiki/Teorie_graf%C5%AF)
- [https://cs.wikipedia.org/wiki/Backtracking](https://cs.wikipedia.org/wiki/Backtracking)
