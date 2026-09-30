# Mission 6 · Contrats de maintenance : récurrent et produits constatés d'avance

**Durée :** 1 h 15 · **Prérequis :** Mission 5 validée

## 1. L'objectif financier

Facturer des contrats annuels payés d'avance et ne reconnaître en chiffre d'affaires que la part réellement acquise. Tu vas calculer le revenu récurrent mensuel (MRR) et les produits constatés d'avance (PCA) au 31/12/2026, deux indicateurs clés d'une activité d'abonnement.

## 2. La théorie du contrôle de gestion

### Le revenu récurrent

Le MRR (Monthly Recurring Revenue) additionne les montants mensuels des contrats actifs. L'ARR (Annual Recurring Revenue) vaut 12 × MRR. Ces revenus sont prévisibles : les investisseurs et les banquiers les valorisent davantage qu'un chiffre d'affaires ponctuel.

### Les produits constatés d'avance (PCA)

Un contrat annuel facturé d'avance le 1er octobre couvre 9 mois de l'exercice suivant. À la clôture, ces 9 mois sont retirés du chiffre d'affaires et placés au passif, au compte 487000.

```text
PCA = Montant facturé × Mois restant à courir ÷ 12
```

### Le principe de rattachement

Le chiffre d'affaires se rattache à la période où le service est rendu, pas à la date de la facture. C'est ce qui rend les comptes comparables d'une période à l'autre.

### La marge récurrente

Chaque contrat a un coût mensuel (hotline, supervision, pièces) : 45 € pour Essentiel et 95 € pour Premium.

```text
Taux de marque récurrent = (MRR − coûts mensuels) ÷ MRR
```

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Comptabilité → Configuration → Paramètres → Revenus différés`

Active la gestion des revenus différés (le libellé peut être Produits constatés d'avance). Compte : 487000 Produits constatés d'avance. Génération des écritures : à la validation. Calcul : par mois égaux. Enregistre.

### Étape 2

`Comptabilité → Clients → Factures → Nouveau`

Crée les 3 factures annuelles. Sur chaque ligne, renseigne les colonnes Date de début et Date de fin (affiche-les avec l'icône des colonnes optionnelles si besoin). Quantité 12, TVA 20 %.

| Date facture | Client | Produit | Prix mensuel | Total HT | Période couverte |
| --- | --- | --- | --- | --- | --- |
| 01/10/2026 | Logistique Rhône Express SARL | MAINT-PRE | 240,00 | 2 880,00 | 01/10/2026 → 30/09/2027 |
| 01/11/2026 | Entrepôts Gerland Logistique SAS | MAINT-PRE | 240,00 | 2 880,00 | 01/11/2026 → 31/10/2027 |
| 01/12/2026 | Résidences Seniors Confluence SAS | MAINT-ESS | 120,00 | 1 440,00 | 01/12/2026 → 30/11/2027 |

### Étape 3

`Comptabilité → Clients → Factures → (facture) → Confirmer`

Confirme les 3 factures. Odoo génère les écritures de report : le chiffre d'affaires est étalé mois par mois.

### Étape 4

`Comptabilité → Rapports → Balance générale`

Règle la date au 31/12/2026 et lis le solde du compte 487000.

### Étape 5

`Excel → nouvel onglet Maintenance`

Construis l'échéancier des contrats : une ligne par contrat, une colonne par mois d'octobre 2026 à novembre 2027. Formule par cellule : prix mensuel si le mois est dans la période du contrat, sinon 0 (par exemple =SI(ET(mois>=début;mois<=fin);prix;0)). Déduis le CA 2026, les PCA au 31/12/2026, le MRR de décembre et le taux de marque récurrent.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] Les 3 factures portent des dates de début et de fin sur leurs lignes.
- [ ] Le compte 487000 a un solde créditeur au 31/12/2026.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Produits constatés d'avance au 31/12/2026 | € | Σ montant × mois restants ÷ 12 |
| CA de maintenance reconnu en 2026 | € | Facturé − PCA |
| MRR en décembre 2026 | € | Somme des prix mensuels actifs |
| Taux de marque récurrent | % | (600 − 235) ÷ 600 |

---

[← Programme](../README.md#programme)
