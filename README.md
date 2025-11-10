# Challenge - Inspection et Analyse d'un Repository GIT

## Consignes générales

Ce challenge a pour but d'évaluer votre capacité à **explorer, comprendre et analyser l'historique d'un projet GIT**.

### Règles

- **Aucune interface graphique n'est autorisée**, vous devez travailler **exclusivement en ligne de commande** (sauf pour le FORK depuis Github)
- **L'utilisation d'outils d'intelligence artificielle est strictement interdite.**
- Vous pouvez utiliser la documentation à l'adresse suivante: https://git-scm.com/book/fr/v2
- **Objectif : comprendre l'évolution du code et reconstituer les décisions prises.**

## Travail à effectuer

Le dépôt d'origine à utiliser est disponible à l'adresse suivante :
```bash
https://github.com/ETML-RRY/324_inspection_git.git
```

### Partie 1 - Préparation

1. Faites un *FORK* du dépôt sur votre compte GitHub (Attention il faut copier toutes les branches donc il faut **décocher** la case "Copy the main branch only" sur l'interface de Github)
2. Ajoutez votre enseignant comme collaborateur à votre dépôt forké.
3. Vous trouverez une réplique de ces instructions dans le fichier README.md de votre dépôt.
4. Répondez directement aux questions dans le fichier README.md qui est au format **Markdown**
5. Pour chaque points, veuillez noter la ou les commandes `git` utilisées vous permettant de répondre à la question.
6. Pour chaque partie, effectuez au minimum un commit et un push lorsque vous avez complété les réponses de la partie correspondante.

> Le format Markdown: [https://www.markdownguide.org/basic-syntax/](https://www.markdownguide.org/basic-syntax/)


### Partie 2 — Exploration de base

1. Combien de branches existent dans le dépôt ? Citez-les.  
5, `main`, `experiment/dark-mode`, `feature/header`, `feature/login`, `hotfix/login`
2. Quels sont les **tags** disponibles ? A quoi correspondent-ils ? 
 `v0.1`, `v0.2`, au version
3. Quelle est la **branche principale** du projet ?
`main``

Commandes utilisées:
- `git branch -a`
- `git tag`

### Partie 3 — Historique et commits

4. Quel est le message du **premier commit** du projet ? 
`Initial commit: structure HTML/CSS/JS + README + docs`
5. Trouvez le commit où une **clé API** a été ajoutée par erreur. Quel est son identifiant (hash court) ?  
`bea2d1aeaecd11e9c0af36cf6f052f65e82d36c5`
6. Quel commit a ensuite corrigé cette erreur ?  
`1b682c91ef14cda333419e2e387a53033ae575a1`
7. Trouvez le commit où le **titre de la page d'accueil** a été corrigé.
`6317c073f7514d580522c90fa1f0f0402066a48f`
8. Quel est le message du commit qui a **ajouté le fichier `CHANGELOG.md`** et quelle commande avez-vous utilisé ?
`docs: ajoute un changelog de base`

Commands utilisées:
- `git log --reverse` 
- `git log --grep "API"`
- `git log --grep "titre"`
- `git log --follow docs/CHANGELOG.md`

### Partie 4 — Branches et fusions

9. Quelles branches ont été fusionnées dans `main` ?
`feature/header`,`feature/login`,`hotfix/type`
10. Quelle branche **n'a pas été fusionnée** ? Pourquoi, selon vous ? 
`experiment/dark-mode`, car c'est experimental donc pas fini.

Commandes utilisées:
- `git branch -a --merged main`
- `git branch -a --no-merged main`

### Partie 5 — Analyse du contenu

11. Quelle est la **différence principale** entre les fichiers `index.html` dans les versions `v0.1` et `v0.2` et quelle commande permet de le voir rapidement ?  
Le header a été ajouté.
12. Que contient la branche `feature/login` ?  
Le code du login
13. Dans quelle branche a été ajouté le code pour le **mode sombre** ? 
`experiment/dark-mode`
14. Quelle bonne pratique de sécurité est évoquée dans les commits du fichier `config.js` ?
Ne pas mettre des clé API dans le code.

Commandes utilisées:
- `git diff v0.1 v0.2 index.html`

### Partie 6 — Réflexion

15. Pourquoi est-il important de **taguer** des versions dans un projet ? 
16. Que peut-on déduire du style de travail de l'équipe à partir de cet historique GIT ?  

Bonne chance, et surtout... **ne vous perdez pas dans le log !** 😉