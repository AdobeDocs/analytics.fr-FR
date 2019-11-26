---
title: Canal interne (actualisation de session)
description: Découvrez le canal Interne (actualisation de session).
translation-type: tm+mt
source-git-commit: cf05e9f5d666fd40e74028929a831dad57ee2007

---


# Canal interne (actualisation de session)

Le canal interne (souvent renommé Actualisation de la session) consiste en des visites sur le site où l’URL de référence correspond aux filtres d’URL internes configurés dans la Console d’administration, ce qui signifie que le visiteur est venu du site pour commencer sa visite.

![](assets/int-channel1.png)

## Remplacer les meilleures pratiques

Il est recommandé de désélectionner l’option de remplacement Dernière touche pour les canaux Direct et Interne, afin qu’ils ne puissent pas prendre le crédit d’autres canaux Dernière touche (ou les uns des autres) persistants.

>[!NOTE]Ce document suppose que les paramètres de remplacement de Direct et Session Refresh sont désactivés.

![](assets/int-channel2.png)

## Période d’engagement

Les canaux Première touche et Dernière touche d’un visiteur sont réinitialisés après 30 jours d’inactivité sur ce navigateur.

>[!NOTE] 30 jours est la valeur par défaut et peut être modifiée selon les besoins via les paramètres d’administration.

Si le visiteur utilise fréquemment le site, la fenêtre d’engagement s’affiche avec eux. Ils doivent être inactifs pendant 30 jours pour que la période arrive à expiration et que les canaux soient réinitialisés.
Exemple :

* Jour 1 : L’utilisateur accède au site sur Display. Les canaux Première touche et Dernière touche seront définis sur Affichage.

* Jour 2 : L'utilisateur se rend sur le site de la Recherche naturelle. La première touche reste affichée et la dernière touche est définie sur Recherche naturelle.

* Jour 35 : L'utilisateur n'est pas allé sur le site depuis 33 jours et revient en utilisant l'onglet qu'il avait ouvert dans son navigateur. En supposant qu’une fenêtre d’engagement de 30 jours soit fermée, la fenêtre aurait été fermée et les cookies de canal marketing auraient expiré. Le canal Première touche et Dernière touche sera réinitialisé et sera défini sur Actualisation de la session puisque l’utilisateur est venu d’une URL interne.

## Relation entre Première touche et Dernière touche

Pour comprendre l’interaction entre la première et la dernière touche et confirmer que les remplacements fonctionnent comme prévu, vous pouvez extraire un rapport Canal Première touche, sous-lié à un rapport Canal Dernière touche, avec votre mesure de réussite clé ajoutée dans (voir l’exemple ci-dessous). Cet exemple illustre l’interaction entre les canaux Première touche et Dernière touche.

![](assets/int-channel3.png)

L’intersection où first est égal à last-touch est surlignée en orange. Direct et Session Refresh n’obtiennent le crédit Dernière touche que s’ils étaient également le canal Première touche, car ils ne peuvent pas prendre le crédit d’autres canaux persistants (lignes en surbrillance grisées).

## Pourquoi l’actualisation de session se produit-elle ?

Comme nous savons que l’actualisation de session Dernière touche ne peut avoir lieu que s’il s’agissait également de la première touche, les scénarios ci-dessous expliquent comment l’actualisation de session peut être un canal Première touche.

### Scénario 1 : Délai de session

Un visiteur se rend sur le site Web, puis laisse l’onglet ouvert dans son navigateur pour l’utiliser ultérieurement. La période d’engagement du visiteur expire (ou bien il supprime volontairement ses cookies) et il utilise l’onglet ouvert pour se rendre à nouveau sur le site Web. L’URL de référence étant un domaine interne, la visite est classée comme Actualisation de la session.

### Scénario 2 : Toutes les pages du site ne sont pas balisées

Un visiteur arrive sur la page A qui n’est pas balisée, puis passe à la page B qui est balisée. La page A serait considérée comme le référent interne et la visite serait classée comme Actualisation de la session.

### Scénario 3 : Redirections

Si aucune redirection n’est configurée pour transmettre les données de référent à la nouvelle page de renvoi, les données de référent d’entrée réelle sont perdues et la page de redirection (probablement une page interne) apparaît désormais comme domaine référent. La visite sera classée comme Actualisation de la session.

### Scénario 4 : Trafic inter-domaines

Un visiteur passe d’un domaine qui se déclenche vers la suite A à un autre domaine qui se déclenche vers la suite B. Si, dans la suite B, les filtres d’URL internes incluent le premier domaine, la visite dans la suite B est enregistrée comme interne, puisque les canaux marketing la considèrent comme une nouvelle visite dans la deuxième suite. La visite sera classée comme Actualisation de la session.

### Scénario 5 : Temps de chargement long de la page d’entrée

Un visiteur accède à la page A, qui contient beaucoup de contenu, et le code Adobe Analytics se trouve au bas de la page. Avant que tout le contenu (y compris la demande d’image Adobe Analytics) puisse être chargé, le visiteur clique sur la page B. La page B déclenche sa demande d’image Adobe Analytics. Comme la demande d’image de la page A n’a jamais été chargée, la deuxième page apparaît comme le premier accès de la visite dans Adobe Analytics, avec la page A comme référent. La visite est classée comme actualisation de session.

### Scénario 6 : Effacement des cookies au milieu du site

Un visiteur se rend sur le site et efface ses cookies en milieu de session. Les canaux Première touche et Dernière touche sont réinitialisés et la visite est classée comme Actualisation de la session (car le référent est interne).
