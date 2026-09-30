# Mission 7 · Frais de structure et clés de répartition

**Durée :** 1 h 30 · **Prérequis :** Mission 6 validée

## 1. L'objectif financier

Passer de la marge directe au résultat analytique de chaque pôle. Tu vas enregistrer les frais de structure du 4e trimestre, puis les répartir selon deux clés différentes et constater que le choix de la clé change la rentabilité apparente d'un pôle.

## 2. La théorie du contrôle de gestion

### Charges directes et indirectes

Une charge directe se rattache sans ambiguïté à un pôle (le matériel acheté pour MAT). Une charge indirecte profite à tous (loyer, expert-comptable) : il faut la répartir avec une clé.

### La clé de répartition

Une clé est une unité qui reflète la consommation des ressources communes : chiffre d'affaires, heures de main-d'œuvre, effectif, surface… Une bonne clé suit la cause réelle de la charge.

```text
Charge allouée au pôle = Charges indirectes × (Clé du pôle ÷ Clé totale)
```

### Marge directe et résultat analytique

La marge directe mesure ce que chaque pôle apporte. Le résultat analytique retranche en plus sa part des frais de structure.

```text
Résultat analytique = Marge directe − Frais de structure alloués
```

### Le piège de la répartition

Toute clé est une convention. Ne supprime jamais un pôle parce que son résultat analytique est faible : les frais de structure ne disparaîtraient pas avec lui. Raisonne d'abord sur la marge directe.

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Contacts → Nouveau`

Crée les 4 fournisseurs de frais généraux.

| Fournisseur | Nature |
| --- | --- |
| SCI Les Artisans | Loyer du siège |
| Fiduciaire Rhône Audit | Expert-comptable |
| Mutuelle Pro Assurances | Assurance RC professionnelle |
| Cloudtel Services | Logiciels et télécom |

### Étape 2

`Comptabilité → Fournisseurs → Factures → Nouveau`

Saisis les 6 factures. Sur chaque ligne, choisis le compte indiqué et la distribution analytique STRUCT 100 %.

| Date | Fournisseur | Compte | Montant HT | TVA |
| --- | --- | --- | --- | --- |
| 01/10/2026 | SCI Les Artisans | 613200 Locations immobilières | 3 000,00 | 20 % |
| 01/11/2026 | SCI Les Artisans | 613200 Locations immobilières | 3 000,00 | 20 % |
| 01/12/2026 | SCI Les Artisans | 613200 Locations immobilières | 3 000,00 | 20 % |
| 05/10/2026 | Mutuelle Pro Assurances | 616000 Primes d'assurances | 1 200,00 | Aucune |
| 31/10/2026 | Cloudtel Services | 626000 Frais postaux et télécom | 1 500,00 | 20 % |
| 15/12/2026 | Fiduciaire Rhône Audit | 622600 Honoraires | 1 800,00 | 20 % |

### Étape 3

`Comptabilité → Rapports → Analytique`

Filtre sur le 4e trimestre 2026 (01/10 au 31/12) et lis le total du compte STRUCT.

### Étape 4

`Excel → nouvel onglet Répartition`

Saisis la synthèse du trimestre ci-dessous. Elle consolide tes missions et le reste de l'activité d'Altiplan.

| Pôle | CA T4 | Coûts directs | Marge directe | Heures techniciens |
| --- | --- | --- | --- | --- |
| MAT | 118 000 | 80 240 | 37 760 | 150 |
| INST | 96 000 | 62 400 | 33 600 | 1 900 |
| MAINT | 24 000 | 9 600 | 14 400 | 450 |
| Total | 238 000 | 152 240 | 85 760 | 2 500 |

### Étape 5

`Excel → onglet Répartition`

Répartis les 13 500 € de STRUCT avec la clé CA, puis avec la clé heures. Pour chaque clé, calcule le résultat analytique et le taux de résultat (résultat ÷ CA) de chaque pôle. Mets les deux versions côte à côte et commente l'écart pour INST dans tes notes.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] Le rapport analytique affiche 13 500,00 € de charges sur STRUCT pour le trimestre.
- [ ] Les deux répartitions totalisent bien 13 500 €.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Frais alloués à INST avec la clé CA | € | 13 500 × 96 000 ÷ 238 000 |
| Résultat analytique d'INST avec la clé heures | € | 33 600 − 13 500 × 1 900 ÷ 2 500 |
| Taux de résultat d'INST avec la clé heures | % | Résultat ÷ CA d'INST |

---

[← Programme](../README.md#programme)
