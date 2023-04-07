---
layout: default
title: Úplný a neúplný podmíněný příkaz
permalink: /informatika/uplny-a-neuplny-podmineny-prikaz/
---

### Neúplný

Python:

```py
podminka = True

if podminka:
    # Kód, který se vykoná, pokud je podmínka splněna
    print("Podmínka je splněna")
```

### Úplný

Python:

```py
podminka = False

if podminka:
    # Kód, který se vykoná, pokud je podmínka splněna
    print("Podmínka je splněna")
else:
    # Kód, který se vykoná, pokud podmínka není splněna
    print("Podmínka není splněna")
```

### Vrstvené podmínky (nested conditions)

Úplný zápis, Python:

```py
podminka = False
podminka2 = True

if podminka:
    # Kód, který se vykoná, pokud je podmínka splněna
    print("Podmínka je splněna")
else:
    # Kód, který se vykoná, pokud podmínka není splněna
    if podminka2:
        # Kód, který se vykoná, pokud je podmínka2 splněna
        print("Podmínka 2 splněna")
    else:
        # Kód, který se vykoná, pokud podmínka2 není splněna
        print("Podmínka není splněna")
```

Zkrácený zápis, Python:

```py
podminka = False
podminka2 = True

if podminka:
    # Kód, který se vykoná, pokud je podmínka splněna
    print("Podmínka je splněna")
elif podminka2:
    # Kód, který se vykoná, pokud není splněna podmínka a je splněna podmínka2
    print("Podmínka 2 splněna")
else:
    # Kód, který se vykoná, pokud podminka ani podmínka2 není splněna
    print("Podmínka není splněna")
```
