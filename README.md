# Financial House - Test Technique Data Analyst

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-1.5.3-brightgreen)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![n8n](https://img.shields.io/badge/n8n-workflow-purple)

Ce dépôt contient l'ensemble des livrables pour le test technique de Data Analyst chez **Financial House S.A**. L'objectif de ce test est de démontrer une rigueur analytique, des compétences en manipulation de données et la capacité à générer des insights business exploitables.

**Auteur :** Darlin Kuajo
**Date :** 22-23 Février 2026

---

## Compréhension du besoin

Le test est structuré en plusieurs parties, chacune simulant une tâche réelle qu'un Data Analyst pourrait rencontrer chez Financial House :

1.  **Logique et Connaissances Métier :** Évaluation de la pensée analytique fondamentale et de la compréhension du paysage de l'analyse de données.
2.  **Étude de Cas 1 (Remboursement de Crédit) :** Un exercice de haut niveau sur les processus, les KPI et les solutions digitales pour un problème métier.
3.  **Étude de Cas 2 (Workflow n8n) :** Un projet pratique d'automatisation pour concevoir un système de gestion de leads utilisant n8n et l'IA, démontrant la capacité à construire des pipelines efficaces et low-code.
4.  **Étude de Cas 3 (Analyse des Transactions) :** Une analyse exploratoire de données (AED) approfondie de 2 000 transactions bancaires anonymisées pour comprendre le comportement des clients, l'utilisation des canaux et identifier les tendances clés. (Fichiers : `bank_transactions_cameroon_...csv`)
5.  **Étude de Cas 4 (Analyse du Risque de Crédit) :** Une analyse complète de 500 clients pour établir le profil de santé financière, évaluer les facteurs de risque de crédit et identifier les segments de clients les plus précieux et les plus risqués. (Fichier : `bank_clients_cameroon_risk_...csv`)

L'objectif principal n'est pas seulement de fournir des réponses, mais de **montrer le travail** : le processus logique, le code, les interprétations et les recommandations finales.

---

## Structure du Dépôt

Le dépôt est organisé pour plus de clarté et de facilité de révision.

```
financial-house-data-analyst-test/
│
├── README.md # Ce fichier : Aperçu du projet et structure
│
├── partie_4_n8n_workflow/ # Étude de Cas 2 : Automatisation de la gestion des leads
│ ├── documentation.md # Conception conceptuelle, choix techniques, guide d'installation
│ └── lead_manager_workflow.json # Le fichier d'export du workflow n8n
│
├── partie_5_transactions/ # Étude de Cas 3 : Analyse des transactions
│ └── analyse_transactions.ipynb # Notebook Jupyter avec l'analyse Python complète
│
├── partie_6_credit_risk/ # Étude de Cas 4 : Analyse du risque de crédit
│ └── analyse_credit_risk.ipynb # Notebook Jupyter avec l'analyse Python complète
│
└── rapport_final_darlin_kuajo.pdf # Le rapport de synthèse final à soumettre
```

---

## Technologies Utilisées

- **Langage Principal :** Python 3.12.3
- **Manipulation de Données :** Pandas, NumPy
- **Visualisation de Données :** Matplotlib, Seaborn
- **Environnement :** Jupyter Notebook
- **Automatisation :** n8n (outil de workflow low-code)
- **Contrôle de Version :** Git & GitHub

---

## Comment Exécuter les Analyses

Les analyses Python sont contenues dans des notebooks Jupyter (`.ipynb`).

1.  **Cloner le dépôt :**

    ```bash
    git clone https://github.com/kd237/financial-house-data-analyst-test.git
    cd financial-house-data-analyst-test
    ```

2.  **Configurer un environnement Python (recommandé) :**

    ```bash
    python -m venv venv
    source venv/bin/activate  # Sur Windows : venv\Scripts\activate
    ```

3.  **Installer les dépendances :**

    ```bash
    pip install pandas numpy matplotlib seaborn jupyter
    ```

4.  **Lancer Jupyter et ouvrir un notebook :**
    ```bash
    jupyter notebook
    ```
    Naviguez vers `partie_5_transactions/` ou `partie_6_credit_risk/` et ouvrez le fichier `.ipynb`.

Tout le code est abondamment commenté pour expliquer la logique derrière chaque étape.

---

## Approche et Méthodologie

Les analyses de ce projet suivent un processus structuré et itératif inspiré des meilleures pratiques de l'industrie (comme CRISP-DM), tel que décrit dans le document de référence fourni :

1.  **Poser la Question :** Chaque section des notebooks commence par reformuler la question métier à laquelle il faut répondre.
2.  **Collecte des Données :** Chargement des données CSV.
3.  **Préparation des Données (Nettoyage) :**
    - Vérification des valeurs manquantes et des doublons.
    - Vérification et correction des types de données (ex : dates, valeurs numériques).
    - Traitement des valeurs aberrantes le cas échéant.
4.  **Analyse Exploratoire :**
    - Génération de statistiques descriptives.
    - Création de champs calculés (ex : métriques d'activité client, scores composites).
5.  **Interprétation et Visualisation :**
    - Construction de graphiques clairs et informatifs pour illustrer les résultats.
    - Fourniture d'insights écrits et mise en lien avec les questions métier initiales.
6.  **Recommandations :**
    - Synthèse de l'analyse en recommandations business actionnables.

---

## Principaux Résultats et Recommandations (Aperçu)

- **Analyse des Transactions (Partie 5) :** Les canaux digitaux (Mobile & Online) dominent en volume, mais les distributeurs automatiques (ATM) restent cruciaux pour les retraits de montants élevés dans certaines villes. L'activité des clients est multidimensionnelle ; nous avons identifié des segments distincts d'utilisateurs "actifs" basés sur la fréquence et le volume.
- **Analyse du Risque de Crédit (Partie 6) :** Une corrélation claire existe entre un faible score de crédit, un nombre élevé de prêts et le défaut de paiement. Nous avons identifié des groupes d'âge et des villes spécifiques avec des profils de risque plus élevés, ainsi qu'un segment de clients à "haut potentiel" combinant revenu élevé, solde élevé et excellents scores de crédit.
- **Workflow n8n (Partie 4) :** Un système fonctionnel de gestion des leads a été conçu, démontrant la puissance de l'automatisation low-code pour qualifier instantanément les leads, générer des réponses personnalisées par IA et notifier les équipes commerciales.

---

## Statut

**Terminé / Publié** (au 23 Février 2026)

Ce dépôt représente le livrable final pour le test technique. Le projet est considéré comme terminé dans ce cadre.

---

## Crédits

- **Candidat :** Darlin Kuajo
- **Évaluateurs :** Rodrigue Awomo, Arielle Wandji (Financial House S.A)
- **Source des Données :** Fournies par Financial House S.A pour les besoins de ce test.
