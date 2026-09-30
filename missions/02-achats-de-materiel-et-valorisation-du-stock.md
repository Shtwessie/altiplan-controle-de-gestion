# Mission 2 · Achats de matériel et valorisation du stock

**Durée :** 1 h 30 · **Prérequis :** Mission 1 validée

## 1. L'objectif financier

Suivre le cycle d'achat complet (commande, réception, facture fournisseur) et comprendre comment Odoo valorise le stock au coût moyen pondéré. Une hausse du prix d'achat modifie le coût de revient, donc la marge : le contrôleur de gestion doit la voir avant qu'elle n'apparaisse dans les comptes.

## 2. La théorie du contrôle de gestion

### Le cycle achat en trois documents

Commande fournisseur (engagement), bon de réception (entrée physique en stock) et facture fournisseur (dette). Le rapprochement de ces trois documents, appelé « three-way match », évite de payer une marchandise non reçue ou facturée au mauvais prix.

### Le coût moyen pondéré (AVCO)

À chaque réception, Odoo recalcule le coût unitaire du produit en pondérant le stock existant et l'entrée.

```text
Nouveau CUMP = (Stock × ancien coût + Quantité reçue × prix d'achat)
              ÷ (Stock + Quantité reçue)
```

### Valorisation manuelle ou automatisée

En valorisation automatisée, chaque mouvement de stock génère une écriture comptable (compte 31x ou 37x). Le stock du bilan suit alors le stock physique en temps réel.

### L'effet prix sur la marge

Si le prix d'achat monte et que le prix de vente ne bouge pas, le taux de marque baisse. Un contrôleur de gestion suit l'écart de prix d'achat pour alerter les commerciaux.

```text
Écart de prix = (Nouveau prix − Ancien prix) ÷ Ancien prix
```

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Inventaire → Configuration → Catégories de produits → Matériel`

Passe la Valorisation de l'inventaire sur Automatisée (la méthode de coût reste Coût moyen AVCO). Enregistre.

### Étape 2

`Contacts → Nouveau`

Crée le fournisseur (société), avec Conditions de paiement fournisseur = 30 jours.

| Champ | Valeur |
| --- | --- |
| Nom | Vidéonet Distribution SAS |
| Adresse | 22 rue du Progrès, 69100 Villeurbanne |
| Conditions de paiement | 30 jours |

### Étape 3

`Achats → Commandes → Demandes de prix → Nouveau`

Commande n° 1, datée du 05/10/2026, fournisseur Vidéonet Distribution SAS. Clique sur Confirmer la commande.

| Produit | Quantité | Prix unitaire HT | Total HT |
| --- | --- | --- | --- |
| CAM-IP4K | 20 | 142,00 | 2 840,00 |
| SW-24P | 5 | 386,00 | 1 930,00 |
| NVR-16 | 4 | 540,00 | 2 160,00 |

### Étape 4

`Achats → (commande n° 1) → Réception → Valider`

Valide la réception complète. Le stock passe à 20 caméras, 5 switchs et 4 enregistreurs.

### Étape 5

`Achats → (commande n° 1) → Créer une facture`

Date de facturation : 05/10/2026. Vérifie le total (6 930,00 € HT), puis Confirmer.

### Étape 6

`Achats → Commandes → Demandes de prix → Nouveau`

Commande n° 2, datée du 19/10/2026. Le fournisseur a augmenté le prix des caméras. Confirme, valide la réception, puis crée et confirme la facture au 19/10/2026.

| Produit | Quantité | Prix unitaire HT | Total HT |
| --- | --- | --- | --- |
| CAM-IP4K | 30 | 150,00 | 4 500,00 |
| AP-WF6 | 10 | 118,00 | 1 180,00 |

### Étape 7

`Ventes → Produits → Produits → CAM-IP4K`

Regarde le champ Coût : Odoo l'a recalculé au coût moyen pondéré.

### Étape 8

`Inventaire → Rapports → Valorisation du stock`

Lis la valeur du stock par produit, puis exporte la vue en XLSX (⚙ Actions → Exporter, ou bouton de téléchargement).

### Étape 9

`Excel → nouvel onglet Stock`

Recalcule à la main le CUMP de la caméra avec la formule de la théorie. Calcule l'écart de prix d'achat, puis le nouveau taux de marque de la caméra au prix de vente inchangé de 229 €.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] La réception de la commande n° 2 est au statut Fait.
- [ ] Les deux factures fournisseurs sont confirmées (6 930,00 € et 5 680,00 € HT).

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Coût moyen pondéré de la caméra CAM-IP4K | € | (20 × 142 + 30 × 150) ÷ 50 |
| Valeur totale du stock après les deux réceptions | € | Somme des quantités × coût moyen |
| Nouveau taux de marque de la caméra | % | (229 − CUMP) ÷ 229 |

---

[← Programme](../README.md#programme)
