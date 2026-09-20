# PFE — Plateforme Big Data de collecte et d'analyse des offres d'emploi

Projet de Fin d'Études — Approche Data Engineering avec Microsoft Fabric.

## Résumé

Ce projet vise à concevoir une plateforme Big Data capable de collecter régulièrement des offres
d'emploi provenant de plusieurs sources (API France Travail, Open Data, référentiels métiers,
fichiers CSV/JSON), de les centraliser dans Microsoft Fabric (OneLake / Lakehouse), de contrôler
leur qualité, de les stocker selon une architecture **Bronze / Silver / Gold**, puis de produire des
analyses du marché de l'emploi dans **Power BI**.

Le projet est volontairement centré sur le Data Engineering (pas de volet IA/ML/NLP dans cette
première version).

## Axes du projet

1. Qualité des données
2. Stockage des données
3. Analyse des données
4. Sécurité et gouvernance

## Stack technique

- **Plateforme** : Microsoft Fabric
- **Ingestion / orchestration** : Data Factory, Pipelines Fabric
- **Stockage** : OneLake, Lakehouse, tables Delta
- **Traitement** : PySpark
- **Analyse** : SQL, modèle sémantique
- **Restitution** : Power BI

## Structure du dépôt

```
.
├── docs/                          # Rapport de cadrage, dictionnaire de données
├── notebooks/                     # Notebooks Fabric (ingestion, nettoyage, qualité)
│   ├── 01_ingestion_bronze_france_travail.py
│   └── 02_ingestion_bronze_autres_sources.py
├── .gitignore
└── README.md
```

## Sources de données

| Source | Description |
|---|---|
| API Offres d'emploi France Travail | Source principale, offres actives en temps réel |
| Open Data France Travail (data.gouv.fr) | Données historiques / volumétrie de test |
| Référentiels métiers | Harmonisation des catégories de métiers |
| Fichiers CSV / JSON | Sources complémentaires / tests de schémas |

## Architecture cible

```
Sources → Fabric Data Factory / Pipelines → OneLake + Lakehouse
        → Bronze → Silver → Gold → SQL / Modèle sémantique → Power BI
```

## État d'avancement

- [x] Cadrage du projet et rédaction du document d'architecture
- [x] Premiers notebooks d'ingestion Bronze (API + autres sources)
- [ ] Accès validé à l'API France Travail
- [ ] Nettoyage PySpark et couche Silver
- [ ] Règles de Data Quality
- [ ] Couche Gold et modèle dimensionnel
- [ ] Dashboard Power BI
- [ ] Sécurité et monitoring

## Auteur

Projet de Fin d'Études — [Votre nom], [Filière / promotion]
