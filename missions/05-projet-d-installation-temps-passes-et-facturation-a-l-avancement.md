# Mission 5 · Projet d'installation : temps passés et facturation à l'avancement

**Durée :** 2 h · **Prérequis :** Mission 4 validée

## 1. L'objectif financier

Piloter la rentabilité d'un chantier au forfait. Tu vas vendre un projet avec facturation par jalons, saisir les heures des équipes valorisées au coût horaire, puis comparer ce qui est facturé à ce qui est réellement produit. L'écart donne la facture à établir (FAE), un classique des clôtures.

## 2. La théorie du contrôle de gestion

### Forfait ou régie

En régie, le client paie les heures passées : le risque est pour lui. Au forfait, le prix est fixe : chaque heure de dépassement réduit la marge d'Altiplan. Le forfait exige donc un budget d'heures et un suivi serré.

### Facturation par jalons

Le forfait est facturé par étapes validées avec le client (ici 40 % au câblage, 60 % à la recette). La facturation suit le calendrier contractuel, pas le travail réellement produit.

### Avancement par les coûts

À une clôture, on mesure le travail produit par la part du budget de coûts déjà consommée. Le chiffre d'affaires acquis se déduit de cet avancement.

```text
Avancement = Coûts engagés ÷ Coûts budgétés
CA acquis = Prix du forfait × Avancement
FAE = CA acquis − CA facturé (si positif)
PCA = CA facturé − CA acquis (si négatif)
```

### Coût d'un chantier

Heures × coût horaire chargé de chaque personne, plus le matériel posé au coût moyen. Le taux horaire chargé du chef de projet est plus élevé : 420 € par jour ÷ 8 h = 52,50 €.

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Projet → Configuration → Paramètres`

Coche Jalons et Feuilles de temps (si ce n'est pas déjà fait), puis enregistre.

### Étape 2

`Employés → Nouveau`

Crée les 3 personnes du chantier. Dans l'onglet Paramètres RH, renseigne le Coût horaire.

| Employé | Poste | Coût horaire |
| --- | --- | --- |
| Karim Benali | Technicien | 38,00 |
| Julie Moreau | Technicienne | 38,00 |
| Thomas Girard | Chef de projet | 52,50 |

### Étape 3

`Ventes → Produits → Produits → Nouveau`

Crée le produit de forfait.

| Champ | Valeur |
| --- | --- |
| Nom | Forfait installation vidéoprotection |
| Type | Service |
| Catégorie | Installation |
| Prix de vente | 9 000,00 |
| Coût | 0,00 (le coût viendra des feuilles de temps) |
| Politique de facturation | Basée sur des jalons |
| Créer sur commande | Projet et tâche |

### Étape 4

`Contacts → Nouveau`

Client : Résidences Seniors Confluence SAS, 12 cours Charlemagne, 69002 Lyon. Conditions de paiement : 30 jours.

### Étape 5

`Ventes → Commandes → Devis → Nouveau`

Devis du 03/11/2026. Confirme-le : Odoo crée automatiquement le projet et sa tâche.

| Produit | Quantité | Prix unitaire HT | Total HT |
| --- | --- | --- | --- |
| CAM-IP4K | 16 | 229,00 | 3 664,00 |
| SW-24P | 2 | 590,00 | 1 180,00 |
| NVR-16 | 1 | 820,00 | 820,00 |
| Forfait installation vidéoprotection | 1 | 9 000,00 | 9 000,00 |

### Étape 6

`Projet → (projet Résidences Seniors Confluence) → Jalons`

Crée les 2 jalons, liés à la ligne du forfait. Budget interne du chantier : 120 h de techniciens et 24 h de chef de projet, soit 5 820 € de coûts.

| Jalon | Quantité à facturer | Date prévue |
| --- | --- | --- |
| Câblage terminé | 40 % | 27/11/2026 |
| Mise en service et recette | 60 % | 18/12/2026 |

### Étape 7

`Ventes → (commande) → Livraison → Valider, puis Créer une facture`

Livre le matériel le 10/11/2026 et facture-le le même jour (5 664,00 € HT). Le forfait n'est pas encore facturable.

### Étape 8

`Feuilles de temps → Toutes les feuilles de temps → Nouveau`

Saisis les heures sur le projet (une ligne par personne et par date).

| Date | Karim Benali | Julie Moreau | Thomas Girard |
| --- | --- | --- | --- |
| 03/11/2026 | — | — | 4 h |
| 10/11/2026 | 16 h | 16 h | — |
| 17/11/2026 | 12 h | 16 h | 4 h |
| 24/11/2026 | 12 h | 12 h | — |
| 27/11/2026 | — | — | 4 h |
| 08/12/2026 | 12 h | 14 h | — |
| 10/12/2026 | — | — | 4 h |
| 15/12/2026 | 10 h | 12 h | — |
| 18/12/2026 | — | — | 4 h |

### Étape 9

`Projet → Jalons → Câblage terminé → Atteint`

Marque le jalon comme atteint au 27/11/2026, puis sur la commande, Créer une facture au 30/11/2026 (3 600,00 € HT). Fais de même pour le jalon 2 au 18/12/2026 (5 400,00 € HT).

### Étape 10

`Projet → (projet) → Rentabilité`

Lis la synthèse de rentabilité : chiffre d'affaires facturé et coût des feuilles de temps.

### Étape 11

`Feuilles de temps → Toutes les feuilles de temps → vue Liste → ⚙ Actions → Exporter`

Exporte Date, Employé, Projet, Durée et Montant (le coût, en négatif). Dans Excel, filtre les heures jusqu'au 30/11/2026 et calcule l'avancement par les coûts, le CA acquis et la FAE à cette date. Calcule ensuite la marge finale du forfait et du projet complet (matériel au coût moyen de 146,80 € pour la caméra).

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] La Rentabilité du projet affiche un coût des feuilles de temps de 6 066,00 €.
- [ ] Les deux jalons sont atteints et les trois factures du projet sont confirmées.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Facture à établir (FAE) au 30/11/2026 | € | 9 000 × (coûts au 30/11 ÷ 5 820) − 3 600 |
| Taux de marque réel du forfait | % | (9 000 − coût des heures) ÷ 9 000 |
| Taux de marque du projet complet | % | Matériel + forfait, coûts au CUMP et aux heures |

---

[← Programme](../README.md#programme)
