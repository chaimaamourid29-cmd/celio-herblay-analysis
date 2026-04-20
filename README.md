# Célio Herblay — Customer Loyalty Analysis 2025

> 🇬🇧 [English version](#english-version) | 🇫🇷 [Version française](#version-française)

---

<a name="english-version"></a>
# 🇬🇧 English Version

**Author:** Chaimaa MOURID  
**Realisation:** 2026 | **Study case:** 2025  
**Tools:** MySQL · Power BI · GitHub

---

## Context

I work as a seller at Célio Herblay (Val d'Oise, France).  
From my daily experience at the cashier, I identified two recurring operational problems that cause silent revenue loss for the store:

1. **Expired coupons** — Customers accumulate €5 coupons through the loyalty program (€1 spent = 1 point, 150 points = €5 coupon). The coupon is visible on the cashier screen and is always applied when the customer visits. However, if the customer does not visit the store within the 2-month validity window, the coupon expires — and that visit never happens.

2. **Missed birthday discounts** — Every customer is entitled to a 20% discount on their most expensive item during their birthday month. Unlike coupons, this discount is **not visible on the main cashier screen** — it requires the seller to manually check the customer profile. Similarly, the customer's **points balance is not visible on the cashier screen either**, which means sellers cannot proactively inform customers how close they are to their next coupon. As a result, both the birthday discount and the points progress go unnoticed most of the time.

This project quantifies the revenue impact of both problems using SQL analysis and Power BI visualization.

---

## Dataset

Simulated dataset based on realistic Célio pricing and customer behavior (Val d'Oise region).

| Table | Rows | Description |
|-------|------|-------------|
| customers | 100 | Loyalty card holders with points and coupon history |
| transactions | 593 | All purchases in 2025 with discount details |
| coupons | 267 | All coupons generated, used, expired or active |

**Realistic parameters:**
- Average annual spend per customer: €470
- Average basket per visit: €77.93
- Visits per year: 4 to 6
- Prices based on real Célio catalogue

---

## Key Findings

| Metric | Value |
|--------|-------|
| Total Revenue 2025 | €46,212 |
| Expired Coupons | 82 |
| Estimated Revenue Lost (Coupons) | €5,765 |
| Birthday Eligible Visits | 131 |
| Birthday Discounts Missed | 104 (79%) |
| Estimated Revenue Lost (Birthday) | €961 |
| **Total Estimated Loss** | **€6,726** |

---

## SQL Analysis

8 queries covering:
- Database overview
- Revenue overview (before and after discounts)
- Expired coupon analysis
- Estimated real revenue loss from expired coupons
- Birthday discount miss rate
- Coupon status breakdown
- Priority contact list (active coupons expiring soon)
- Customer segmentation (Active / At Risk / Sleeping)

→ See [`celio_analysis.sql`](celio_analysis.sql)

---

## Power BI Dashboard

The dashboard includes:
- 5 KPI cards (Total Revenue, Expired Coupons, Coupon Loss, Birthday Loss, Total Loss)
- Monthly Revenue trend (line chart)
- Coupon Status Breakdown (donut chart)
- Birthday Discount Performance (bar chart)
- Revenue by City (bar chart)
- Priority Contact List — customers with active coupons expiring soon (table)

---

## Business Recommendations

1. **Activate double opt-in at the cashier screen** — When registering a new customer to the loyalty program, systematically collect both SMS and email consent directly at the register. A larger reachable base means every following action (reminders, birthday alerts) reaches more customers and has a greater impact on store visits.

2. **Automated reminder in the last week before expiry** — Send an automated SMS or email during the last 7 days of the coupon validity window. The message should feel personal and casual, in the tone of the Be+ program — for example: *"Oops, vous avez oublié quelque chose dans votre Be+ ! Votre bon d'achat de 5€ expire dans X jours. Profitez-en vite 🛍️"*. SMS has a significantly higher open rate than email, but having both channels activated maximizes the reach.

3. **Add birthday discount and points balance to the main cashier screen** — Both the birthday discount and the customer's points progress are currently hidden and require the seller to manually check the customer profile. Displaying them directly on the cashier screen — the same way coupons are shown — would ensure sellers never miss them, without any extra effort or training required.

4. **Verbal reminder at the register** — Encourage sellers to mention expiring coupons and points progress during checkout. A simple *"You have a €5 coupon expiring in X days"* or *"You only need X more points for your next coupon"* is enough to motivate a return visit.

5. **Monthly action list** — Generate a monthly list of customers with active coupons expiring soon and contact them proactively via SMS or email to drive store visits before expiry.

---

## Disclaimer

> The goal of this project is to learn and practice SQL analysis and Power BI. The dataset is entirely simulated — names, transactions, and figures are fictional and do not represent real Célio Herblay customers or actual store performance. It was generated to reflect realistic behavior based on real Célio pricing and French customer spending patterns, with the help of Claude AI (Anthropic) and my real experience as a seller.

---

## Files

| File | Description |
|------|-------------|
| `customers.csv` | Customer dataset |
| `transactions.csv` | Transactions dataset |
| `coupons.csv` | Coupons dataset |
| `celio_analysis.sql` | All SQL queries with results |
| `README.md` | This file |

---
---

<a name="version-française"></a>
# 🇫🇷 Version Française

**Auteure :** Chaimaa MOURID  
**Réalisation :** 2026 | **Étude de cas :** 2025  
**Outils :** MySQL · Power BI · GitHub

---

## Contexte

Je travaille en tant que vendeuse au magasin Célio Herblay (Val d'Oise, France).  
De mon expérience quotidienne en caisse, j'ai identifié deux problèmes opérationnels récurrents qui entraînent une perte de chiffre d'affaires silencieuse pour le magasin :

1. **Bons d'achat expirés** — Les clients accumulent des bons d'achat de 5€ grâce au programme de fidélité (1€ dépensé = 1 point, 150 points = 1 bon de 5€). Le bon est visible sur l'écran caisse et est toujours appliqué lorsque le client se présente en magasin. Cependant, si le client ne revient pas pendant la fenêtre de validité de 2 mois, le bon expire — et cette visite n'a jamais lieu.

2. **Remises anniversaire manquées** — Chaque client a droit à une remise de 20% sur l'article le plus cher lors de son mois d'anniversaire. Contrairement aux bons d'achat, cette remise **n'est pas visible sur l'écran principal de caisse** — elle nécessite que le vendeur consulte manuellement le profil client. De même, le **solde de points du client n'est pas affiché à la caisse**, ce qui empêche les vendeurs d'informer proactivement les clients de leur progression vers le prochain bon. Résultat : la remise anniversaire et l'avancement des points passent inaperçus la plupart du temps.

Ce projet quantifie l'impact financier de ces deux problèmes grâce à une analyse SQL et une visualisation Power BI.

---

## Jeu de données

Jeu de données simulé basé sur les prix réels de Célio et le comportement des clients de la région Val d'Oise.

| Table | Lignes | Description |
|-------|--------|-------------|
| customers | 100 | Porteurs de carte fidélité avec historique de points et bons |
| transactions | 593 | Tous les achats de 2025 avec le détail des remises |
| coupons | 267 | Tous les bons générés, utilisés, expirés ou actifs |

**Paramètres réalistes :**
- Dépense annuelle moyenne par client : 470€
- Panier moyen par visite : 77,93€
- Visites par an : 4 à 6
- Prix basés sur le catalogue réel Célio

---

## Résultats Clés

| Indicateur | Valeur |
|------------|--------|
| Chiffre d'affaires 2025 | 46 212€ |
| Bons expirés | 82 |
| Perte estimée (Bons) | 5 765€ |
| Visites éligibles anniversaire | 131 |
| Remises anniversaire manquées | 104 (79%) |
| Perte estimée (Anniversaire) | 961€ |
| **Perte totale estimée** | **6 726€** |

---

## Analyse SQL

8 requêtes couvrant :
- Vue d'ensemble de la base de données
- Vue d'ensemble du chiffre d'affaires (avant et après remises)
- Analyse des bons expirés
- Estimation de la perte réelle liée aux bons expirés
- Taux de remises anniversaire manquées
- Répartition des statuts des bons
- Liste de contact prioritaire (bons actifs expirant bientôt)
- Segmentation client (Actif / À risque / Inactif)

→ Voir [`celio_analysis.sql`](celio_analysis.sql)

---

## Dashboard Power BI

Le dashboard comprend :
- 5 cartes KPI (CA Total, Bons Expirés, Perte Bons, Perte Anniversaire, Perte Totale)
- Évolution du CA mensuel (courbe)
- Répartition des statuts des bons (graphique en anneau)
- Performance des remises anniversaire (graphique en barres)
- CA par ville (graphique en barres)
- Liste de contact prioritaire — clients avec bons actifs expirant bientôt (tableau)

---

## Recommandations

1. **Activer le double opt-in à la caisse** — Lors de l'inscription d'un nouveau client au programme de fidélité, collecter systématiquement le consentement SMS et email directement en caisse. Une base de contacts plus large signifie que chaque action suivante touche davantage de clients et génère plus de visites.

2. **Rappel automatique dans la dernière semaine avant expiration** — Envoyer un SMS ou email automatique durant les 7 derniers jours de validité du bon. Le message doit être personnel et dans le ton du programme Be+, par exemple : *"Oops, vous avez oublié quelque chose dans votre Be+ ! Votre bon d'achat de 5€ expire dans X jours. Profitez-en vite 🛍️"*. Le SMS a un taux d'ouverture nettement supérieur à l'email, mais avoir les deux canaux activés maximise la portée.

3. **Afficher la remise anniversaire et le solde de points sur l'écran caisse** — La remise anniversaire et la progression des points sont actuellement cachées et nécessitent une consultation manuelle du profil client. Les afficher directement sur l'écran caisse — au même titre que les bons d'achat — permettrait aux vendeurs de ne jamais les manquer, sans effort ni formation supplémentaire.

4. **Rappel verbal en caisse** — Encourager les vendeurs à mentionner les bons qui expirent bientôt et la progression des points lors du passage en caisse. Un simple *"Vous avez un bon de 5€ qui expire dans X jours"* ou *"Il ne vous manque plus que X points pour votre prochain bon"* suffit à motiver une prochaine visite.

5. **Liste d'action mensuelle** — Générer chaque mois une liste des clients ayant des bons actifs expirant prochainement et les contacter proactivement par SMS ou email pour générer des visites avant expiration.

---

## Avertissement

> L'objectif de ce projet est d'apprendre et de pratiquer l'analyse SQL et Power BI. Le jeu de données est entièrement simulé — les noms, transactions et chiffres sont fictifs et ne représentent pas les vrais clients de Célio Herblay ni les performances réelles du magasin. Il a été généré pour refléter un comportement réaliste basé sur les prix réels du catalogue Célio et les habitudes de consommation françaises, avec l'aide de Claude AI (Anthropic) et mon expérience réelle en tant que vendeuse.

---

## Fichiers

| Fichier | Description |
|---------|-------------|
| `customers.csv` | Jeu de données clients |
| `transactions.csv` | Jeu de données transactions |
| `coupons.csv` | Jeu de données bons d'achat |
| `celio_analysis.sql` | Toutes les requêtes SQL avec résultats |
| `README.md` | Ce fichier |

