# Guide rapide pour démarrer le projet

## 1. Créer et activer l'environnement virtuel

```bash
python -m venv env_mlflow
source ~/Documents/dev/python/cours-6/env_mlflow/Scripts/activate
```

## 2. Installer les dépendances

```bash
pip install --upgrade pip
pip install -r requirements.txt
pip install -U pytest
pip install mlflow

pip list
```

## 3. (Optionnel) Activer un autre environnement

```bash
source ~/Documents/dev/python/cours-6/env_mlflow/Scripts/activate
```

## 4. Désactiver l'environnement

```bash
deactivate
```
