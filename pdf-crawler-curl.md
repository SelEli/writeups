# Extraction de PDF protégé via curl — Calameo

## Index
- [Contexte](#contexte)
- [Objectif](#objectif)
- [Méthode](#méthode)
- [Compétences mobilisées](#compétences-mobilisées)
- [Résultat](#résultat)
- [Ce que j'ai appris](#ce-que-jai-appris)

---

## Contexte

Magazine publié sur Calameo avec téléchargement désactivé.
Le document était librement accessible en lecture mais
l'option de téléchargement avait été volontairement bloquée
par l'hébergeur.

## Objectif

Récupérer le document complet en contournant la restriction
de téléchargement par analyse de la structure de la ressource.

## Méthode

1. Inspection du code source via DevTools (F12) — onglet
   Network et Resources
2. Identification du pattern de stockage des pages :
   chaque page du PDF est servie comme image individuelle
   depuis une URL prévisible et séquentielle
3. Rétro-ingénierie du schéma d'URL pour en déduire
   la structure complète
4. Écriture d'un script CLI avec curl pour automatiser
   le téléchargement séquentiel de chaque page
5. Reconstruction du document complet depuis les ressources
   récupérées

## Compétences mobilisées

- Analyse de requêtes HTTP via DevTools
- Compréhension de la structure de stockage d'une ressource web
- Scripting CLI et automatisation curl
- Rétro-ingénierie d'API non documentée

## Résultat

Document complet récupéré de façon automatisée.
Script réutilisable sur tout document Calameo suivant
le même pattern de stockage.

## Ce que j'ai appris

Comprendre qu'une restriction de téléchargement côté interface
ne signifie pas protection côté serveur. Les ressources
accessibles en lecture sont accessibles en téléchargement
si l'URL de stockage est identifiable. Première approche
concrète de la reconnaissance passive et de l'analyse
de surface d'exposition d'une application web.
