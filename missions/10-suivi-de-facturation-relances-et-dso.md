# Mission 10 · Suivi de facturation, relances et DSO

**Durée :** 2 h · **Prérequis :** Mission 9 validée

## 1. L'objectif financier

Mesurer et piloter le risque client. Tu vas paramétrer les relances, lire une balance âgée, puis calculer dans Excel le DSO global et par client. Chaque jour de DSO en moins libère de la trésorerie et réduit le besoin en fonds de roulement.

## 2. La théorie du contrôle de gestion

### BFR et DSO

Le BFR d'exploitation mesure l'argent immobilisé par le cycle d'activité. Le DSO (Days Sales Outstanding) exprime les créances clients en jours de chiffre d'affaires. Pour Altiplan, un jour de DSO vaut environ 5 918 € de trésorerie.

```text
BFR = Stocks + Créances clients − Dettes fournisseurs
DSO = Créances clients TTC ÷ CA TTC de la période × nb de jours
1 jour de DSO = 1 800 000 × 1,20 ÷ 365 ≈ 5 918 €
```

### La balance âgée

Elle classe les créances par ancienneté de retard : non échu, 1–30 jours, 31–60, 61–90, 91–120, plus ancien. C'est l'outil de priorisation du recouvrement : une créance de plus de 90 jours a une probabilité d'encaissement nettement plus faible.

### Les limites du DSO simple

Le DSO simple est sensible à la saisonnalité et aux créances anciennes hors période. La méthode par épuisement (on retire les CA mensuels les plus récents jusqu'à épuiser les créances) est plus précise. Ici, une facture de juin gonfle le DSO d'un client.

### Le cadre légal français

Délai de paiement maximal entre professionnels : 60 jours date de facture, ou 45 jours fin de mois. Tout retard entraîne des pénalités et une indemnité forfaitaire de recouvrement de 40 €, à mentionner sur la facture.

### Les niveaux de relance

Une relance progressive, déclenchée par le nombre de jours après l'échéance, standardise le recouvrement : rappel courtois, relance ferme, mise en demeure, puis contentieux.

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Comptabilité → Configuration → Journaux → Nouveau`

Crée un journal dédié à cet exercice. Il isole ces factures de celles des autres missions et facilite les filtres.

| Champ | Valeur |
| --- | --- |
| Nom du journal | Ventes exercice DSO |
| Type | Ventes |
| Code court | DSO |

### Étape 2

`Comptabilité → Configuration → Relances de paiement`

Remplace les niveaux existants par ces trois niveaux (le menu peut s'appeler Niveaux de relance).

| Nom | Délai après échéance | Actions |
| --- | --- | --- |
| Rappel amical | 15 jours | E-mail |
| Relance ferme | 30 jours | E-mail + courrier |
| Mise en demeure | 60 jours | E-mail + courrier + activité Appel |

### Étape 3

`Contacts → Nouveau`

Crée les 3 clients (sociétés), avec Conditions de paiement = 30 jours.

| Client | Ville |
| --- | --- |
| Transports Saône Vallée SARL | Villefranche-sur-Saône |
| Imprimerie Bellecour SAS | Lyon 2e |
| Cabinet Médical Saint-Clair | Caluire-et-Cuire |

### Étape 4

`Comptabilité → Clients → Factures → Nouveau`

Saisis les 9 factures dans l'ordre des dates. Pour chacune : Journal = Ventes exercice DSO, une ligne sans produit (libellé « Prestations Altiplan »), prix = montant HT, TVA 20 %, Conditions = 30 jours. Confirme chaque facture.

| N° | Client | Date | HT | TTC | Échéance |
| --- | --- | --- | --- | --- | --- |
| 1 | Cabinet Médical Saint-Clair | 15/06/2026 | 2 500,00 | 3 000,00 | 15/07/2026 |
| 2 | Transports Saône Vallée SARL | 03/07/2026 | 4 000,00 | 4 800,00 | 02/08/2026 |
| 3 | Imprimerie Bellecour SAS | 10/07/2026 | 1 500,00 | 1 800,00 | 09/08/2026 |
| 4 | Transports Saône Vallée SARL | 22/07/2026 | 6 000,00 | 7 200,00 | 21/08/2026 |
| 5 | Cabinet Médical Saint-Clair | 05/08/2026 | 800,00 | 960,00 | 04/09/2026 |
| 6 | Imprimerie Bellecour SAS | 18/08/2026 | 3 200,00 | 3 840,00 | 17/09/2026 |
| 7 | Transports Saône Vallée SARL | 02/09/2026 | 5 000,00 | 6 000,00 | 02/10/2026 |
| 8 | Cabinet Médical Saint-Clair | 16/09/2026 | 1 200,00 | 1 440,00 | 16/10/2026 |
| 9 | Imprimerie Bellecour SAS | 25/09/2026 | 2 000,00 | 2 400,00 | 25/10/2026 |

### Étape 5

`Comptabilité → Clients → Factures → (facture) → Enregistrer un paiement`

Enregistre les 3 encaissements. Pour le paiement partiel, choisis « Garder ouvert » afin que la facture reste due pour le solde.

| Facture | Date du paiement | Montant | Type |
| --- | --- | --- | --- |
| N° 2 (Transports Saône Vallée) | 01/08/2026 | 4 800,00 | Total |
| N° 4 (Transports Saône Vallée) | 25/08/2026 | 3 600,00 | Partiel, garder ouvert |
| N° 5 (Cabinet Médical Saint-Clair) | 04/09/2026 | 960,00 | Total |

### Étape 6

`Comptabilité → Rapports → Balance âgée des clients`

Règle la date sur Au 30/09/2026 et filtre sur les 3 clients de l'exercice. Lis le total de chaque tranche d'ancienneté.

### Étape 7

`Comptabilité → Clients → Relances de paiement`

Ouvre le rapport de relance du Cabinet Médical Saint-Clair. Vérifie le niveau proposé et lis la lettre générée, sans l'envoyer.

### Étape 8

`Comptabilité → Clients → Factures → vue Liste → filtre Journal = Ventes exercice DSO → tout sélectionner → ⚙ Actions → Exporter`

Exporte en XLSX : Numéro, Client, Date de facturation, Date d'échéance, Total signé (TTC), Montant dû signé.

### Étape 9

`Excel → fichier exporté`

Calcule le DSO sur le 3e trimestre 2026 (92 jours). Numérateur : les créances au 30/09, soit tous les montants dus. Dénominateur : le CA TTC facturé entre le 01/07 et le 30/09.

| Indicateur | Formule Excel (à adapter à tes colonnes) |
| --- | --- |
| CA TTC T3 | =SOMME.SI.ENS(E:E;C:C;">="&DATE(2026;7;1);C:C;"<="&DATE(2026;9;30)) |
| Créances au 30/09 | =SOMME(F:F) |
| DSO global | =Créances ÷ CA TTC T3 × 92 |
| DSO par client | Mêmes formules avec un critère B:B = nom du client |

### Étape 10

`Excel → Insertion → Tableau croisé dynamique`

Construis un TCD avec les clients en lignes, puis la somme du Total TTC et la somme du Montant dû. Ajoute une colonne DSO à côté. Explique en une phrase dans tes notes pourquoi le DSO du Cabinet Médical est trompeur.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] Le Cabinet Médical Saint-Clair est au niveau Mise en demeure dans les relances.
- [ ] La facture n° 4 affiche un montant dû de 3 600,00 €.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Total de la balance âgée au 30/09/2026 | € | Somme de toutes les tranches |
| Tranche 31–60 jours | € | Deux factures en retard de 40 et 52 jours |
| DSO global du trimestre | j | Créances ÷ CA TTC T3 × 92 |
| DSO de Transports Saône Vallée | j | Même formule, filtrée sur le client |

---

[← Programme](../README.md#programme)
