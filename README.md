# Altiplan Systèmes · Parcours contrôle de gestion sur Odoo et Excel

Un parcours pratique en **12 missions** pour apprendre le métier de contrôleur de gestion sur un vrai ERP. Le fil rouge est une entreprise fictive, **Altiplan Systèmes SAS**, dont les chiffres s'enchaînent d'une mission à l'autre : le coût d'achat calculé à la Mission 2 se retrouve dans la marge de la Mission 3, puis dans le tableau de bord de la Mission 11.

🌐 **Site de l'entreprise :** [shtwessie.odoo.com](https://shtwessie.odoo.com/) · 🎓 **Cours en ligne (Odoo eLearning) :** [shtwessie.odoo.com/slides/1](https://shtwessie.odoo.com/slides/1)

> Altiplan Systèmes est une entreprise fictive. Les clients, fournisseurs, numéros SIRET et montants sont des données d'exercice.

---

## Le cas d'étude

Altiplan Systèmes est un intégrateur B2B de sécurité et de réseaux basé à Lyon : 12 salariés et environ 1,8 M€ de chiffre d'affaires. L'entreprise vend du matériel, l'installe, puis le maintient sous contrat. Trois modèles économiques dans une même société, c'est ce qui en fait un bon terrain pour le contrôle de gestion.

| Pôle | Activité | Modèle économique | Taux de marque cible |
| --- | --- | --- | --- |
| **MAT** | Caméras IP, switchs PoE, bornes Wi-Fi, enregistreurs | Achat-revente avec stock (coût moyen pondéré) | 25 à 35 % |
| **INST** | Déploiements clé en main | Forfait facturé par jalons, ou régie | 40 % |
| **MAINT** | Contrats de support | Revenu récurrent mensuel | 60 % |
| **STRUCT** | Loyer, expert-comptable, assurances | Centre de coût, à répartir | — |

## Programme

Chaque mission suit la même structure : **1.** l'objectif financier, **2.** la théorie, **3.** l'exercice pratique Odoo + Excel avec des données chiffrées, **4.** la validation par un KPI à retrouver.

| # | Mission | Durée |
| --- | --- | --- |
| 0 | [Démarrage de l'espace Odoo](missions/00-demarrage-de-l-espace-odoo.md) | 45 min |
| 1 | [Structure analytique et catalogue](missions/01-structure-analytique-et-catalogue.md) | 1 h 30 |
| 2 | [Achats de matériel et valorisation du stock](missions/02-achats-de-materiel-et-valorisation-du-stock.md) | 1 h 30 |
| 3 | [Vente de matériel : marge réelle par facture](missions/03-vente-de-materiel-marge-reelle-par-facture.md) | 1 h |
| 4 | [Facturation électronique (Factur-X)](missions/04-facturation-electronique-factur-x.md) | 1 h 15 |
| 5 | [Projet d'installation : temps passés et facturation à l'avancement](missions/05-projet-d-installation-temps-passes-et-facturation-a-l-avancement.md) | 2 h |
| 6 | [Contrats de maintenance : récurrent et produits constatés d'avance](missions/06-contrats-de-maintenance-recurrent-et-produits-constates-d-avance.md) | 1 h 15 |
| 7 | [Frais de structure et clés de répartition](missions/07-frais-de-structure-et-cles-de-repartition.md) | 1 h 30 |
| 8 | [Export Odoo vers Excel : TCD de rentabilité par pôle et client](missions/08-export-odoo-vers-excel-tcd-de-rentabilite-par-pole-et-client.md) | 1 h 30 |
| 9 | [Budget et analyse des écarts](missions/09-budget-et-analyse-des-ecarts.md) | 1 h 30 |
| 10 | [Suivi de facturation, relances et DSO](missions/10-suivi-de-facturation-relances-et-dso.md) | 2 h |
| 11 | [Tableau de bord mensuel du DAF](missions/11-tableau-de-bord-mensuel-du-daf.md) | 2 h |

Environ **17 heures** de pratique au total.

## Compétences travaillées

- **Comptabilité analytique :** plans et comptes analytiques, modèles de distribution, centres de profit et de coût
- **Coûts et marges :** coût de revient d'un bien et d'un service, coût moyen pondéré (AVCO), taux de marque, taux de marge, coefficient
- **Revenus :** facturation par jalons, avancement par les coûts, factures à établir (FAE), produits constatés d'avance (PCA), revenu récurrent (MRR)
- **Facturation électronique :** format Factur-X (PDF/A-3 + XML CII), réforme française 2026-2027, contrôle de cohérence
- **Pilotage :** clés de répartition, budget, écarts sur volume et sur taux, seuil de rentabilité, point mort
- **Trésorerie :** balance âgée, niveaux de relance, DSO global et par client, BFR
- **Excel :** tableaux croisés dynamiques, champs calculés, SOMME.SI.ENS, RECHERCHEX, Power Query, graphiques en cascade, mise en forme conditionnelle

## Outils

`Odoo 20` (Comptabilité, Ventes, Achats, Inventaire, Projet, Feuilles de temps, eLearning, Site Web) · `Excel` · `Power Query`

## Contenu du dépôt

```text
missions/   Les 12 missions en Markdown, lisibles directement sur GitHub
README.md   Cette présentation
```

Les résultats attendus (KPI) ne sont pas publiés dans les missions : chaque mission donne l'indicateur à trouver et un indice de calcul.

## Auteur

Conçu par **[Shtwessie D.](https://github.com/Shtwessie)**, gestionnaire (facturation, RH et automatisation) en évolution vers le contrôle de gestion et la gestion de projet. Portfolio : [shtwessie.github.io/kim-os](https://shtwessie.github.io/kim-os/)

**Conçu avec Claude (Anthropic).** Le cas d'étude, les missions, les jeux de données chiffrés, le site et le cours Odoo ont été réalisés avec l'aide de Claude. Tous les KPI de validation ont été recalculés et vérifiés.

## Licence

Contenu pédagogique sous licence [Creative Commons BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.fr) : réutilisation libre, y compris commerciale, en citant l'auteur.
