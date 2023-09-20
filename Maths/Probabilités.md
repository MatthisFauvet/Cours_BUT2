**But : modéliser les expériences aléatoires**
Exemple : Résultats lancé de pièce, de dès, etc.

## I - Espace probabilisé

### 1. Univers

On note Ω (Omega), l'ensemble de toutes les issues possibles :
_Exemple (pièce) : Ω={pile; face}_
les issues sont notées **ω (omega)**.

Les parties de Ω (Omega) sont appelées **événement**
_Exemple : On lance 2 dés discernables_
_Ω = {(i, j), i, j, ... E 1 ... 6} = {(1,1), (1,2), ... , (6,6)}_
_A = "La somme de = G" = {(1,3),(2,2),(3,1)}_ C _Ω_ avec A un événement.

Si A, B, ... Sont des événements. Alors : 

A⋂B = AB (A et B)
![Intersection](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Venn_A_intersect_B.svg/1280px-Venn_A_intersect_B.svg.png)
A∪B = (A ou B)
![Union](https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Venn_diagram_for_A_union_B.svg/1920px-Venn_diagram_for_A_union_B.svg.png)



### 2. Probabilité

On veut attribuer à tout évenement ACΩ une probabilité p(A)

**Idée** si on répète l'expérience N fois, et si A se réalise n(A) fois, alors p(A) ≈ n(A)/n quand N -> ∞

On en déduit que : 

1. 0 <= p(A) <= 1 et p(Ω)=1

2. Si AB = ∅ (incompatible) alors :
	- p(AUB) ≈ n(AUB)/n = n(A)+n(B)/n = n(A)/n + n(B)/n -> p(A) + p(B)

	- Donc p(AUB) = p(A) + p(B) si AB=∅

	- Sinon, p(AUB) = p(A) + p(B) - p(AB)
			             = p(A/B) + p(AB) + p(B/A)
			                          p(A)        p(B) - p(AB)
	- On en déduit aussi :
		- p(Ā) = p(Ω) - p(A) = 1 - p(A)
	                     p(A∪B∪C) = p(A) + p(B) + p(C) - p(AB) - p(AC) - p(BC) + p(ABC)

Toutes p(A) qui vérifie 1. et 2. est une proba sur Ω.

**Comment définir p ?**

Si Ω est dénombrable, alors Ω = {ω1, ω2, ωn}

Il suffit de la définir p(ω) pour ∀ ω  ∊ Ω
tant que Σp(ω) = 1 = p(Ω)

On pose alors p(A) = Σp(ω) alors p(A) vérifie 1. et 2.

Cas d'équiprobabilité  : |Ω| = n (fini)

___

On suppose que p(ω1) = p(ω2) = ... = 1/n = 1/|Ω|
=> p(A) = 2p(ω) = |A|/|Ω| (dénombrables)

Ex : On lance 2 dés discernables 

Ω = {(i, j), i, j ∊ 1 ... 6}
|Ω|  = 6² = 36 => p(ω) = 1/36
p(Somme = 4) = 3/36 = 1/12
   trois couples

On lance 2 dès **identiques**
Ω = {[i,j], i, j ∊ 1, ..., 6} = {[1, 1], [1,2], ..., [6,6]}
	|Ω| = 6 = 2C6 = 6 + 15 = 21

**Equiprobable ?**

Si oui, p(Somme = 4) = (2/21) ≠ (1/12)
NON



### Chars spéciaux :

Ωω
∊∪
Σ
≠≈