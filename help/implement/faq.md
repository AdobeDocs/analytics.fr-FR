---
title: FAQ sur l’implémentation
description: Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 67%

---


# FAQ sur la mise en œuvre d’Analytics

Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.

## Quelle est la différence entre l’identifiant visiteur Experience Cloud et l’identifiant visiteur Analytics ?

Identity Service affecte un identifiant persistant unique qui peut être partagé entre d’autres solutions dans Experience Cloud. L’identifiant visiteur Analytics est utilisé uniquement par Analytics. Adobe recommande d’utiliser le service d’identification des visiteurs d’Experience Cloud dans votre mise en œuvre.

## Comment mettre en œuvre le suivi des vidéos Pulsation ?

Voir [Mesures audio et vidéo dans Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/media-analytics/using/media-overview.html).

## Une interruption de service chez Adobe peut-elle affecter les performances ?

Non. Le fichier JavaScript n’est pas hébergé sur les serveurs Adobe. Par conséquent, une panne des serveurs Adobe n’affecte pas votre bibliothèque AppMeasurement. Si vous utilisez Adobe Experience Platform Launch, le fichier JavaScript est hébergé par Akamai ou sur un emplacement de serveur déterminé par votre entreprise.

## L’envoi de données du navigateur vers les services Adobe peut-il réduire les performances ?

AppMeasurement crée un objet image dans la page HTML, puis le navigateur demande l’objet image auprès des serveurs de collecte de données Adobe. Si les serveurs Adobe sont lents ou ne répondent pas, le thread gérant cette demande est retardé jusqu’à ce que l’image réapparaisse ou qu’une temporisation se produise. Les navigateurs gèrent les images avec plusieurs threads. Pour cette raison, les pannes de serveurs Adobe ont peu d’incidence sur le temps de chargement de la page puisqu’un seul thread est concerné tandis que les autres continuent à fonctionner.

## Comment puis-je invalider ou supprimer une mise en oeuvre Analytics ?

Il arrive qu’une entreprise souhaite supprimer une implémentation en raison de l’expiration du contrat ou réduire le nombre d’appels au serveur.

* **Implémentations à l’aide du lancement**: Désactivez ou désinstallez l’extension Adobe Analytics dans l’onglet [!UICONTROL Extensions] , puis publiez.
* **Implémentations** AppMeasurement héritées : Remplacez l’intégralité du contenu de votre `s_code.js` fichier par la ligne de code suivante :

```js
var s = new Object();
```

>[!WARNING]
>
>Ne pas :
>
>* Remplacez la suite de rapports par une valeur non valide, car elle crée une charge inutile sur les serveurs d’Adobe.
>* Supprimez complètement le `s_code.js` fichier, sauf si vous supprimez également toutes les références au fichier sur chaque page.
>* Modifiez la `trackingServer` variable pour qu’elle pointe loin de l’Adobe. AppMeasurement envoie toujours des demandes d’image, qui renvoient des erreurs 404.

