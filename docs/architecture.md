# Architecture

## High-Level Components

### 1. Source Data Generation
Python simulates raw transactional events from multiple business systems.

### 2. Bronze Layer
Raw records are ingested and stored in their original structure for traceability and replayability.

### 3. Silver Layer
Records are cleaned, standardized, deduplicated, and validated using Spark transformations.

### 4. Gold Layer
Business-focused aggregates and curated datasets are generated for analytics and dashboarding.

### 5. Orchestration
Airflow manages pipeline scheduling and dependencies across ingestion, transformation, and export jobs.

### 6. ML Handoff
Kubeflow-style pipeline definitions illustrate how curated data and engineered features can be passed into machine learning workflows.

### 7. Feature Store Preparation
Feature datasets are created in Python and exported into ML-ready structures, including PyTorch-compatible tabular datasets.

## Storage Mapping
- `data/raw/` simulates source landing zone
- `data/bronze/` stores raw ingested outputs
- `data/silver/` stores cleaned standardized data
- `data/gold/` stores curated business aggregates
- `data/features/` stores ML-ready features
