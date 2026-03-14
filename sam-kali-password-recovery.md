# Récupération d'accès Windows via dump SAM — Kali Linux

## Contexte

Stage en entreprise de maintenance informatique, partenaire 
d'une école professionnelle post-bac. Mission : remise en état 
d'une salle de cours avant la rentrée (nettoyage, mise à jour).

Problème découvert sur 4 postes Windows : impossibilité de 
se connecter malgré des mots de passe corrects. Après échange 
avec la responsable, diagnostic : les machines avaient perdu 
leurs droits d'authentification auprès du serveur réseau 
(problème de jonction domaine).

## Objectif

Restaurer l'accès local aux 4 postes sans réinstallation 
complète, puis les réintégrer au domaine avec les credentials 
d'origine.

## Méthode

1. Déconnexion des machines du réseau
2. Boot sur live USB Kali Linux
3. Montage de la partition Windows
4. Accès au fichier SAM et suppression des hash de mots de passe 
   via chntpw
5. Redémarrage sur Windows — accès local restauré
6. Reconnexion au domaine et recréation des credentials réseau 
   d'origine

## Résultat

4 postes pleinement opérationnels, réintégrés au domaine, 
credentials réseau restaurés à l'identique. Intervention 
réalisée de manière autonome après diagnostic initial.

## Ce que j'ai appris

Comprendre comment Windows stocke et vérifie les credentials 
locaux vs domaine. Identifier la différence entre un problème 
de mot de passe et un problème de jonction domaine. Manipuler 
le fichier SAM en environnement live pour intervenir sur un 
système verrouillé.
