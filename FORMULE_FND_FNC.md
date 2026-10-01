# Formule FND / FNC — ce se transformă în ce

X, Y, Z = orice variabilă sau formulă. Bara deasupra (X̅) = negație („non X”). `non(...)` = bara peste tot grupul.
Versiunea interactivă, cu bara desenată peste grupuri: `FND_FNC_interactiv.html`.

**Algoritm:** 1) elimini → și ↔; 2) muți negațiile la variabile (De Morgan); 3) distribui (∧ peste ∨ pentru FND, ∨ peste ∧ pentru FNC); 4) simplifici.

## Elimini → și ↔ (primul pas)

| Ai | | Devine | Nume |
|---|---|---|---|
| X → Y | ≡ | X̅ ∨ Y | implicația |
| X ↔ Y | ≡ | (X̅ ∨ Y) ∧ (Y̅ ∨ X) | forma FNC |
| X ↔ Y | ≡ | (X ∧ Y) ∨ (X̅ ∧ Y̅) | forma FND |

## Negația (pasul 2)

| Ai | | Devine | Nume |
|---|---|---|---|
| non non X (bară dublă) | ≡ | X | dubla negație |
| non(X ∧ Y) | ≡ | X̅ ∨ Y̅ | De Morgan |
| non(X ∨ Y) | ≡ | X̅ ∧ Y̅ | De Morgan |
| non(X → Y) | ≡ | X ∧ Y̅ | negarea implicației |
| non(X ↔ Y) | ≡ | (X ∧ Y̅) ∨ (X̅ ∧ Y) | negarea echivalenței |
| X → Y | ≡ | Y̅ → X̅ | contrapoziția |

## Distribuirea (pasul 3)

| Ai | | Devine | Nume |
|---|---|---|---|
| X ∧ (Y ∨ Z) | ≡ | (X ∧ Y) ∨ (X ∧ Z) | pentru FND |
| X ∨ (Y ∧ Z) | ≡ | (X ∨ Y) ∧ (X ∨ Z) | pentru FNC |

## Simplificarea (pasul 4)

| Ai | | Devine | Nume |
|---|---|---|---|
| X ∨ X̅ | ≡ | 1 | tautologie |
| X ∧ X̅ | ≡ | 0 | contradicție |
| X ∧ X | ≡ | X | idempotență |
| X ∨ X | ≡ | X | idempotență |
| X ∨ 0 | ≡ | X | element neutru |
| X ∧ 1 | ≡ | X | element neutru |
| X ∨ 1 | ≡ | 1 | dominare |
| X ∧ 0 | ≡ | 0 | dominare |
| non 1 | ≡ | 0 | negația constantelor |
| non 0 | ≡ | 1 | negația constantelor |
| X ∨ (X ∧ Y) | ≡ | X | absorbție |
| X ∧ (X ∨ Y) | ≡ | X | absorbție |
| X ∧ Y | ≡ | Y ∧ X | comutativitate (la fel pentru ∨) |
| (X ∧ Y) ∧ Z | ≡ | X ∧ (Y ∧ Z) | asociativitate (la fel pentru ∨) |

## Forma perfectă (completezi variabilele lipsă)

| Ai | | Devine | Nume |
|---|---|---|---|
| X (în FND) | ≡ | X ∧ (Y ∨ Y̅) | apoi distribui ∧ peste ∨ |
| X (în FNC) | ≡ | X ∨ (Y ∧ Y̅) | apoi distribui ∨ peste ∧ |

