# Mission 4 · Facturation électronique (Factur-X)

**Durée :** 1 h 15 · **Prérequis :** Mission 3 validée

## 1. L'objectif financier

Émettre une facture client conforme à la réforme française de la facturation électronique B2B, au format Factur-X, puis vérifier le fichier produit. Une facture structurée se traite sans ressaisie chez le client : elle est payée plus vite et fiabilise les données du contrôle de gestion.

## 2. La théorie du contrôle de gestion

### La réforme B2B en France

Depuis le 1er septembre 2026, toute entreprise assujettie à la TVA doit pouvoir recevoir des factures électroniques, et les grandes entreprises et ETI doivent aussi en émettre. Les PME comme Altiplan émettront au plus tard le 1er septembre 2027. Les factures passent par une plateforme agréée (PA, anciennement PDP). Un simple PDF envoyé par e-mail n'est pas une facture électronique.

### Le format Factur-X

Format hybride franco-allemand (équivalent de ZUGFeRD 2). C'est un PDF/A-3 lisible par un humain, dans lequel est embarqué un fichier factur-x.xml au standard CII (Cross Industry Invoice), lisible par une machine. Profils : MINIMUM, BASIC WL, BASIC, EN 16931, EXTENDED. La réforme exige au moins les données de la norme EN 16931.

### Les nouvelles mentions obligatoires

SIREN du client, adresse de livraison si elle diffère, nature de l'opération (livraison de biens, prestation de services ou mixte) et, le cas échéant, option pour la TVA d'après les débits. Une facture Altiplan qui mêle matériel et heures d'installation est une opération mixte.

### L'intérêt pour le contrôleur de gestion

Des données structurées permettent le rapprochement automatique chez le client, réduisent les litiges et donc le DSO. L'e-reporting transmet aussi les données de transaction à l'administration : une erreur de facturation devient visible.

### Le contrôle de cohérence d'un fichier Factur-X

Les totaux de l'en-tête XML doivent correspondre à la somme des lignes.

```text
Σ lignes HT = TaxBasisTotalAmount
TaxBasisTotalAmount × 20 % = TaxTotalAmount
TaxBasisTotalAmount + TaxTotalAmount = GrandTotalAmount
```

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Paramètres → Sociétés → Mettre à jour les infos`

Complète l'identité fiscale d'Altiplan (données fictives mais valides au contrôle de clé).

| Champ | Valeur |
| --- | --- |
| SIRET | 98765432400019 |
| N° TVA | FR14987654324 |
| Adresse | 14 rue des Artisans, 69007 Lyon |

### Étape 2

`Contacts → Nouveau`

Coche Société, puis crée le client. Dans l'onglet Ventes et achats, règle Conditions de paiement = 30 jours. Dans l'onglet Comptabilité (ou Facturation), règle le format de facture électronique sur Factur-X (CII).

| Champ | Valeur |
| --- | --- |
| Nom | Logistique Rhône Express SARL |
| Adresse | 8 quai Perrache, 69002 Lyon, France |
| SIRET | 12345678200010 |
| N° TVA | FR11123456782 |
| E-mail | compta@rhone-express.example |
| Conditions de paiement | 30 jours |
| Format de facture électronique | Factur-X (CII) |

### Étape 3

`Comptabilité → Clients → Factures → Nouveau`

Client : Logistique Rhône Express SARL. Date de facturation : 30/10/2026. Conditions : 30 jours. Ajoute les 4 lignes (TVA 20 % sur chaque ligne).

| Produit | Quantité | Prix unitaire HT | Sous-total HT |
| --- | --- | --- | --- |
| CAM-IP4K Caméra IP 4K extérieure | 6 | 229,00 | 1 374,00 |
| SW-24P Switch PoE 24 ports | 1 | 590,00 | 590,00 |
| NVR-16 Enregistreur NVR 16 voies | 1 | 820,00 | 820,00 |
| SRV-INST Heure d'installation technicien | 12 | 75,00 | 900,00 |

### Étape 4

`Comptabilité → Clients → Factures → (ta facture) → Confirmer`

Vérifie le total avant de confirmer : 3 684,00 € HT, 736,80 € de TVA, 4 420,80 € TTC.

### Étape 5

`Comptabilité → Clients → Factures → (ta facture) → Envoyer`

Dans la fenêtre d'envoi, vérifie que le format Factur-X est coché. Décoche l'e-mail et choisis Télécharger. Odoo embarque automatiquement le fichier factur-x.xml dans le PDF.

### Étape 6

`Adobe Acrobat Reader → Pièces jointes (icône trombone)`

Ouvre le PDF dans Acrobat Reader (un navigateur n'affiche pas les pièces jointes). Le panneau Pièces jointes doit contenir factur-x.xml. Enregistre-le.

### Étape 7

`Navigateur → validateur Factur-X en ligne`

Dépose le PDF dans un validateur Factur-X, par exemple celui du FNFE-MPE (services.fnfe-mpe.org). Note le profil détecté et les éventuelles erreurs. Les données sont fictives.

### Étape 8

`Excel → Données → Obtenir des données → À partir d'un fichier → À partir de XML`

Ouvre factur-x.xml. Dans Power Query, développe IncludedSupplyChainTradeLineItem pour obtenir une ligne par article. Recalcule la somme des lignes HT et compare-la aux totaux de l'en-tête.

### Étape 9

`Excel → nouvelle colonne Coût`

Ajoute le coût unitaire actuel de chaque produit : 146,80 € pour la caméra (coût moyen depuis la Mission 2), 386 € pour le switch, 540 € pour l'enregistreur, 38 € pour l'heure. Calcule le coût total, la marge et le taux de marque de la facture.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] Le PDF téléchargé contient la pièce jointe factur-x.xml.
- [ ] Le validateur reconnaît un fichier Factur-X sans erreur bloquante.
- [ ] Le SIREN du client (123456782) figure dans le XML.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| GrandTotalAmount lu dans le XML | € | Total TTC de l'en-tête |
| TaxTotalAmount lu dans le XML | € | Total TVA de l'en-tête |
| Taux de marque de la facture | % | (HT − coût total) ÷ HT |

---

[← Programme](../README.md#programme)
