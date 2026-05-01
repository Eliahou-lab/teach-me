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
