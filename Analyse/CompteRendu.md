---
title: "Analyse des livraisons — Last-mile Delivery Dataset (Inde)"
author: "Ton Nom"
date: "`r format(Sys.Date(), '%Y-%m-%d')`"
---

# 1. Introduction

Dans ce rapport, nous analysons un jeu de données simulées de **25 000 livraisons** effectuées en Inde, par divers prestataires logistiques, afin d’évaluer la performance opérationnelle, les délais, les coûts, l’impact des conditions (distance, météo, type de colis, véhicule, etc.) et la satisfaction client.

Objectifs :  
- Décrire la structure des données.  
- Identifier les facteurs influençant les retards et les échecs de livraison.  
- Étudier les coûts en fonction des caractéristiques des livraisons.  
- Analyser la qualité du service (via les notes clients).  
- Proposer des recommandations / pistes d’optimisation.

---

# 2. Description du dataset

| Colonne | Description |
|--------|-------------|
| `delivery_id` | Identifiant unique de la livraison |
| `delivery_partner` | Prestataire logistique (Delhivery, Blue Dart, Ekart, DHL, FedEx, Shadowfax, XpressBees, Amazon Logistics, Ecom Express) |
| `package_type` | Type de colis (électronique, nourriture, meubles, objets fragiles, etc.) |
| `vehicle_type` | Véhicule utilisé (bike/moto, van, camion, véhicule électrique, etc.) |
| `delivery_mode` | Mode de livraison (Standard, Express, Same Day, Two Day) |
| `region` | Région de livraison (Nord, Sud, Est, Ouest, Centre) |
| `weather_condition` | Conditions météorologiques (Clair, Pluie, Brouillard, Tempête, Chaleur, Froid) |
| `distance_km` | Distance parcourue (1 à 300 km) |
| `package_weight_kg` | Poids du colis (0.2 à 50 kg) |
| `delivery_time_hours` | Temps réel de livraison |
| `expected_time_hours` | Temps estimé selon le mode de livraison |
| `delayed` | Indicateur de retard (`Yes` / `No`) |
| `delivery_status` | Statut final (Delivered, Delayed, Failed) |
| `delivery_rating` | Note de satisfaction client (1 à 5) |
| `delivery_cost` | Coût de la livraison (en fonction distance, poids, mode) |

Le dataset est propre : aucune valeur manquante, format homogène, valeurs dans des plages réalistes.  

---

# 3. Méthodologie  

## 3.1 Nettoyage / préparation des données  

- Chargement du fichier CSV  
- Vérification des types de variables (catégorielles, numériques)  
- Vérification de la cohérence des valeurs (par exemple : distance non négative, poids > 0, mode de livraison valide, etc.)  
- Conversion / encodage des variables catégorielles si nécessaire  

## 3.2 Analyses exploratoires (statistiques descriptives)

- Distribution des livraisons par prestataire, mode de livraison, type de colis, région, météo.  
- Statistiques de base : moyenne, médiane, écart-type pour des variables comme `distance_km`, `package_weight_kg`, `delivery_time_hours`, `delivery_cost`.  
- Proportions de livraisons retardées ou échouées, taux de réussite, moyenne des notes clients.

## 3.3 Analyses de corrélation / relations  

- Corrélation entre la distance (ou le poids) et le temps de livraison / retard / coût.  
- Impact de la météo sur les délais et les échecs.  
- Comparaison des performances entre prestataires et types de véhicule.  
- Analyse coût vs service (coût moyen par mode / prestataire vs satisfaction client).  

## 3.4 Visualisations  

- Graphiques de distribution (histogrammes, boxplots) pour les variables numériques.  
- Diagrammes en barres / secteurs pour les variables catégorielles (prévalence des modes, prestataires, météo, etc.).  
- Graphiques de type scatter / heatmap pour explorer relations (distance vs coût, délai vs poids, etc.).  

---

# 4. Résultats — Principaux constats (à compléter)  

## 4.1 Statistiques globales  
*(ex. : moyenne distance, poids, coût, taux de retard, taux d’échec)*

- Nombre total de livraisons analysées : 25 000  
- Distribution des livraisons par mode / prestataire / région / météo …  

## 4.2 Facteurs influençant les retards / échecs  

- Impact de la météo (pluie, brouillard, tempête…) sur le taux de retards / échecs  
- Influence de la distance et du poids sur le temps de livraison et les coûts  
- Différences de performance entre prestataires ou types de véhicule  

## 4.3 Analyse des coûts  

- Coût moyen de livraison selon le mode, la distance, le poids, le prestataire  
- Corrélation entre coût et satisfaction client  

## 4.4 Satisfaction client & qualité de service  

- Distribution des notes (1–5)  
- Relation entre retard / échec et note client  
- Prestataires / modes de livraison ayant les meilleures notes moyennes  

---

# 5. Discussion — Limites & biais  

- Le dataset est **synthétique** — les résultats doivent être interprétés avec prudence avant de les généraliser à des opérations réelles.  
- Absence d’informations fines : localisation exacte, horaire, contexte urbain/rural, nombre de tentatives, communications avec le client, etc.  
- Modélisation simplifiée des échecs : dans la vraie vie, des tentatives de re-livraison, retards partiels ou communication client peuvent influencer les résultats.  
- Potentiel biais de génération des données — certaines combinaisons distance/poids/météo/colis pourraient être sur- ou sous-représentées.  

---

# 6. Conclusion & Recommandations  

- Ce dataset constitue une **base solide** pour une première analyse des dynamiques de livraison last-mile (délais, coûts, service).  
- Il permet d’identifier **des leviers potentiels d’optimisation** (choix véhicule, planification selon météo, segmentation colis, tarification selon distance/poids).  
- Pour aller plus loin : combiner ce jeu de données avec des **données réelles** (tracking GPS, logs d’erreurs, retours clients), ou du moins simuler des scénarios plus complexes (tentatives multiples, retards partiels, priorisation des colis).  
- Utiliser les résultats pour développer des recommandations pour des prestataires logistiques — ou pour prototyper un outil de **prévision de délai & coût / optimisation de route**.  

---

# 7. Annexes / Méthodes (optionnel)  

- Script de chargement et nettoyage des données (ex. en R / Python)  
- Code pour les visualisations et analyses statistiques  
- Tableaux complets de corrélations, distributions, sous-groupes (par prestataire, par mode, etc.)  
- Définitions des catégories (type de colis, météo, etc.)  

---

