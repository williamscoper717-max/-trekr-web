# Guide de Déploiement Trekr sur Vercel

Ce projet est configuré comme un monorepo pour Vercel, avec le Frontend React et le Backend FastAPI.

## Étapes de déploiement

1. **Prérequis** :
   - Un compte Vercel.
   - Une base de données PostgreSQL (ex: Vercel Postgres, Supabase, ou Neon).

2. **Configuration sur Vercel** :
   - Importez votre dépôt sur Vercel.
   - Configurez les variables d'environnement suivantes dans les paramètres du projet Vercel.

### Variables d'Environnement Obligatoires

| Variable | Description | Exemple |
| :--- | :--- | :--- |
| `DATABASE_URL` | URL de votre base de données PostgreSQL | `postgresql://user:pass@host:5432/db` |
| `SECRET_KEY` | Clé secrète pour les JWT | Une chaîne aléatoire longue |
| `ALGORITHM` | Algorithme JWT | `HS256` |
| `SECRET_APP_KEY` | Clé secrète pour les sessions | Une chaîne aléatoire |
| `UPLOAD_DIR` | Dossier pour les uploads | `images` |

### Initialisation de la Base de Données

Une fois le projet lié à votre base de données, vous pouvez initialiser les tables en exécutant localement (avec la DATABASE_URL configurée) :
```bash
python api/init_db.py
```

## Structure du Projet
- `/` : Frontend React (Vite)
- `/api` : Backend FastAPI (Python)
- `vercel.json` : Configuration du déploiement monorepo
