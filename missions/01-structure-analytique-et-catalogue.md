# Mission 1 · Structure analytique et catalogue

## 1. L'objectif financier

Construire l'axe d'analyse qui servira à tout le parcours (les pôles MAT, INST, MAINT et STRUCT), puis créer un catalogue avec des coûts de revient justes. Tu termineras par un premier export Excel pour mesurer la marge théorique du catalogue.

## 2. La théorie du contrôle de gestion

### Comptabilité générale ou analytique

La générale classe les charges par nature (comptes 6 et 7) pour l'État et les tiers. L'analytique les classe par destination (pôle, projet, client) pour décider. Dans Odoo, une même ligne de facture porte un compte général et une distribution analytique en pourcentage.

### Plan et compte analytique

Un plan analytique est un axe d'analyse (ici « Pôles d'activité »). Chaque compte analytique en est une valeur (MAT, INST…). On pourra ajouter plus tard un second axe (Projet, Client) sans toucher au premier.

### Centre de profit ou centre de coût

MAT, INST et MAINT portent du chiffre d'affaires et des coûts : ce sont des centres de profit. STRUCT ne porte que des charges (loyer, administratif) qu'il faudra répartir sur les trois autres.

### Coût de revient d'un service

Pour une heure de technicien, le coût n'est pas le salaire horaire mais le coût chargé divisé par les heures réellement facturables.

```text
2 450 € brut × 1,45 = 3 552,50 € / mois
3 552,50 € ÷ 93,5 h facturables = 37,99 € / h, arrondi à 38 €
(93,5 h sur 151,67 h payées = 61,6 % d'occupation)
```

### Taux de marque ou taux de marge

Deux ratios souvent confondus. Et un piège : le taux global se calcule sur les totaux, jamais en faisant la moyenne des taux.

```text
Taux de marque = (PV − Coût) ÷ PV
Taux de marge  = (PV − Coût) ÷ Coût
```

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Comptabilité → Configuration → Paramètres → Analytique`

Coche « Comptabilité analytique » puis Enregistrer. Les menus analytiques apparaissent dans Configuration.

### Étape 2

`Comptabilité → Configuration → Plans analytiques → Nouveau`

Nom : Pôles d'activité  
Applicabilité par défaut : Optionnel  
Enregistre.

### Étape 3

`Comptabilité → Configuration → Comptes analytiques → Nouveau`

Crée les 4 comptes, tous rattachés au plan « Pôles d'activité ».

| Nom | Référence | Plan |
| --- | --- | --- |
| Matériel | MAT | Pôles d'activité |
| Installation | INST | Pôles d'activité |
| Maintenance | MAINT | Pôles d'activité |
| Frais de structure | STRUCT | Pôles d'activité |

### Étape 4

`Inventaire → Configuration → Catégories de produits → Nouveau`

Crée 3 catégories (catégorie parente : All). Pour Matériel, règle Méthode de coût = Coût moyen (AVCO) et Valorisation de l'inventaire = Manuelle ; on passera en automatisée à la mission 2.

| Catégorie | Méthode de coût |
| --- | --- |
| Matériel | Coût moyen (AVCO) |
| Installation | Prix standard |
| Maintenance | Prix standard |

### Étape 5

`Comptabilité → Configuration → Modèles de distribution analytique → Nouveau`

Un modèle par catégorie : dès qu'un produit de la catégorie est vendu ou acheté, sa ligne est imputée automatiquement au bon pôle. Si le menu est absent, active le mode développeur (Paramètres → tout en bas → Activer le mode développeur).

| Catégorie de produit | Distribution analytique |
| --- | --- |
| Matériel | MAT 100 % |
| Installation | INST 100 % |
| Maintenance | MAINT 100 % |

### Étape 6

`Inventaire → Configuration → Paramètres → Produits`

Coche « Unités de mesure » puis Enregistrer, pour pouvoir vendre à l'heure et au jour.

### Étape 7

`Ventes → Produits → Produits → Nouveau`

Crée les 8 produits. Matériel : Type = Biens, coche « Suivre l'inventaire ». Autres : Type = Service. Taxe à la vente : 20 %. Le champ Coût se trouve sous le prix de vente.

| Référence interne | Nom | Catégorie | Type | Unité | Prix de vente HT | Coût |
| --- | --- | --- | --- | --- | --- | --- |
| CAM-IP4K | Caméra IP 4K extérieure | Matériel | Biens | Unités | 229,00 | 142,00 |
| SW-24P | Switch PoE 24 ports | Matériel | Biens | Unités | 590,00 | 386,00 |
| AP-WF6 | Borne Wi-Fi 6 pro | Matériel | Biens | Unités | 185,00 | 118,00 |
| NVR-16 | Enregistreur NVR 16 voies | Matériel | Biens | Unités | 820,00 | 540,00 |
| SRV-INST | Heure d'installation technicien | Installation | Service | Heures | 75,00 | 38,00 |
| SRV-CP | Journée chef de projet | Installation | Service | Jours | 750,00 | 420,00 |
| MAINT-ESS | Contrat maintenance Essentiel (mois) | Maintenance | Service | Unités | 120,00 | 45,00 |
| MAINT-PRE | Contrat maintenance Premium (mois) | Maintenance | Service | Unités | 240,00 | 95,00 |

### Étape 8

`Ventes → Produits → Produits → vue Liste → case d'en-tête → ⚙ Actions → Exporter`

Passe en vue liste, sélectionne les 8 produits, puis exporte au format XLSX les champs : Référence interne, Nom, Catégorie de produit, Prix de vente, Coût.

### Étape 9

`Excel → fichier exporté`

Ajoute trois colonnes : Marge unitaire (= PV − Coût), Taux de marque (= Marge ÷ PV) et Taux de marge (= Marge ÷ Coût). Ajoute une ligne Total avec SOMME sur PV, Coût et Marge, puis calcule les taux globaux à partir de ces totaux. Fais un TCD par catégorie (Somme de PV, Somme de Coût) pour obtenir le taux de marque du pôle Matériel.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] La fiche CAM-IP4K affiche un coût de 142,00 € et la catégorie Matériel.
- [ ] Le modèle de distribution de la catégorie Matériel impute 100 % sur MAT.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| Taux de marque global du catalogue | % | Σ(PV − Coût) ÷ ΣPV |
| Taux de marge global du catalogue | % | Σ(PV − Coût) ÷ ΣCoût |
| Taux de marque du pôle Matériel | % | Depuis le TCD par catégorie |

---

[← Programme](../README.md#programme)
