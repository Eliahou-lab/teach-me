<<<<<<< HEAD
# AI Coding Assistant pour lycéens

Setup minimal d'un assistant self-hosted basé sur Open WebUI, avec Mistral comme backend LLM, orchestré par Docker Compose et déployé sur Railway.

## Fichiers

- `docker-compose.yml` lance Open WebUI avec persistance locale.
- `Dockerfile` permet à Railway de builder l'image simplement.
- `railway.toml` configure le déploiement Railway.
- `system_prompt.md` contient le prompt système à coller dans Open WebUI.
- `config_du_jour.md` est le template professeur pour préparer chaque séance.

## Déploiement Railway en 5 étapes

1. Créer un nouveau repo Git avec ces fichiers et le pousser sur GitHub.
2. Dans Railway, créer un nouveau projet puis connecter le repo GitHub.
3. Ajouter la variable d'environnement `OPENAI_API_KEY` avec la clé API Mistral.
4. Déployer le service. Railway build le `Dockerfile`, lance Open WebUI sur le port `8080`, et expose l'application publiquement.
5. Ouvrir l'URL Railway générée et finaliser la configuration initiale d'Open WebUI.

## Configuration Mistral dans Open WebUI

Les variables suivantes sont déjà prévues côté conteneur:

- `OPENAI_API_BASE_URL=https://api.mistral.ai/v1`
- `OPENAI_API_KEY=${OPENAI_API_KEY}`

Open WebUI utilisera donc l'API compatible OpenAI pointée vers Mistral.

## Mise à jour du prompt système avant chaque cours

1. Remplir `config_du_jour.md` avec le contenu de la séance.
2. Copier `system_prompt.md`.
3. Remplacer les placeholders:
   - `{{project_name}}`
   - `{{stack}}`
   - `{{what_we_are_building}}`
   - `{{why_we_are_building_it}}`
   - `{{sprint_steps}}`
4. Dans Open WebUI, coller ce prompt dans le modèle, l'assistant ou l'espace de travail que les élèves vont utiliser.
5. Vérifier que le prompt insiste bien sur:
   - pas de solution complète ;
   - indices progressifs ;
   - scope limité au sprint du jour ;
   - réponses en français.

## Partage avec les élèves

- récupérer l'URL publique Railway du service ;
- la partager aux élèves ;
- leur indiquer quel assistant ou quel modèle utiliser dans Open WebUI.

## Exploitation locale

```bash
export OPENAI_API_KEY="your_mistral_key"
docker compose up -d
```

Puis ouvrir `http://localhost:3000`.
=======
# Assistant Coding Élèves - Self-Hosted

Assistant IA codé pour aider les lycéens à apprendre le "vibe coding" avec Windsurf.

## Stack

- **Open WebUI** (ghcr.io/open-webui/open-webui:main)
- **Mistral Large API** (backend LLM)
- **Docker Compose** (orchestration)
- **Railway** (hébergement)

## Déploiement sur Railway (5 étapes)

### 1. Préparer le repository
```bash
git init
git add .
git commit -m "Initial commit"
git push origin main
```

### 2. Créer un projet Railway
- Aller sur [railway.app](https://railway.app)
- Cliquer sur "New Project" → "Deploy from GitHub repo"
- Sélectionner ce repository

### 3. Configurer les variables d'environnement
Dans Railway, ajouter la variable :
- `MISTRAL_API_KEY`: Votre clé API Mistral

### 4. Déployer
- Railway détectera automatiquement le docker-compose.yml
- Le déploiement démarre automatiquement
- Attendre que le statut passe à "Running"

### 5. Récupérer l'URL
- Dans Railway, cliquer sur le service "open-webui"
- Copier l'URL générée (ex: https://xxx.railway.app)
- Partager cette URL avec les élèves

## Mise à jour du System Prompt

### Avant chaque cours :

1. **Ouvrir `config_du_jour.md`**
   - Remplir tous les placeholders `{{...}}`
   - Sauvegarder

2. **Copier dans Open WebUI**
   - Se connecter à l'interface Open WebUI
   - Aller dans "Settings" → "Prompts"
   - Coller le contenu de `system_prompt.md` avec les valeurs du jour remplies
   - Sauvegarder

3. **Tester**
   - Faire un test de conversation pour vérifier que le prompt fonctionne
   - S'assurer que l'assistant reste dans le scope du sprint

## Partager avec les Élèves

1. Partager l'URL Railway
2. Expliquer comment utiliser l'assistant :
   - Poser des questions sur le code
   - Demander des indices progressifs
   - Copier-coller les prompts Windsurf générés
3. Rappeler les règles : l'assistant ne donne pas la solution complète

## Structure des Fichiers

- `docker-compose.yml` : Configuration Docker Open WebUI
- `railway.toml` : Configuration déploiement Railway
- `system_prompt.md` : Template du prompt système (à personnaliser)
- `config_du_jour.md` : Template de configuration journalière pour le prof
- `README.md` : Ce fichier

## Maintenance

- Mettre à jour l'image Open WebUI : changer le tag dans docker-compose.yml
- Mettre à jour le prompt : modifier system_prompt.md
- Vérifier les logs Railway en cas de problème
>>>>>>> 840afd16e3360927beb9152bed6183ef0e749875
