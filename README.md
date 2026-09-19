# ATD — Test UX/UI Designer

Conception d'une version simplifiée et accessible d'un parcours mobile permettant à un usager de soumettre et suivre une démarche en ligne.

## Prototype

**Prototype Figma :** 

**Livrable :** 5 écrans mobile couvrant les étapes essentielles de la démarche.

---

## 1. Contexte

Le parcours initial permet à un usager de soumettre une démarche en ligne depuis son téléphone.

L'analyse du parcours fourni met en évidence plusieurs sources de friction :

* absence d'informations essentielles avant le début de la démarche ;
* formulaire contenant 12 champs sur un même écran ;
* champs obligatoires peu explicites ;
* libellés difficiles à comprendre ;
* messages d'erreur techniques et peu utiles ;
* absence d'aide pour résoudre les erreurs ;
* récapitulatif dense avant validation ;
* action finale peu rassurante ;
* manque de visibilité sur l'avancement de la démarche ;
* absence d'information sur la prochaine étape après transmission.

L'objectif est de réduire ces frictions sans ajouter de complexité au parcours.

---

# 2. Objectifs UX

La proposition cible poursuit six objectifs principaux :

1. **Réduire la charge cognitive** en structurant progressivement les informations.
2. **Clarifier les actions et les contenus** avec une hiérarchie visuelle simple.
3. **Rendre les erreurs actionnables** avec des messages compréhensibles et une solution associée.
4. **Donner de la visibilité sur la progression** pendant la démarche.
5. **Rassurer avant la transmission** grâce à un récapitulatif clair et modifiable.
6. **Donner de la visibilité après la transmission** avec une référence, un statut et une prochaine étape.

---

# 3. Parcours cible

Le parcours est restructuré autour de cinq écrans :

```text
Accueil
   ↓
Informations
   ↓
Pièces justificatives
   ↓
Vérification
   ↓
Confirmation et suivi
```

La progression visible permet à l'usager de comprendre où il se trouve dans la démarche et ce qu'il lui reste à accomplir.

---

# 4. Principaux arbitrages UX/UI

## 4.1. Informer avant de demander

### Problème

L'écran d'accueil initial contient un long texte explicatif, mais ne précise pas la durée de la démarche ni les pièces à préparer.

### Choix

Remplacer le paragraphe par une présentation synthétique :

* durée indicative ;
* nombre de pièces nécessaires ;
* possibilité d'effectuer la démarche depuis un téléphone ;
* étapes principales du parcours.

### Arbitrage

L'information utile est conservée, mais présentée avant l'action sous une forme rapidement scannable.

---

## 4.2. Réduire la charge cognitive du formulaire

### Problème

Le parcours initial présente 12 champs sur un seul écran, avec des champs requis peu explicites.

### Choix

Structurer le formulaire avec :

* une hiérarchie claire ;
* des labels explicites ;
* une indication des champs obligatoires ;
* des espacements suffisants ;
* une progression par étape.

### Arbitrage

La quantité d'informations métier n'est pas supprimée. Elle est organisée pour éviter de présenter simultanément toutes les informations à l'usager.

---

## 4.3. Remplacer le jargon technique par une erreur actionnable

### Problème

Le parcours initial affiche `ERR_UPLOAD_413` lorsqu'un fichier ne peut pas être téléversé. Le message n'explique ni le problème ni la manière de le résoudre.

### Choix

Remplacer le message technique par :

> **Document trop volumineux**
> Ce fichier dépasse la taille maximale de 5 Mo. Choisissez un fichier plus léger.

Avec une action :

> **Choisir un autre fichier**

### Arbitrage

L'information technique nécessaire au système n'est pas exposée à l'utilisateur. Le message se concentre sur la compréhension du problème et sa résolution.

---

## 4.4. Rendre la validation réversible avant transmission

### Problème

Le parcours initial présente un bloc dense de données et une action intitulée « VALIDER DÉFINITIVEMENT », perçue comme irréversible.

### Choix

Créer un écran de vérification organisé en sections :

* informations ;
* pièces justificatives ;
* confirmation.

Chaque section peut être modifiée avant la transmission.

Le bouton devient :

> **Transmettre ma demande**

### Arbitrage

Le libellé décrit précisément l'action effectuée. La dernière étape sert de contrôle avant transmission, plutôt que de présenter une validation abstraite ou anxiogène.

---

## 4.5. Donner une progression visible

### Problème

Le parcours initial ne permet pas suffisamment de comprendre l'état d'avancement de la démarche.

### Choix

Utiliser un indicateur de progression :

**Informations → Pièces → Vérification**

avec une distinction claire entre :

* étape terminée ;
* étape actuelle ;
* étape à venir.

### Arbitrage

La progression reste volontairement simple afin de ne pas ajouter une couche d'information inutile sur mobile.

---

## 4.6. Donner une réponse utile après la transmission

### Problème

Le parcours initial confirme uniquement que le dossier a été transmis et fournit une référence, sans délai ni prochaine étape.

### Choix

L'écran de confirmation fournit :

* confirmation de l'enregistrement ;
* référence de la demande ;
* statut actuel ;
* prochaines étapes ;
* accès au suivi.

### Arbitrage

Aucun délai de traitement n'est inventé, car le parcours fourni ne donne pas cette information. L'interface indique plutôt ce que l'usager peut faire ensuite.

---

# 5. Architecture de l'information

L'architecture suit une logique progressive :

### 01 — Comprendre

L'usager découvre la démarche et les informations nécessaires avant de commencer.

### 02 — Renseigner

Il fournit les informations nécessaires.

### 03 — Justifier

Il ajoute les documents demandés.

### 04 — Vérifier

Il contrôle ses informations avant transmission.

### 05 — Suivre

Il obtient une confirmation et peut suivre l'évolution de sa demande.

Cette structure sépare les différentes tâches cognitives au lieu de présenter toutes les informations simultanément.

---

# 6. Hiérarchie visuelle

La hiérarchie visuelle repose sur quatre niveaux :

1. **Titre de l'écran** : comprendre immédiatement où l'on se trouve.
2. **Titre et sections** : comprendre la tâche actuelle.
3. **Contenu et champs** : réaliser la tâche.
4. **Actions** : identifier clairement l'action principale.

Chaque écran possède une action principale afin de limiter les hésitations.

Les informations secondaires sont volontairement moins dominantes visuellement.

---

# 7. Gestion des erreurs

Les erreurs suivent une logique en trois parties :

**Problème → Explication → Action**

Exemple :

> **Document trop volumineux**
> Ce fichier dépasse la taille maximale de 5 Mo. Choisissez un fichier plus léger.
> **Choisir un autre fichier**

Cette approche évite les codes techniques et permet à l'usager de comprendre immédiatement comment continuer.

---

# 8. Accessibilité

La conception prend en compte les principes suivants :

* contraste suffisant ;
* typographie lisible ;
* labels explicites ;
* champs suffisamment espacés ;
* zones tactiles adaptées ;
* hiérarchie visuelle claire ;
* messages d'erreur compréhensibles ;
* états identifiables sans dépendre uniquement de la couleur ;
* langage simple ;
* actions prévisibles.

L'objectif est de rendre le parcours utilisable par des personnes ayant différents niveaux de familiarité avec les services numériques.

---

# 9. Adaptation mobile

Le parcours est conçu mobile-first.

Les choix principaux sont :

* structure en une colonne ;
* marges et espacements adaptés aux petits écrans ;
* boutons facilement accessibles au toucher ;
* contenu court et scannable ;
* champs suffisamment espacés ;
* progression visible ;
* absence de tableaux ou structures complexes ;
* priorité donnée au contenu et aux actions essentielles.

---

# 10. Structure des écrans

| Écran                     | Objectif                                         | Action principale      |
| ------------------------- | ------------------------------------------------ | ---------------------- |
| 01. Accueil               | Comprendre la démarche avant de commencer        | Commencer              |
| 02. Informations          | Renseigner les informations nécessaires          | Continuer              |
| 03. Pièces justificatives | Ajouter les documents nécessaires                | Continuer              |
| 04. Vérification          | Contrôler et corriger les données                | Transmettre ma demande |
| 05. Confirmation          | Confirmer l'enregistrement et permettre le suivi | Suivre ma demande      |

---

# 11. Principes retenus

La proposition repose sur quelques principes simples :

* **Informer avant de demander.**
* **Une étape, une intention principale.**
* **Réduire la charge cognitive plutôt que supprimer arbitrairement des informations.**
* **Transformer les erreurs en indications utiles.**
* **Permettre la vérification avant une action importante.**
* **Toujours donner un retour après une action.**
* **Donner à l'usager une visibilité sur la suite du parcours.**
* **Concevoir d'abord pour les contraintes du mobile.**
* **Ne pas utiliser la couleur comme seul moyen de communication.**

---

# 12. Livrables

* Prototype mobile haute fidélité
* 5 écrans principaux
* Parcours utilisateur simplifié
* Gestion d'un état d'erreur
* Écran de confirmation et de suivi
* Justification des principaux choix UX/UI

---

## Prototype

[Figma — Prototype interactif](LIEN_FIGMA)

## Auteur

**Christophe Anani**

UX/UI Designer
