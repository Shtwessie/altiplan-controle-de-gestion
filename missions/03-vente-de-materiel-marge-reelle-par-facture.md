# Mission 3 · Vente de matériel : marge réelle par facture

**Durée :** 1 h · **Prérequis :** Mission 2 validée

## 1. L'objectif financier

Suivre une vente de matériel de bout en bout (devis, livraison, facture) et mesurer sa marge réelle, calculée au coût moyen du stock et non au coût du catalogue. Tu verras aussi pourquoi le rapport analytique d'Odoo ne donne pas directement cette marge en comptabilité française.

## 2. La théorie du contrôle de gestion

### Marge théorique ou marge réelle

La marge théorique utilise le coût du catalogue. La marge réelle utilise le coût du stock au moment de la livraison (ici le CUMP de 146,80 € pour la caméra) et tient compte des remises accordées.

### La remise commerciale

Une remise de 5 % sur un produit à 37 % de marque ne réduit pas la marge de 5 %, mais de beaucoup plus : c'est de la marge pure qui disparaît.

```text
Marge après remise = PV × (1 − remise) − Coût
```

### Comptabilité continentale et analytique

En France, les achats sont passés en charges (compte 607) à la réception de la facture fournisseur, et le stock est ajusté à la clôture. Le rapport analytique MAT montre donc les achats de la période, pas le coût des produits vendus. La marge par vente se lit dans les ventes (champ Marge) ou se recalcule dans Excel.

### Coût des ventes

Coût des produits réellement livrés, valorisés au coût du stock.

```text
Coût des ventes = Σ quantités livrées × CUMP
Taux de marque = (CA HT − Coût des ventes) ÷ CA HT
```

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Ventes → Configuration → Paramètres → Tarification`

Coche Marges et Remises, puis enregistre. Une colonne Marge apparaît sur les devis.

### Étape 2

`Contacts → Nouveau`

Crée le client (société), Conditions de paiement = 30 jours.

| Champ | Valeur |
| --- | --- |
| Nom | Entrepôts Gerland Logistique SAS |
| Adresse | 45 avenue Tony Garnier, 69007 Lyon |
| Conditions de paiement | 30 jours |

### Étape 3

`Ventes → Commandes → Devis → Nouveau`

Devis du 26/10/2026 pour Entrepôts Gerland Logistique SAS. Applique la remise de 5 % sur la ligne des caméras uniquement. Confirme le devis.

| Produit | Quantité | Prix unitaire HT | Remise | Total HT |
| --- | --- | --- | --- | --- |
| CAM-IP4K | 12 | 229,00 | 5 % | 2 610,60 |
| SW-24P | 2 | 590,00 | — | 1 180,00 |
| NVR-16 | 1 | 820,00 | — | 820,00 |
| AP-WF6 | 2 | 185,00 | — | 370,00 |

### Étape 4

`Ventes → (commande) → onglet Autres informations`

Lis la marge calculée par Odoo en bas de la commande, et son pourcentage.

### Étape 5

`Ventes → (commande) → Livraison → Valider`

Valide la livraison au 27/10/2026. Le stock de caméras passe de 50 à 38.

### Étape 6

`Ventes → (commande) → Créer une facture → Facture normale`

Date de facturation : 28/10/2026. Vérifie le total (4 980,60 € HT, 5 976,72 € TTC) et confirme.

### Étape 7

`Comptabilité → Rapports → Analytique`

Filtre sur octobre 2026 et regarde le compte MAT : les produits de la vente et les achats du mois apparaissent, sans coût des ventes. Note l'écart dans ton Journal.

### Étape 8

`Excel → nouvel onglet Ventes`

Reconstitue la marge de la commande : pour chaque ligne, CA HT après remise, coût (quantité × CUMP de la Mission 2), marge et taux de marque. Calcule aussi la marge perdue à cause de la remise.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] La livraison est au statut Fait et le stock de CAM-IP4K affiche 38 unités.
- [ ] La facture de 5 976,72 € TTC est confirmée.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Marge de la commande (champ Marge d'Odoo) | € | CA HT après remise − coût au CUMP |
| Taux de marque de la commande | % | Marge ÷ CA HT |
| Marge perdue à cause de la remise | € | 12 × 229 × 5 % |

---

[← Programme](../README.md#programme)
