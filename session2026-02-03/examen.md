# Problemes

Per cada problema:
* Estructures de dades que et calen (enters, diccionaris, conjunts, piles, ...)
* Que faig mentre recullo cada dada de l'entrada estàndard.
* Que faig quan ja tinc totes les dades.

## Problema 1 - Quadrat N x N
Reps per l'entrada estàndar un número N i pintes un cuadrat d'N x N amb un `.` a cada cella i una `X` a les diagonals.

Exemple per N = 4

```text
X..X
.XX.
X..X
```

## Problema 2 - Els amics dels meus amics
Reps per l'entrada estàndar una primera filera amb dos nombres, A i N. A és l'identificador de la persona que ens interessa i N el número de parelles d'amics. Després reps N fileres amb parelles de nombres X Y on vol dir que X és amic de Y. Exemple:

```
1 5 // Ens interessa '1'. Rebem 5 fileres.
3 1 // 3 és amic de 1
1 2 // 1 és amic de 2
3 7 // 3 és amic de 7
7 8 // 7 és amic de 8
3 1 // 3 és amic de 1 (poden venir repetits)
```

> Nota, encara que digui `3 7 // 3 és amic de 7` el que rebem és només `3 7`.

Volem un llistat dels amics de A i els amics dels amics de A (fins al segon nivell) Volem resoldre sense recursió. A l'exemple, `A` és `1`. Els amics de `1` són `2` i `3` . Lamic de `3` és `7`. El `2` no té amics. La resposta és  `2,3,7`.

## Problema 3 - Pluja de mandonguilles

Tenim un terreny d' `N x M`. Comencen a ploure mandonguilles, tenim un sensor que ens diu on ha caigut cada mandonguilla, la `X` i la `Y`, per exemple `14 19`. Quan rebem `-1 -1` vol dir que ja ha deixat de ploure i al una llista de les coordenades on han caigut més mandonguilles.