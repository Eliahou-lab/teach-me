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
