# A61-TP: Production Machine Learning

Guide pour préparer, tester et exécuter la solution d'IA.

## 1. Environnement (Git Bash)

Activer l'environnement virtuel :
```bash
# python -m venv env_mlflow
source ~/OneDrive/Documents/dev/python/cours-6/env_mlflow/Scripts/activate
```

## 2. Package: Regression Model

Tester le modèle de régression (logique métier).

```bash
# Aller dans le dossier du modèle
cd packages/regression_model

# Installer les dépendances
pip install -r requirements.txt

# Lancer les tests
tox
```

## 3. Package: ML API (Flask)

Tester et lancer l'API web (qui utilise le modèle).

```bash
# Aller dans le dossier de l'API
cd ../ml_api  # ou le chemin complet

# Installer les dépendances (installe aussi le modèle localement)
pip install -r requirements.txt

# Option A : Lancer les tests unitaires
python -m pytest

# Option B : Lancer l'application (Serveur Web)
python run.py
```

## 4. Désactiver l'environnement

```bash
deactivate
```