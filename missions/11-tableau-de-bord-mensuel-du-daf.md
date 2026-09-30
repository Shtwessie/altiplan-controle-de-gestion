# Mission 11 · Tableau de bord mensuel du DAF

**Durée :** 2 h · **Prérequis :** Mission 10 validée

## 1. L'objectif financier

Assembler tout le parcours dans un tableau de bord d'une page, que le dirigeant peut lire en deux minutes. Tu vas choisir les bons indicateurs, calculer le seuil de rentabilité et présenter les résultats du trimestre avec des alertes visuelles.

## 2. La théorie du contrôle de gestion

### Un bon tableau de bord

Peu d'indicateurs (6 à 10), chacun comparé à une référence (budget, période précédente), avec une alerte visuelle. Il répond à trois questions : où en est-on, pourquoi, que faire.

### Marge sur coûts variables

Les coûts directs d'Altiplan varient avec l'activité ; les frais de structure sont fixes. Le taux de marge sur coûts variables mesure ce que rapporte chaque euro de CA pour couvrir les charges fixes.

```text
Taux de MCV = Marge directe ÷ CA
```

### Seuil de rentabilité et point mort

Le seuil est le CA qui couvre exactement les charges fixes. Le point mort est la date à laquelle il est atteint dans la période.

```text
Seuil de rentabilité = Charges fixes ÷ Taux de MCV
Point mort (jours) = Seuil ÷ CA × nb de jours
Marge de sécurité = CA − Seuil
```

### Les indicateurs de trésorerie

Un résultat positif ne garantit pas la trésorerie : le DSO et les PCA complètent la lecture. Un DSO qui monte est une alerte, même avec un bon résultat.

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Comptabilité → Rapports → Compte de résultat`

Filtre sur le 4e trimestre 2026, active la comparaison avec la période précédente et exporte en XLSX. C'est la source officielle à rapprocher de ton tableau de bord.

### Étape 2

`Comptabilité → Rapports → Analytique`

Groupe par plan analytique sur le trimestre et exporte. Ajoute la vue à tes favoris pour la retrouver chaque mois.

### Étape 3

`Excel → nouvel onglet Tableau de bord`

Rassemble les indicateurs ci-dessous. Sources : Missions 6, 7, 9 et 10.

| Indicateur | Réel | Référence | Source |
| --- | --- | --- | --- |
| CA T4 | 238 000 € | Budget 237 000 € | Mission 9 |
| Marge directe | 85 760 € | Budget 93 700 € | Mission 9 |
| Frais de structure | 13 500 € | Budget 12 900 € | Mission 7 |
| Résultat analytique | 72 260 € | Budget 80 800 € | Mission 9 |
| DSO | 71,43 j | Objectif 60 j | Mission 10 |
| MRR maintenance | 600 € | — | Mission 6 |

### Étape 4

`Excel → onglet Tableau de bord`

Calcule le taux de marge sur coûts variables, le seuil de rentabilité du trimestre, le point mort en jours (92 jours) et le taux de résultat. Ajoute une mise en forme conditionnelle : vert si le réel atteint la référence, orange à moins de 10 % d'écart, rouge au-delà.

### Étape 5

`Excel → Insertion → Graphiques`

Ajoute 3 graphiques : CA et marge par pôle (budget ou réel, histogramme groupé), la cascade de résultat de la Mission 9, et l'évolution des créances par tranche d'âge (barres empilées).

### Étape 6

`Excel → zone Commentaire`

Rédige 3 phrases pour le dirigeant : le fait marquant du trimestre, sa cause principale, et une action proposée (par exemple réviser le budget d'heures des forfaits d'installation).

## 4. La validation

**À vérifier dans :** Excel

- [ ] Le tableau de bord tient sur une page imprimée.
- [ ] Chaque indicateur est comparé à une référence avec une couleur d'alerte.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Taux de marge sur coûts variables | % | 85 760 ÷ 238 000 |
| Seuil de rentabilité du trimestre | € | 13 500 ÷ taux de MCV |
| Point mort | j | Seuil ÷ CA × 92 |
| Taux de résultat analytique | % | 72 260 ÷ 238 000 |

---

[← Programme](../README.md#programme)
