# Mission 0 · Démarrage de l'espace Odoo

## 1. L'objectif financier

Mettre en place un espace Odoo propre et conforme au droit comptable français avant toute saisie. Une localisation fiscale ne se change plus après la première écriture : c'est le premier réflexe d'un contrôleur de gestion qui démarre un ERP.

## 2. La théorie du contrôle de gestion

### ERP et référentiel unique

Odoo relie ventes, achats, stock, projets et comptabilité. Chaque document opérationnel (commande, bon de livraison, feuille de temps) produit ou alimente une écriture comptable. Le contrôleur de gestion exploite cette chaîne au lieu de ressaisir des chiffres.

### Localisation fiscale

Le package France charge le Plan Comptable Général (comptes à 6 chiffres), les taxes TVA et les rapports légaux. Sans elle, les classes 6 et 7 n'existent pas et aucune analyse par nature n'est possible.

### Périmètre applicatif

On n'installe que ce qui produit des données utiles à l'analyse. Chaque application en plus est une source de coûts d'abonnement et de données à contrôler.

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Menu principal → Applications`

Active les six applications ci-dessous (bouton Activer sur chaque carte). Employés, Contacts et Discussion s'installent seules.

| Application | Rôle dans le parcours |
| --- | --- |
| Comptabilité | Écritures, analytique, rapports |
| Ventes | Devis, commandes, facturation à l'avancement |
| Achats | Commandes et factures fournisseurs |
| Inventaire | Stock et valorisation AVCO |
| Projet | Suivi des chantiers d'installation |
| Feuilles de temps | Heures valorisées au coût horaire |

### Étape 2

`Menu principal → Applications → carte Site Web → ⋮ → Désinstaller`

Facultatif. Si tu n'utilises pas le site public, désinstalle Site Web (cela retire aussi eLearning). Sur odoo.com, chaque application en plus compte dans l'abonnement après l'essai de 15 jours.

### Étape 3

`Comptabilité → Configuration → Paramètres → Représentation fiscale`

Package de localisation fiscale : France. Clique sur Enregistrer. À faire avant toute facture.

### Étape 4

`Paramètres → Sociétés → Mettre à jour les infos`

Renseigne l'identité de la société puis enregistre.

| Champ | Valeur |
| --- | --- |
| Nom | Altiplan Systèmes SAS |
| Rue | 14 rue des Artisans |
| Code postal | 69007 |
| Ville | Lyon |
| Pays | France |
| Devise | EUR |

## 4. La validation

**À vérifier dans :** Odoo

- [ ] Les 6 applications apparaissent dans le menu principal.
- [ ] Comptabilité → Configuration → Plan comptable affiche 411100 Clients, 401100 Fournisseurs et 706000 Prestations de services.
- [ ] Comptabilité → Configuration → Taxes contient une taxe de vente à 20 %.
- [ ] Le nom Altiplan Systèmes SAS s'affiche en haut à droite, dans le sélecteur de société.

---

[← Programme](../README.md#programme)
