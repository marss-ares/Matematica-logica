# Formule pentru FND / FNC (foaie de printat)

F, G, H = orice variabilă sau formulă. Negația se scrie cu bară deasupra: F̅ = „non F”.
Când bara acoperă un grup, scriem `non(...)`: `non(F ∧ G)` = bara peste tot grupul.

## Algoritmul (în ordine)

1. **Elimini → și ↔**, folosind formulele din tabelul 1.
2. **Muți negațiile la variabile** (De Morgan, tabelul 2), până când bara stă doar pe variabile.
3. **Distribui**: `∧` peste `∨` pentru **FND**, `∨` peste `∧` pentru **FNC** (tabelul 3).
4. **Simplifici** cu tabelul 4.

Prima regulă: întâi elimini → și ↔, pentru că De Morgan merge doar peste `∧` și `∨`.

## 1. Elimini → și ↔

| Ai | | Devine | Nume |
|---|---|---|---|
| F → G | ≡ | F̅ ∨ G | implicația |
| F ↔ G | ≡ | (F → G) ∧ (G → F) | echivalența, în două implicații |
| F ↔ G | ≡ | (F̅ ∨ G) ∧ (G̅ ∨ F) | forma FNC |
| F ↔ G | ≡ | (F ∧ G) ∨ (F̅ ∧ G̅) | forma FND |

## 2. Negația (De Morgan și rude)

| Ai | | Devine | Nume |
|---|---|---|---|
| non non F (bară dublă) | ≡ | F | dubla negație |
| non(F ∧ G) | ≡ | F̅ ∨ G̅ | De Morgan |
| non(F ∨ G) | ≡ | F̅ ∧ G̅ | De Morgan |
| non(F → G) | ≡ | F ∧ G̅ | negarea implicației |
| non(F ↔ G) | ≡ | (F ∧ G̅) ∨ (F̅ ∧ G) | negarea echivalenței |
| F → G | ≡ | G̅ → F̅ | contrapoziția (rămâne implicație, nu elimină nimic) |

## 3. Distribuirea

| Ai | | Devine | Pentru |
|---|---|---|---|
| F ∧ (G ∨ H) | ≡ | (F ∧ G) ∨ (F ∧ H) | FND |
| F ∨ (G ∧ H) | ≡ | (F ∨ G) ∧ (F ∨ H) | FNC |

## 4. Simplificarea

| Ai | | Devine | Nume |
|---|---|---|---|
| F ∨ F̅ | ≡ | 1 | tautologie |
| F ∧ F̅ | ≡ | 0 | contradicție |
| F ∧ F | ≡ | F | idempotență |
| F ∨ F | ≡ | F | idempotență |
| F ∨ 0 | ≡ | F | element neutru |
| F ∧ 1 | ≡ | F | element neutru |
| F ∨ 1 | ≡ | 1 | dominare |
| F ∧ 0 | ≡ | 0 | dominare |
| non 1 | ≡ | 0 | negația constantelor |
| non 0 | ≡ | 1 | negația constantelor |
| F ∨ (F ∧ G) | ≡ | F | absorbție |
| F ∧ (F ∨ G) | ≡ | F | absorbție |
| F ∧ G | ≡ | G ∧ F | comutativitate (la fel pentru ∨) |
| (F ∧ G) ∧ H | ≡ | F ∧ (G ∧ H) | asociativitate (la fel pentru ∨) |

## 5. Forma perfectă (FDNP / FCNP)

Fiecare termen conține **toate** variabilele. Se citește direct din tabelul de adevăr.

| Formă | Rânduri | Termenii | Variabila |
|---|---|---|---|
| FDNP | cele cu **f = 1** | legați cu ∧, termenii legați cu ∨ | 0 → cu bară, 1 → fără bară |
| FCNP | cele cu **f = 0** | legați cu ∨, termenii legați cu ∧ | 0 → fără bară, 1 → cu bară |

Dacă lipsesc variabile dintr-un termen, le completezi:
- în FND: `F ≡ F ∧ (G ∨ G̅)`, apoi distribui;
- în FNC: `F ≡ F ∨ (G ∧ G̅)`, apoi distribui.

## Exemplu rezolvat: `(A ∧ B) → (B ∨ A)`

1. Elimini implicația: `non(A ∧ B) ∨ (B ∨ A)`
2. De Morgan: `(A̅ ∨ B̅) ∨ (B ∨ A)`
3. Scoți parantezele și grupezi: `A̅ ∨ A ∨ B̅ ∨ B`
4. `A̅ ∨ A ≡ 1`, deci `1 ∨ B̅ ∨ B ≡ 1`

Rezultat: `1`, adică tautologie. FND = FNC = 1.

## Exemplul 2: `(A → B) → C`

1. Elimini implicația din interior: `(A̅ ∨ B) → C`
2. Elimini implicația din exterior: `non(A̅ ∨ B) ∨ C`
3. De Morgan: `(A ∧ B̅) ∨ C` ← aceasta este **FND**
4. Distribui `∨` peste `∧`: `(A ∨ C) ∧ (B̅ ∨ C)` ← aceasta este **FNC**

## Capcane

- Implicația se desface în `non F ∨ G`, nu în `non F ∧ G`.
- Reciproca `G → F` **nu** e echivalentă cu `F → G`. Contrapoziția `G̅ → F̅` este.
- La De Morgan se schimbă și operatorul (`∧` devine `∨` și invers), și bara se mută pe fiecare parte.
- Termenul `X ∧ X̅` este 0 și dispare dintr-un `∨`. Termenul `X ∨ X̅` este 1 și dispare dintr-un `∧`.
- Verifici mereu cu tabelul pe câteva rânduri.
