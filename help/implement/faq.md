---
title: FAQ sur la mise en œuvre
description: Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: ht
source-wordcount: '508'
ht-degree: 100%

---

# FAQ sur la mise en œuvre d’Analytics

Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.

## Quelle est la différence entre l’identifiant visiteur Experience Cloud et l’identifiant visiteur Analytics ?

Identity Service affecte un identifiant persistant unique qui peut être partagé entre d’autres solutions dans Experience Cloud. L’identifiant visiteur Analytics est utilisé uniquement par Analytics. Adobe recommande d’utiliser le service d’identification des visiteurs d’Experience Cloud dans votre mise en œuvre.

## Comment mettre en œuvre le suivi des vidéos Pulsation ?

Voir [Mesures audio et vidéo dans Adobe Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=fr).

## Une interruption de service chez Adobe peut-elle affecter les performances ?

Non. Le fichier JavaScript n’est pas hébergé sur les serveurs Adobe. Par conséquent, une panne des serveurs Adobe n’affecte pas votre bibliothèque AppMeasurement. Si vous utilisez les balises dans Adobe Experience Platform, le fichier JavaScript est hébergé par Akamai ou sur un emplacement de serveur déterminé par votre organisation.

## L’envoi de données du navigateur vers les services Adobe peut-il réduire les performances ?

AppMeasurement crée un objet image dans la page HTML, puis le navigateur demande l’objet image auprès des serveurs de collecte de données Adobe. Si les serveurs Adobe sont lents ou ne répondent pas, le thread gérant cette demande est retardé jusqu’à ce que l’image réapparaisse ou qu’une temporisation se produise. Les navigateurs gèrent les images avec plusieurs threads. Pour cette raison, les pannes de serveurs Adobe ont peu d’incidence sur le temps de chargement de la page puisqu’un seul thread est concerné tandis que les autres continuent à fonctionner.

## Comment puis-je invalider ou supprimer une mise en œuvre Analytics ?

Il arrive qu’une entreprise souhaite supprimer une mise en œuvre en raison de l’expiration du contrat ou afin de réduire le nombre d’appels au serveur.

* **Implémentations utilisant la collecte de données Adobe Experience Platform** : désactivez ou désinstallez l’extension Adobe Analytics, SDK Web ou SDK Mobile applicable dans l’onglet [!UICONTROL Extensions], puis publiez.
* **Mises en œuvre AppMeasurement héritées** : remplacez l’intégralité du contenu de votre fichier `s_code.js` par la ligne de code suivante :

```js
var s = new Object();
```

>[!WARNING]
>
>N’effectuez aucune des actions suivantes :
>
>* Remplacer la suite de rapports par une valeur non valide, car cela génère une charge inutile sur les serveurs d’Adobe.
>* Supprimer complètement le fichier `s_code.js`, sauf si vous supprimez également toutes les références au fichier sur chaque page.
>* Modifier la variable `trackingServer` afin qu’elle ne pointe plus vers Adobe. AppMeasurement continue à envoyer des demandes d’image, qui renvoient des erreurs 404.

## J’ai exécuté AppMeasurement par le biais d’un analyseur de code et il a signalé son utilisation de `Math.random()` comme risque potentiel de sécurité. `Math.random()` est-il utilisé avec des données sensibles ?

Non. Les nombres qui utilisent `Math.random()` ne sont pas utilisés pour masquer, envoyer ou recevoir des données sensibles. Les données envoyées aux serveurs de collecte de données d’Adobe dépendent de la sécurité de la connexion HTTPS sous-jacente. <!-- AN-173590 -->

AppMeasurement utilise `Math.random()` dans trois domaines clés :

* **Échantillonnage** : en fonction de votre implémentation, certaines informations peuvent être collectées pour un faible pourcentage seulement de visiteurs sur votre site. `Math.random()` est utilisé pour déterminer si un visiteur donné doit envoyer des données. La plupart des implémentations n’utilisent pas l’échantillonnage.
* **Identifiant visiteur de secours** : si l’identifiant visiteur ne peut pas être récupéré à partir de cookies, un identifiant visiteur aléatoire est généré. Cette partie d’AppMeasurement utilise deux appels à `Math.random()`.
* **Contournement de la mémoire cache** : un nombre aléatoire est ajouté à la fin des URL de demande d’image pour empêcher le caching du navigateur.
