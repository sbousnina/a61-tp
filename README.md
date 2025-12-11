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

```bash
deactivate
```

## 5. Documentation API

Liste des endpoints disponibles :

### Health Check
Vérifier si le service est en ligne.
- **URL** : `/health`
- **Méthode** : `GET`
- **Réponse** : `ok` (Text)

### Version
Récupérer les versions du modèle et de l'API.
- **URL** : `/version`
- **Méthode** : `GET`
- **Réponse** :
  ```json
  {
      "model_version": "0.1.0",
      "api_version": "1.0.0"
  }
  ```

### Prediction
Faire une prédiction de prix pour une maison.
- **URL** : `/v1/predict/regression`
- **Méthode** : `POST`
- **Body** : Liste d'objets JSON (Inputs).
- **Exemple** :
  ```json
  [
    {
      "Alley": "Pave",
      "BedroomAbvGr": 2,
      ...
    }
  ]
  ```
- **Réponse** :
  ```json
  {
      "predictions": [112512.05],
      "version": "0.1.0",
      "errors": null
  }
  ```