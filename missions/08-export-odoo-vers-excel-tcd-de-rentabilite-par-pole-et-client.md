# Mission 8 · Export Odoo vers Excel : TCD de rentabilité par pôle et client

**Durée :** 1 h 30 · **Prérequis :** Mission 7 validée

## 1. L'objectif financier

Transformer les écritures de vente d'Odoo en tableau de rentabilité exploitable : chiffre d'affaires et marge par pôle et par client. C'est l'export le plus demandé à un contrôleur de gestion, et il doit être refait chaque mois sans erreur.

## 2. La théorie du contrôle de gestion

### Choisir la bonne source

On exporte les lignes d'écritures (et non les factures) pour avoir une ligne par produit, avec son compte et sa distribution analytique. On filtre sur le journal des ventes pour exclure les autres flux.

### Les données propres

Un TCD fiable repose sur un tableau plat : une ligne par enregistrement, une colonne par attribut, aucun total intermédiaire, aucune cellule fusionnée. Mets les données sous forme de tableau Excel (Ctrl + L) pour que le TCD suive les ajouts.

### Rentabilité par client

Un client au gros chiffre d'affaires n'est pas forcément le plus rentable. Le taux de marque par client révèle ceux qui négocient trop ou consomment trop d'heures.

```text
Taux de marque client = (CA − coûts directs du client) ÷ CA
```

### Rapprocher les sources

Le total du TCD doit égaler le chiffre d'affaires du compte de résultat sur la même période. Un écart signale un filtre oublié ou un doublon.

## 3. L'exercice pratique Odoo + Excel

### Étape 1

`Comptabilité → Comptabilité → Écritures comptables → Lignes d'écritures`

Filtre : Journal = Factures clients (le journal de ventes standard, pas Ventes exercice DSO), comptes de classe 7, période du 01/10/2026 au 31/12/2026.

### Étape 2

`Lignes d'écritures → tout sélectionner → ⚙ Actions → Exporter`

Exporte en XLSX : Date, Partenaire, Produit, Libellé, Compte, Distribution analytique, Crédit, Débit.

### Étape 3

`Excel → nouvel onglet Données_ventes`

Mets les données sous forme de tableau. Ajoute une colonne Montant = Crédit − Débit et une colonne Pôle (MAT, INST ou MAINT, déduite de la distribution analytique).

### Étape 4

`Excel → nouvel onglet Coûts`

Saisis les coûts directs des ventes du trimestre, calculés dans les missions précédentes.

| Client | MAT | INST | MAINT |
| --- | --- | --- | --- |
| Entrepôts Gerland Logistique SAS | 3 309,60 | 0,00 | 1 140,00 |
| Logistique Rhône Express SARL | 1 806,80 | 456,00 | 1 140,00 |
| Résidences Seniors Confluence SAS | 3 660,80 | 6 066,00 | 540,00 |

### Étape 5

`Excel → Insertion → Tableau croisé dynamique`

Clients en lignes, Pôles en colonnes, Somme de Montant en valeurs. Vérifie le total général.

### Étape 6

`Excel → onglet Rentabilité`

À côté du TCD, ramène les coûts avec SOMME.SI.ENS ou RECHERCHEX, puis calcule la marge et le taux de marque par pôle et par client. Classe les clients par taux de marque décroissant.

## 4. La validation

**À vérifier dans :** Odoo + Excel

- [ ] Le total du TCD égale le CA HT du trimestre dans Comptabilité → Rapports → Compte de résultat (hors journal DSO).
- [ ] Aucune ligne du journal Ventes exercice DSO n'apparaît dans l'export.

| Résultat à trouver | Unité | Indice |
| --- | --- | --- |
| CA du pôle MAT au T4 | € | Missions 3, 4 et 5 |
| Taux de marque global | % | Σ marges ÷ Σ CA |
| Taux de marque de Logistique Rhône Express | % | Le client le plus rentable en taux |
| Marge de Résidences Seniors Confluence | € | Le client le plus rentable en valeur |

---

[← Programme](../README.md#programme)
