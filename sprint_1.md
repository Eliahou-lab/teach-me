# Sprint 1 - Structure visible du produit

## Objectif global
A la fin du Sprint 1, l'eleve a un debut de vrai produit visible :
- des pages principales ;
- une navbar ;
- une home simple et lisible ;
- une structure claire pour la suite.

## Fondamentaux a faire comprendre
- une route = une page ;
- une navbar = une navigation commune ;
- une home = une promesse produit claire ;
- on construit d'abord la structure, puis les donnees.

## Micro-etapes

### 1.1 - Creer les routes principales
Routes visees :
- /
- /map
- /beth-habad/[slug]
- /chaliah/[slug]
- /login
- /dashboard
Resultat attendu : chaque route s'ouvre sans casser l'app.

### 1.2 - Verifier la structure
But : voir que les pages existent vraiment.
Verification : test local des routes une par une.

### 1.3 - Ajouter une navbar minimale
But : creer un repere de navigation.
Resultat attendu : nom du produit + liens essentiels.
Verification : la navbar s'affiche proprement.

### 1.4 - Integrer la navbar dans la structure globale
But : eviter de la dupliquer partout.
Resultat attendu : navbar visible sur les pages utiles.
Verification : la navigation reste coherente en changeant de page.

### 1.5 - Remplacer la home par une vraie page d'accueil
But : sortir de la page Next.js par defaut.
Resultat attendu : titre, sous-titre, bouton, proposition de valeur simple.
Verification : on comprend en 5 secondes ce qu'est ChlouhIN.

### 1.6 - Faire une verification utilisateur
But : verifier que le produit ressemble a un debut de produit.
Checklist :
- home lisible
- navbar visible
- liens principaux presents
- pages existantes
- aucun crash visible

### 1.7 - Commit et push du Sprint 1
But : figer la structure visible.
Resultat attendu : code pousse, Vercel redeploie.
Verification : la version en ligne reflète la version locale.

## Si la classe va vite
- on peut commencer a preparer la logique metier du Sprint 2 ;
- on ne part pas sur des details decoratifs.

## Erreurs frequentes
- vouloir faire trop de pages detaillees trop tot
- ajouter des liens hors sprint
- passer du temps sur le design au lieu de la structure
- oublier de verifier la production apres push
