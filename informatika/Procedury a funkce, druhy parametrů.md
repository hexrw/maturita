---
layout: default
title: Procedury a funkce, druhy parametrů
permalink: /informatika/procedury-a-funkce-druhy-parametru/
---

> Procedury a funkce označujeme společným pojmem podprogramy (angl. subroutines). Podprogram je část kódu (programu), samostatně definovaná, kterou je možné volat opakovaně z různých míst kódu. Podprogram může mít tzv. parametry, což jsou data, které se podprogramu předávají ke zpracování. Výhoda podprogramů spočívá v tom, že určitý algoritmus, který potřebujeme používat opakovaně, napíšeme pouze jednou (při definici) a na místech, kde potřebujeme tento algoritmus provést, jej pouze zavoláme. Navíc, řešíme-li nějakou složitější úlohu, rozdělíme si složitý problém na jednodušší dílčí podproblémy, jejichž algoritmus řešení napíšeme právě jako podprogramy.

## Procedura

> Jako procedura se označuje programová část (ve většině případů obyčejná [funkce](#funkce)), která nevrací žádnou hodnotu.

*Příklad procedury v Pythonu:*

```python
def funkce():
    udelej_neco()

funkce() # žádná návratová hodnota
```

## Funkce

> Funkce je pojmenovaný blok kódu, jehož účelem je vrátit hodnotu (tzv. *"návratovou hodnotu"*, angl. *"return value"*). Stejně jako proceduru může funkci zavolat jiná část programu.

*Příklad funkce v Pythonu:*

```python
def pozdrav(jmeno): # jmeno je parametr funkce
    print("Ahoj", jmeno)

pozdrav("Karle") # Ahoj Karle
```

## Parametry (argumenty)

> Parametr je speciální druh proměnné, která se ve funkci používá k označení jednoho z údajů zadaných jako vstup do funkce. Tyto údaje jsou hodnoty argumentů, s nimiž bude funkce volána/vyvolána. Uspořádaný seznam parametrů je obvykle součástí definice funkce, aby se při každém volání funkce vyhodnotily její argumenty pro dané volání a výsledné hodnoty mohly být přiřazeny příslušným parametrům.

------------------

**Zdroje**

- [https://www.fd.cvut.cz/personal/xfabera/PRG1/prednasky/prednaska4/prednaska4.php?num=4](https://www.fd.cvut.cz/personal/xfabera/PRG1/prednasky/prednaska4/prednaska4.php?num=4)
- [https://press.rebus.community/programmingfundamentals/chapter/parameters-and-arguments/](https://press.rebus.community/programmingfundamentals/chapter/parameters-and-arguments/)
