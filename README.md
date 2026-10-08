# Systèmes Multi-Agents — Patrouille par Intelligence en Essaim

## Présentation

Projet réalisé dans le cadre d'un projet universitaire en **Systèmes Multi-Agents**.

L'objectif est d'étudier le problème de **patrouille multi-agents**, dans lequel plusieurs agents doivent explorer continuellement un environnement tout en minimisant les zones qui restent longtemps non visitées.

Le projet s'appuie sur des approches d'**intelligence en essaim** et de **stigmergie**, où les agents prennent leurs décisions localement à partir d'informations diffusées dans leur environnement.

Deux stratégies de patrouille ont été implémentées et comparées :

- **EVAP** : comportement basé sur l'évaporation de phéromones ;
- **CLInG** : comportement basé sur la diffusion d'un gradient d'oisiveté.

## Objectifs

- Modéliser un système multi-agents de patrouille.
- Implémenter deux stratégies réactives inspirées de l'intelligence en essaim.
- Étudier l'influence du nombre d'agents sur les performances.
- Tester les algorithmes sur différents types d'environnements.
- Comparer l'efficacité globale et la sécurité de la couverture.
- Analyser le temps de calcul et la scalabilité du système.

## Approche

L'environnement est représenté par une grille de **33 × 33 cases**.

Les agents se déplacent en utilisant un voisinage de **Von Neumann**, composé des quatre cases adjacentes.

Le système utilise notamment la métrique d'**oisiveté (Idleness)** : chaque case possède un compteur qui augmente lorsqu'elle n'est pas visitée et est remis à zéro lorsqu'un agent la visite.

Deux indicateurs sont utilisés :

- **IGI (Instantaneous Graph Idleness)** : mesure l'oisiveté moyenne de l'environnement.
- **IWI (Instantaneous Worst Idleness)** : mesure la pire oisiveté observée sur une case.

## Algorithmes

### EVAP

EVAP utilise un mécanisme de **phéromones avec évaporation**.

Les agents privilégient les zones ayant été moins récemment explorées afin de répartir efficacement la couverture du territoire.

### CLInG

CLInG utilise un **gradient d'oisiveté diffusé dans l'environnement**.

Les agents sont attirés vers les zones présentant une forte oisiveté, ce qui favorise la surveillance des zones susceptibles d'être délaissées.

## Expérimentations

Les deux approches ont été testées sur plusieurs topologies :

- Espace ouvert
- Spirale
- Obstacles aléatoires
- Couloirs et salles
- Labyrinthe

Les expériences ont été réalisées avec :

- 1 agent
- 4 agents
- 16 agents
- 32 agents

Chaque configuration a été exécutée plusieurs fois afin de réduire l'influence de l'aléatoire.

## Résultats

Les expérimentations montrent que les deux approches présentent des avantages différents.

**EVAP** obtient de meilleures performances en termes d'efficacité globale (IGI) dans la majorité des scénarios et présente également un temps de calcul plus faible.

**CLInG** obtient de meilleurs résultats concernant la sécurité de la couverture (IWI), notamment lorsque le nombre d'agents est faible et dans des environnements complexes.

Les résultats montrent ainsi un compromis entre **efficacité, sécurité, coût de calcul et nombre d'agents**.

## Technologies

- NetLogo
- Programmation multi-agents
- Intelligence en essaim
- Stigmergie
- Simulation
- Analyse de performances
- Visualisation de données

## Perspectives

- Intégrer la gestion de l'énergie des agents.
- Étudier des stratégies de recharge pour les robots.
- Tester des environnements plus complexes.
- Étudier des populations d'agents plus importantes.
- Améliorer les stratégies de coopération entre agents.
