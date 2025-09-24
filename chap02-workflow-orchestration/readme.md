📊 Chapitre 2 : Workflow Orchestration avec Kestra
🎯 Objectif Réalisé

Automatiser l'ingestion et la transformation des données de taxis (vert et jaune) de New York avec une approche scalable et industrialisée.
🔄 Parcours d'Implémentation
1️⃣ Phase Locale avec PostgreSQL

    Ingestion des données Green Taxis 🟩 via Kestra

    Configuration des pipelines de base

    Validation des workflows en environnement contrôlé

2️⃣ Migration vers le Cloud (GCP)

    Stockage : Google Cloud Storage

    Data Warehouse : BigQuery

    Challenge surmonté : Gestion des volumes importants de données Yellow Taxis 🟨

🛠️ Fonctionnalités Implémentées avec Kestra
✅ Gestion du Backfill

    Traitement automatique des périodes manquantes (notamment 2021)

    Reprocessing fiable des données historiques

✅ Automatisation Avancée

    Combinaisons dynamiques année-mois-type de taxi via ForEach + Subflow

    Patterns de workflow réutilisables et modulaires

✅ Orchestration Intelligente

    Déclenchement par planning avec Schedule triggers

    Monitoring intégré des exécutions

    Gestion d'erreurs et reprises automatiques

📁 Structure du Projet
text

data-engineering-zoomcamp-2025/
├── docker-compose.yml          # Orchestration Docker
├── chap02-workflow-orchestration/
│   ├── kestra/
│   │   └── flows/             # Workflows Kestra
│   │       ├── gcp_ny_taxi_scheduled.yaml
│   │       ├── my_postgres_ny_taxi_scheduled.yaml
│   │       └── ...
│   └── dbt/                   # Transformations DBT
├── chap03-data-warehouse/     # Configuration BigQuery
└── ...

🚀 Workflows Disponibles

Les workflows Kestra sont organisés par environnement :
🌐 Cloud (GCP)

    gcp_ny_taxi_scheduled.yaml : Pipeline complet cloud avec backfill

    gcp_setup.yml : Configuration de l'environnement GCP

💻 Local (PostgreSQL)

    my_postgres_ny_taxi_scheduled.yaml : Version locale du pipeline

    02_postgres_taxi.yml : Ingestion basique PostgreSQL

### Démarrage rapide :
```bash
# Cloner le repository
git clone https://github.com/MoussaInc/data-engineering-zoomcamp-2025
cd data-engineering-zoomcamp-2025

# Lancer les services
docker-compose up -d

# Vérifier le statut
docker-compose ps