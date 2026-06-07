# ☁️ Conception d'un Pipeline Data Engineering sur Azure avec Databricks et Power BI
<img width="1280" height="545" alt="work flow Azure" src="https://github.com/user-attachments/assets/c14090c7-a463-4580-a68d-974991b10332" />

## 📝 Présentation du Projet
Ce projet consiste à concevoir et implémenter une solution de **Data Engineering cloud de bout en bout** pour une entreprise du secteur retail. L'objectif est de moderniser son système décisionnel en mettant en place une architecture automatisée capable d'ingérer des sources de données hétérogènes, de les stocker, de les transformer via le moteur **Apache Spark (Databricks)** et de les restituer sous forme d'insights analytiques et orientés métier.

## 🎯 Objectifs du Projet
* **Ingestion & Orchestration Cloud** : Configurer et déployer des pipelines d'ingestion de données hybrides (Base de données SQL et API JSON externe) avec **Azure Data Factory (ADF)**.
* **Architecture Medallion** : Structurer l'entrepôt de données au sein d'**Azure Data Lake Storage Gen2 (ADLS)** à travers les trois couches de maturité : **Bronze** (Données brutes), **Silver** (Données nettoyées) et **Gold** (Données agrégées).
* **Traitement Distribué** : Développer des notebooks de transformation robustes sous **Azure Databricks** en manipulant des DataFrames PySpark et en réalisant des jointures complexes.
* **Modélisation & Décision** : Connecter la couche Gold à **Power BI** pour modéliser les données et bâtir un tableau de bord interactif d'aide à la décision.

## 🛠️ Stack Technique
* **Orchestrateur & Ingestion** : Azure Data Factory (ADF).
* **Stockage Cloud** : Azure Data Lake Storage Gen2 (ADLS).
* **Moteur de Calcul** : Azure Databricks (Apache Spark / PySpark).
* **Sources de Données** : Base de données relationnelle (SQL) & API REST (Fichiers JSON).
* **Restitution BI** : Power BI Desktop.
* **Gestion de Projet** : Jira & GitHub.

---

## 🏗️ Architecture Globale du Pipeline

Le flux de données transite de manière entièrement automatisée à travers l'écosystème cloud Azure :

1.  **Extraction & Ingestion (ADF)** : Extraction simultanée des données transactionnelles SQL et des données de l'API JSON vers le stockage d'objets.
2.  **🥉 Couche Bronze (Raw Layer)** : Réception et persistance des données brutes au format natif au sein d'ADLS Gen2.
3.  **🥈 Couche Silver (Cleansed Layer)** : Montage (*Mounting*) du Data Lake dans Databricks, nettoyage, normalisation des schémas, gestion des types et dédoublonnement.
4.  **🥇 Couche Gold (Curated Business Layer)** : Jointure des différentes sources et agrégation des indicateurs de performance clés (KPIs) orientés Retail.
5.  **📊 Restitution (Power BI)** : Chargement de la couche Gold pour la création d'un dashboard décisionnel interactif.

---

## 🚀 Étapes de Réalisation

### 1. Ingestion et Orchestration avec ADF 🔄
* Déploiement et liaison des services de stockage (ADLS Gen2) et des sources de données.
* Configuration des pipelines d'intégration de données (*Copy Data Activities*) pour automatiser le flux des serveurs SQL et des endpoints d'API JSON vers la couche Bronze.

### 2. Nettoyage et Transformation avec Databricks 🧠
* Création et configuration d'un cluster Spark sous Azure Databricks.
* Développement des scripts PySpark pour nettoyer les données (couche Silver) : standardisation des formats de date, suppression des doublons et alignement des types de données.
* Réalisation des jointures métier complexes entre les datasets pour consolider la vision client et produit.

### 3. Agrégation Métier (Couche Gold) 💎
* Structuration et calcul des indicateurs agrégés indispensables à l'analyse de performance retail.
* Exportation des données raffinées de la couche Gold sous forme de tables finales ou de fichiers structurés (Parquet/CSV) prêts à être consommés.

### 4. Modélisation BI et Insights 📊
* Connexion native de Power BI aux données de la couche Gold sur Azure.
* Conception de rapports analytiques interactifs mettant en avant la performance des ventes, les tendances temporelles et la segmentation produit.

---
