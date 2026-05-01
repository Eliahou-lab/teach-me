# Sprint 0 - Base technique, GitHub, Vercel

## Objectif global
A la fin du Sprint 0, l'eleve a :
- un projet ChlouhIN cree ;
- la stack de base en place ;
- un premier commit ;
- un repo GitHub connecte ;
- une URL Vercel publique.

## Fondamentaux a faire comprendre
- Next.js = la structure de la maison.
- TypeScript = la ceinture de securite.
- Tailwind CSS = le systeme de style.
- shadcn/ui = les composants prets.
- Git = l'historique.
- GitHub = la sauvegarde partagee.
- Vercel = la mise en ligne.

## Micro-etapes

### 0.1 - Verifier le point de depart
But : savoir si l'eleve est pret.
Verification : terminal, Node, Git, Windsurf disponibles.
Question type : "Dis-moi si tu as deja Terminal, Node, Git, Windsurf."

### 0.2 - Creer le projet
But : avoir un dossier ChlouhIN cree avec la bonne stack.
Resultat attendu : dossier cree, dependances installees.
Verification : le dossier existe et contient la structure du projet.

### 0.3 - Comprendre les briques
But : donner du sens a la stack.
Resultat attendu : l'eleve peut dire a quoi servent Next.js, TypeScript, Tailwind, shadcn/ui.
Verification : mini reformulation par l'eleve.

### 0.4 - Lancer le projet en local
But : voir le projet fonctionner.
Resultat attendu : page Next.js visible dans le navigateur.
Verification : localhost ouvert sans erreur.

### 0.5 - Initialiser Git
But : commencer l'historique du projet.
Resultat attendu : repo Git local initialise.
Verification : `git status` fonctionne.

### 0.6 - Premier commit
But : figer la base technique.
Resultat attendu : commit initial cree.
Verification : `git log --oneline` montre le commit.

### 0.7 - Installer gh si necessaire
But : preparer la connexion GitHub proprement.
Resultat attendu : `gh` disponible.
Verification : `gh --version` ou `gh auth login` se lance.

### 0.8 - Se connecter a GitHub
But : relier la machine a GitHub.
Resultat attendu : authentification reussie.
Verification : `gh auth status` fonctionne.

### 0.9 - Creer le repo GitHub
But : creer la destination distante.
Resultat attendu : repo GitHub cree et remote connecte.
Verification : `git remote -v` affiche origin.

### 0.10 - Pousser le projet
But : mettre la base sur GitHub.
Resultat attendu : code pousse sur origin/main.
Verification : le repo GitHub affiche les fichiers.

### 0.11 - Connecter Vercel
But : preparer le deploiement automatique.
Resultat attendu : projet Vercel connecte au repo.
Verification : Vercel reconnait le projet.

### 0.12 - Premier deploiement public
But : rendre la base visible en ligne.
Resultat attendu : URL Vercel fonctionnelle.
Verification : la page par defaut s'affiche en production.

## Si la classe va vite
- On n'ajoute pas de design custom.
- On passe directement au Sprint 1.

## Erreurs frequentes
- `gh: command not found`
- `git push` sans remote
- confusion entre Git et GitHub
- confusion entre local et production
- vouloir personnaliser avant d'avoir deploye
