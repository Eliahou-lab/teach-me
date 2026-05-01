# AI Coding Assistant pour lyceens

Setup minimal d'un assistant self-hosted base sur Open WebUI, avec Mistral comme backend LLM, orchestre par Docker Compose et deploye sur Railway.

## Fichiers

- `docker-compose.yml` lance Open WebUI avec persistance locale.
- `Dockerfile` permet a Railway de builder l'image simplement.
- `railway.toml` configure le deploiement Railway.
- `system_prompt.md` contient le prompt systeme a coller dans Open WebUI.
- `config_du_jour.md` est le template professeur pour preparer chaque seance.

## Deploiement Railway en 5 etapes

1. Creer un nouveau repo Git avec ces fichiers et le pousser sur GitHub.
2. Dans Railway, creer un nouveau projet puis connecter le repo GitHub.
3. Ajouter la variable d'environnement `OPENAI_API_KEY` avec la cle API Mistral.
4. Deployer le service. Railway build le `Dockerfile`, lance Open WebUI sur le port `8080`, et expose l'application publiquement.
5. Ouvrir l'URL Railway generee et finaliser la configuration initiale d'Open WebUI.

## Configuration Mistral dans Open WebUI

Les variables suivantes sont deja prevues cote conteneur:

- `OPENAI_API_BASE_URL=https://api.mistral.ai/v1`
- `OPENAI_API_KEY=${OPENAI_API_KEY}`

Open WebUI utilisera donc l'API compatible OpenAI pointee vers Mistral.

## Mise a jour du prompt systeme avant chaque cours

1. Remplir `config_du_jour.md` avec le contenu de la seance.
2. Copier `system_prompt.md`.
3. Adapter les champs du jour.
4. Dans Open WebUI, coller ce prompt dans le modele, l'assistant ou l'espace de travail que les eleves vont utiliser.
5. Verifier que le prompt insiste bien sur:
   - pas de solution complete ;
   - indices progressifs ;
   - scope limite au sprint du jour ;
   - reponses en francais.

## Partage avec les eleves

- recuperer l'URL publique Railway du service ;
- la partager aux eleves ;
- leur indiquer quel assistant ou quel modele utiliser dans Open WebUI.

## Exploitation locale

```bash
export OPENAI_API_KEY="your_mistral_key"
docker compose up -d
```

Puis ouvrir `http://localhost:3000`.
