---
layout: default
title: Binární a doplňkový kód
permalink: /informatika/ostatni/binarni-a-doplnkovy-kod/
---

## Binární kód

> Způsob uložení informace v počítači definovaný jako konečný počet bitů, z nichž každý může nabývat právě jednu ze dvou hodnot – 0 nebo 1

- pro zápis se používá byte (bajt) s délkou slova 8 bitů
- pro výpočet hodnoty binárního zápisu – binární (=dvojková) soustava

### Význam

- používá se v případě, že člověk neví, jaká informace je v zápisu hodnot použita. Obvykle je tak označován obsah souboru, který obsahuje strojový kód procesoru nebo jiná data, která člověk nemůže přímo z čísel pochopit (např. digitální obrázek, text).

### Kódování

- k uložení a pozdějšímu obnovení – určuje, jak je informace převedena do číselného zápisu (a stejně i zpět)
- např. pro text je používána dohodnutá znaková sada, kde ke každému znaku odpovídá nějaké číslo
- **ASCII** (=American Standard Code for Information Interchange) – používá 7bitový binární kód, který představuje text pro počítače a jiná zařízení, která používají text
    - (v ASCII je pro znak písmene A definován kód 65 – v desítkové soustavě, který je možné vyjídřit v šestnáctkové soustavě jako číslo 41 a binárně 1000001)
- podobně jsou ukládány i strojové instrukce procesoru, kdy každá instrukce je vyjádřena vybraným číslem a procesor musí toto číslo po načtení z paměti nejprve dekódovat (=zjistit, jaký má význam) a teprve potom ji může provést.

## Doplňkový kód

- záporné číslo zaznamenáno jako binární negace (záměna všech 0 za 1) původního čísla zvětšeného o 1
- úvodní bit má význam znaménka
- při odečtení čísla 00000001 od 00000000 dojde k přetečení a výsledkem je číslo 11111111
