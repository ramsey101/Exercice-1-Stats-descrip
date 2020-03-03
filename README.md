# Exercice-1-Stats-descrip
  ## CHAPITRE 1

***Exercice 1***

```js
La variable statistique "couleur de maisons d'un quartier" est :
```
- [ ] Qualitative v
- [ ] Quantitative

- [ ] Discrète
- [ ] Continue

```js
La variable statistique "revenu brut" est :
```
- [ ] Qualitative
- [ ] Quantitative v

- [ ] Discrète
- [ ] Continue


```js
La variable statistique "nombre de maisons vendues par ville" est :
```
- [ ] Qualitative
- [ ] Quantitative  v

- [ ] Discrète.  v
- [ ] Continue


**Exercice 2**

```console
Parmi ces assertions, préciser celles qui sont vrai, et celles qui sont fausses.
````

1. On appelle variable, une caractéristique que l’on étudie.   v

2. La tâche de la statistique descriptive est de recueillir des données.   f

3. La tâche de la statistique descriptive est de présenter les données sous forme de 
tableaux, de graphiques et d’indicateurs statistiques.   v

4. En Statistique, on classe les variables selon différents types.   v

5. Les valeurs des variables sont aussi appelées modalités.   v

6. Pour une variable qualitative, chaque individu statistique ne peut avoir qu’une seule modalité.   f

7. Pour faire des traitements statistiques, il arrive qu’on transforme une variable 
quantitative en variable qualitative.    v 

8. La variable quantitative poids d’automobile peut être reclassée en compacte, intermédiaire et grosse.  v    



**Exercice 3**

```console

Proposer des exemples de variable quantitative transformée en variable qualitative.
Préciser les modalités de cette dernière.
```

| Variable |qualitative   Modalités envisageables |
|----------|--------------------------------------|
| Hauteur  | 1 m..................................|
|Poids     | lourd................................|
|Rendement | .....................................|
|Chiffre d’affaire |..............................|
|Cylindrée | .....................................|


## CHAPITRE 2

**Exercice 1**
```js
Le tableau suivant donne la répartition selon le groupe sanguin de 40 individus pris au
hasard dans une population,
```

| Groupes sanguins | A | B | AB | O |
|------------------|---|---|----|---|
| L’effectif       | 20| 10| n3 | 5 |

```js
1. Déterminer la variable statistique et son type.
    groupe sanguin de type qualitative
2. Déterminer l’effectif des personnes ayant un groupe sanguin AB.
    n3 = 40 - (20+10+5) = 5
```
**Exercice 2**

```js
Le gérant d’un magasin vendant des articles de consommation courante a relevé pour un
article particulier qui semble connaître une très forte popularité, le nombre d’articles vendus
par jour. Son relevé a porté sur les ventes des mois de Mars et Avril, ce qui correspond à
52 jours de vente. Le relevé des observations se présente comme suit :
````
| 7 | 13 | 8 | 10 | 9 | 12 | 10 | 8 | 9 | 10 | 6 | 14 | 7 | 15 | 9 | 11 | 12 | 11 | 12 | 5 | 14 | 11 | 8 | 10 | 14 | 12 | 8 |
|---|--- |---|--- |---|--- |--- |---|---|--- |---|--- |---|--- |---|--- |--- |--- |--- |---|--- |--- |---|--- |--- |--- |---|
| 5 | 7  | 13| 12 | 16| 11 | 9  | 11| 11| 12 | 12| 15 |14 | 5  | 14| 9  | 9  | 14 | 13 | 11|10  | 11 | 12| 9  | 15|.

```console

1. Quel type est la variable statistique étudiée.
    quantitative discret 
2. Déterminer le tableau statistique en fonction des effectifs, des fréquences, des effectifs
cumulés et des fréquences cumulés.
    
    from collections import Counter

a = [
    7,
    13,
    8,
    10,
    9,
    12,
    10,
    8,
    9,
    10,
    6,
    14,
    7,
    15,
    9,
    11,
    12,
    11,
    12,
    5,
    14,
    11,
    8,
    10,
    14,
    12,
    8,
    5,
    7,
    13,
    12,
    16,
    11,
    9,
    11,
    11,
    12,
    12,
    15,
    14,
    5,
    14,
    9,
    9,
    14,
    13,
    11,
    10,
    11,
    12,
    9,
    15,
]
print(a)
count = Counter(a)
print(count)
for cle, nb in count.items():
    print(cle," freq ","{:.2f}".format(nb / 52))
effcum = sorted(count.items(), reverse = False)
long = len(a)
F=0
N=0
for ef in effcum :
    N+=ef[1]
    print ("l'effectif cumulé de ",ef[0]," est " , N)
for ef in effcum :
    freq = ef[1]/52
    F+=freq
    print("la frequence cumulées de ",ef[0]," est : ",F)
print ("La courbe F(x) passe par les points : ")
for ef in effcum:
    freq = ef[1] / 52
    F += freq
    print ("(",ef[0],",",(F-1),")")
mod = []
eff = []
f = []
Nef = []
Ffe = []
N1 = 0
F1 = 0
for ef in effcum:
    mod.append(ef[0])
    eff.append(ef[1])
    f.append(ef[1] / 52)
    N1 += ef[1]
    N1 = round(N1, 2)
    Nef.append(N1)
    F1 += ef[1] / 52
    F1 = round(F1, 2)
    Ffe.append(F1)
print(mod)
print(eff)
print(Nef)
print(Ffe)
mo1 = max(effcum)
print(mo1)
mo = statistics.multimode(a)
print(mo)
som = 0 
for i,j in count.items ():
    som+= i*j
moy = som/len(a)
print (moy)
moy1 = sum(a)/len(a)
print (moy1)
mo1 = max(effcum)
print(mo1)
mo = statistics.multimode(a)
print(mo)
som = 0
for i, j in count.items():
    som += i * j
moy = som / len(a)
print(moy)
moy1 = sum(a) / len(a)
print(moy1)

4. Soit Fx la fonction de répartition. Déterminer Fx.
5. Calculer le mode Mo et la moyenne arithmétique x.
6. Déterminer à partir du tableau puis à partir du graphe, la valeur de la médiane Me.
7. Calculer la variance et l’écart-type.
````
**Exercice 3**
```console

- On considère deux groupes d’étudiants. Nous relevons leurs notes d’examens dans les deux
tableaux suivants :
```

|Note (groupe A)| 8 | 9 | 10 | 11 |
|---------------|---|---|---|---|
|Effectif | 2 | 2 | 1 | 1 |


|Note (groupe B)| 6 | 8 | 9 | 13 | 14 |
|---------------|---|---|---|---|---|
|Effectif| 2 | 2 | 2 | 1 | 1 |

```js


Calculer la moyenne et l’écart type de chaque groupe. Comparer les deux groupes.

from statistics import *
a = [8 , 8 , 9 ,9 ,10 , 11]
b = [6 , 6 , 8 ,8 ,9 ,9 ,13 ,14]
moya = mean(a)
ecarta = stdev(a)
print (moya)
print (ecarta)
moyb = mean(b)
ecartb = stdev(b)
print (moyb)
print (ecartb)
#la classe où l 'ecart est le plus elevé inquide que le niveau de la classe est disproportionné.

```
**Exercice 2**
```js
Une étude sur le budget consacré aux vacances d’été auprès de ménages a donné les
résultats suivants
```

| Budget X | Fréquence cumulée | Fréquences |
|-----------|------|----|
|[800 , 1000[|  0.08  | .... |
|[1000, 1400[| 0.18 |....|
|[1400, 1600[| 0.34 |....|
|[1600, β[| 0.64 |....|
|[β, 2400[| 0.73 |....|
|[2400, α[| 1 |....|


```js
Le travail demandé :

– Certaines données sont manquantes. Calculer la borne manquante α sachant que

l’étendue de la série est égale à 3200.

– Calculer les fréquences dans le tableau.

– Calculer la borne manquante β dans les deux cas suivants :

1. Le budget moyen est égal à 1995.

2. Le budget médian est égal à 1920.

alpha = e + 800 =4000
moy = a + 0,39 B/2 = 1800 avec a = 1644
1600 - Me/1600 - B = 0,34 - 0,5 / 0,34 - 0,64 => B= 2200 

```
