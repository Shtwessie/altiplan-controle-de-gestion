# Mission 9 · Budget et analyse des écarts

**Durée :** 1 h 30 · **Prérequis :** Mission 8 validée

## 1. L'objectif financier

Comparer le réalisé du 4e trimestre au budget et expliquer chaque écart. Tu vas décomposer l'écart de marge en effet volume et effet taux : c'est ce qui permet de dire au dirigeant non seulement combien, mais pourquoi.

## 2. La théorie du contrôle de gestion

### Le budget

Traduction chiffrée des objectifs de la période, par pôle. Il sert de référence pour mesurer la performance, pas de prévision parfaite.

### Écart favorable ou défavorable

Un écart est favorable s'il améliore le résultat (plus de CA, moins de coûts) et défavorable sinon. On l'exprime toujours en impact sur le résultat.

```text
Écart = Réel − Budget (signe inversé pour les charges)
```

### Effet volume et effet taux

L'écart de marge d'un pôle se décompose en deux causes indépendantes.

```text
Écart sur volume = (CA réel − CA budget) × Taux de marge budget
Écart sur taux   = (Taux réel − Taux budget) × CA réel
Écart total      = Écart volume + Écart taux
```

### Taux de réalisation

Rapport entre réel et budget. Au-dessus de 100 % pour le CA, l'objectif est dépassé.

```text
Taux de réalisation = Réel ÷ Budget
```

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Comptabilité → Comptabilité → Budgets → Nouveau`

Crée le budget « Budget T4 2026 », période du 01/10/2026 au 31/12/2026. Ajoute une ligne par compte analytique avec le montant net prévu (produits − charges). Selon ta version, le menu peut se trouver dans Comptabilité → Configuration.

| Compte analytique | Montant prévu |
| --- | --- |
| MAT | 38 500,00 |
| INST | 42 000,00 |
| MAINT | 13 200,00 |
| STRUCT | −12 900,00 |

### Étape 2

`Comptabilité → Rapports → Analyse budgétaire`

Compare le prévu au réalisé dans Odoo. Le réalisé Odoo ne contient que tes exercices : les chiffres complets du trimestre sont dans Excel.

### Étape 3

`Excel → nouvel onglet Budget`

Saisis le budget détaillé et reprends le réel de la Mission 7.

| Pôle | CA budget | Marge budget | CA réel | Marge réelle |
| --- | --- | --- | --- | --- |
| MAT | 110 000 | 38 500 | 118 000 | 37 760 |
| INST | 105 000 | 42 000 | 96 000 | 33 600 |
| MAINT | 22 000 | 13 200 | 24 000 | 14 400 |
| STRUCT | — | −12 900 | — | −13 500 |

### Étape 4

`Excel → onglet Budget`

Calcule pour chaque pôle le taux de marge budget et réel, l'écart sur volume, l'écart sur taux et l'écart total. Calcule ensuite l'écart de résultat global et le taux de réalisation du CA.

### Étape 5

`Excel → Insertion → Graphique en cascade`

Construis un graphique en cascade du résultat : budget 80 800 €, puis chaque écart (volume et taux par pôle, frais de structure), jusqu'au réel de 72 260 €.

## 4. La validation

**À vérifier dans :** Excel

- [ ] Pour chaque pôle, écart volume + écart taux = écart de marge total.
- [ ] Le graphique en cascade part de 80 800 € et arrive à 72 260 €.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Écart de résultat global | € | 72 260 − 80 800 |
| Écart sur taux du pôle INST | € | (35 % − 40 %) × 96 000 |
| Écart sur volume du pôle MAT | € | (118 000 − 110 000) × 35 % |
| Taux de réalisation du CA | % | 238 000 ÷ 237 000 |

---

[← Programme](../README.md#programme)
