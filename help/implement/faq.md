---
title: FAQ sur l’implémentation
description: Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 48%

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


## J’ai exécuté AppMeasurement par le biais d’un analyseur de code, et il a signalé son utilisation comme risque de sécurité potentiel `Math.random()` . Est-il `Math.random()` utilisé avec des données sensibles ?

Non. Les chiffres utilisés `Math.random()` ne sont pas utilisés pour masquer, envoyer ou recevoir des données sensibles. Les données envoyées aux serveurs de collecte de données d’Adobe dépendent de la sécurité de la connexion HTTPS sous-jacente. <!-- AN-173590 -->

AppMeasurement utilise `Math.random()` trois domaines clés :

* **Échantillonnage**: En fonction de votre mise en oeuvre, certaines informations peuvent être collectées pour un faible pourcentage seulement de visiteurs sur votre site. `Math.random()` est utilisée pour déterminer si un visiteur donné doit envoyer des données. La plupart des implémentations n’utilisent pas l’échantillonnage.
* **ID** du visiteur de secours : Si l’ID de visiteur ne peut pas être récupéré à partir de cookies, un ID de visiteur aléatoire est généré. Cette partie d’AppMeasurement utilise deux appels à `Math.random()`.
* **Déroulement** du cache : Un nombre aléatoire est ajouté à la fin des URL de demande d’image pour empêcher la mise en cache du navigateur.
