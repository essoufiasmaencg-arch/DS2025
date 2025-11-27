1. Introduction / Objectif du dataset

Le jeu de données décrit un ensemble de 25 000 enregistrements de livraisons “last-mile” (dernier kilomètre) à travers plusieurs régions d’Inde, effectuées par divers prestataires logistiques.
L’objectif principal : offrir une représentation réaliste des opérations de livraison — avec les contraintes réelles (distance, mode de livraison, météo, type de colis, véhicule, etc.) — afin de permettre des analyses opérationnelles, logistiques, de coût, d’efficacité, d’impact environnemental, de délais et de qualité de service.

Ce dataset se présente comme un outil approprié pour des travaux académiques, analytiques ou pour le secteur privé qui cherche à améliorer la performance logistique ou étudier des patterns dans les livraisons.

2. Structure & Contenu — Description des colonnes / variables

Chaque enregistrement (ligne) contient les informations suivantes :

delivery_id : identifiant unique de la livraison

delivery_partner : le prestataire logistique (Prestataires présents : Delhivery, Blue Dart, Ekart, DHL, FedEx, Shadowfax, XpressBees, Amazon Logistics, Ecom Express).

package_type : type de colis (électronique, nourriture, meubles, objets fragiles, etc.)

vehicle_type : type de véhicule utilisé (vélo/moto, van, camion, véhicule électrique, etc.)

delivery_mode : mode de livraison (Standard, Express, Same Day, Two Day)

region : région de livraison (Nord, Sud, Est, Ouest, Centre)

weather_condition : conditions météorologiques durant la livraison (Clair, Pluie, Brouillard, Tempête, Chaleur, Froid)

distance_km : distance parcourue en km (entre 1 et 300 km — ce qui couvre les livraisons urbaines, péri-urbaines, inter-urbaines)

package_weight_kg : poids du colis (0.2 à 50 kg)

delivery_time_hours : temps réel de livraison — durée totale utilisée (incluant les retards)

expected_time_hours : temps estimé initial selon le mode de livraison

delayed : indicateur — livraison retardée ? (Yes/No) — si le temps réel dépasse l’estimation

delivery_status : statut final (Delivered, Delayed, Failed) — dépend du retard ou d’un échec éventuel

delivery_rating : évaluation client (note de 1 à 5), reflétant la satisfaction du service selon le résultat

delivery_cost : coût calculé de la livraison — prenant en compte distance, poids, mode de livraison (les modes rapides comme Express ou Same Day incluent des surtaxes)

Le dataset est propre : pas de valeurs manquantes, consistance des champs, formatage conforme, valeurs dans des plages réalistes.

3. Ce que ce dataset permet d’analyser — Opportunités d’étude

Avec ces données, plusieurs axes d’analyse ou de recherche sont possibles :

Analyse des délais : comparer le temps réel vs le temps estimé selon le mode, le prestataire, le véhicule, la météo, la distance, etc. Identifier les facteurs qui causent les retards (météo, distance, type de véhicule, package).

Efficacité logistique / optimisation des routes : étudier l’efficacité des livraisons selon les régions, le type de trajet (urbain vs inter-urbain), la densité de colis, le type de colis, etc.

Comportement des coûts : observer comment le coût évolue selon – distance, poids, mode de livraison, prestataire — et étudier des modèles de tarification ou des stratégies de réduction de coût.

Qualité de service & satisfaction client : croiser les retards, les échecs, le statut final avec la note client — pour identifier les leviers d’amélioration du service.

Impact des conditions environnementales : mesurer l’effet de la météo (pluie, brouillard, chaleur, froid, tempête) sur les délais et les résultats — utile pour modéliser des risques ou prévoir des plans de contingence.

Comparaison de prestataires / flotte de véhicules : évaluer la performance (retards, échecs, coûts, satisfaction) selon les prestataires et le type de véhicule (bike, van, truck, EV).

Analyse multi-critères — par exemple, est-ce que les colis lourds + longues distances + mauvais temps augmentent de façon non linéaire les délais ou les coûts ?

Ainsi, ce dataset est particulièrement bien adapté pour des analyses logistiques, optimisation, data-science appliquée au supply chain, modélisation de délais, etc.

4. Forces et limites du dataset (qualité, utilité, biais possibles)
✅ Forces / points positifs

Grande taille : 25 000 enregistrements, ce qui offre une base conséquente pour l’analyse statistique.

Richesse des informations : nombreuses variables qualitatives et quantitatives — ce qui permet des analyses croisées variées.

Propreté des données : aucune valeur manquante, format uniforme, plausibilité des valeurs — ce qui réduit le travail de nettoyage et renforce la fiabilité.

Variété des scénarios : plusieurs prestataires, modes de livraison, types de colis, météo, distances — ce qui rend le dataset représentatif d’un large spectre de conditions réelles.

Sécurité / anonymat : pas d’information personnelle — donc utilisable librement pour recherche, analyses ou projets académiques / business.

⚠️ Limitations & points de vigilance

Données synthétiques : le dataset a été généré via un pipeline de modélisation — ce qui peut impliquer des simplifications ou des hypothèses irréalistes. Certaines interactions complexes du monde réel (trafic, erreurs humaines, imprévus de livraison) peuvent ne pas être fidèlement reproduites.

Absence d’informations temporelles fines ou géographiques précises : si le dataset n’inclut pas de fuseau horaire, d’heure exacte, de localisation GPS, d’adresse, ou de contexte urbain vs rural plus précis — cela limite les analyses fines (ex. « quel quartier ? pic trafic ? »).

Modélisation des “échecs” / “livraisons ratées” possiblement simpliste — si la probabilité d’échec est simulée, elle pourrait ne pas refléter des comportements réels (ex. tentative de re-livraison, retour au dépôt, contact client, etc.).

Biais potentiels selon la génération — si le pipeline de génération n’a pas bien calibré les distributions (distance, poids, météo, colis) selon la réalité, certaines catégories pourraient être sous- ou sur-représentées.

Pas d’aspect humain / opérationnel — le dataset ne contient pas d’information sur le livreur, le nombre de tentatives, la satisfaction qualitative, les retours clients, etc. Ce qui limite certaines analyses socio-logistiques.

5. Conclusion et recommandations d’utilisation

Ce dataset est une excellente base “last-mile delivery” pour des analyses logistiques, des modèles d’optimisation, des études de coût et de retards, ou des projets de recherche sur la supply chain.

Recommandations :

Lors de l’analyse, être conscient que les données sont synthétiques — vérifier que les résultats / patterns observés soient plausibles pour des opérations réelles.

Compléter (idéalement) avec des données réelles si possible — pour valider ou calibrer les modèles issus de ce dataset.

Utiliser des visualisations et des indicateurs clés (delays %, moyenne de delivery_time vs expected_time, distribution des poids/distances, corrélations météo-retards, etc.) pour tirer des insights clairs et exploitables.
