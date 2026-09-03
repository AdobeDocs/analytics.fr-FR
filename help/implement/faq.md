---
title: FAQ sur la mise en œuvre
description: Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/Hm9pIJE9P3jEljJAgB69k2M9-fTa9G0wsCjfvN4xH3E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c77ba355-6681-41fe-b719-563d3f507fdbid: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 96%

---

# FAQ sur la mise en œuvre d’Analytics

Questions fréquemment posées sur la mise en œuvre et liens vers d’autres informations.

## Quelle est la différence entre l’identifiant visiteur Experience Cloud et l’identifiant visiteur Analytics ?

Identity Service attribue un identifiant unique et persistant qui peut être partagé entre d’autres solutions dans l’entreprise CX. L’identifiant visiteur Analytics est utilisé uniquement par Analytics. Adobe recommande d’utiliser le service d’identification des visiteurs d’Experience Cloud dans votre mise en œuvre.

## Comment mettre en œuvre le suivi des vidéos Pulsation ?

Voir [Mesures audio et vidéo dans Adobe Analytics](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-overview).

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
