---
title: Analyseurs de paquets
description: Les analyseurs de paquets vous permettent de voir les données envoyées par votre mise en œuvre aux serveurs de collecte de données Adobe.
keywords: packet sniffer, http status, 200, 302, charles
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 60%

---


# Analyseurs de paquets

Les analyseurs de paquets vous permettent de voir les données envoyées par votre mise en œuvre aux serveurs de collecte de données Adobe.

Comme le débogueur Adobe Experience Cloud, un moniteur de paquets indique les paramètres de données transmis dans une demande d’image. Cependant, les moniteurs de paquets proposent des fonctions supplémentaires :

* Affichage d’un lien personnalisé pour suivre les demandes d’image
* Affichage des demandes d’image à l’aide de méthodes de mise en œuvre autres que JavaScript, comme les demandes d’image codées en dur ou [!DNL Appmeasurement]

Pour afficher les demandes Analytics, filtrez les demandes sortantes à l’aide de « b/ss ».

Il peut arriver, dans de très rares cas, que le débogueur signale une demande d’image alors qu’il n’y en pas sur les serveurs de traitement [!DNL Analytics] d’Adobe. L’utilisation d’un moniteur de paquets est un bon moyen de s’assurer totalement qu’une demande d’image spécifique est bien déclenchée.

Même si Adobe ne fournit pas un moniteur de paquets officiel, de nombreux moniteurs sont disponibles sur Internet. Voici quelques moniteurs de paquets que d’autres utilisateurs trouvent utiles.

>[!TIP]
>
>Ces listes destinées à informer sur les moniteurs utilisés fréquemment n’ont pas vocation à être exhaustives.

| Firefox | Internet Explorer | Chrome | Programmes autonomes |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (visionneuse de balises) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (visionneuse de balises) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe ne prend PAS en charge ou ne résout pas les problèmes que vous rencontrez avec ces moniteurs de paquets. Consultez le site d’origine du moniteur de paquets pour obtenir de l’aide.

## Codes d’état de réponse HTTP standard

Lorsque AppMeasurement envoie des données aux serveurs de collecte de données d’Adobe, les serveurs répondent avec un code d’état de réponse.

* **200 OK**: Réponse la plus courante des serveurs de collecte de données. La demande d&#39;image a été reçue avec succès et une image transparente a été renvoyée.
* **302 TROUVÉ**: Il y a deux ou trois raisons possibles de recevoir cette réponse :
   * Première demande d’image d’un visiteur : Une redirection se produit si un utilisateur consulte votre site pour la première fois. Cette redirection consiste à obtenir un cookie visiteur. Elle n’affecte pas la collecte de données.
   * Intégration entre Comscore et Adobe : Si votre entreprise utilise une intégration Comscore/Analytics, chaque demande d’image génère toujours une réponse 302.
* **404 NON TROUVÉ**: Cette réponse signifie que la demande d’image est introuvable et que les données ne sont pas envoyées aux serveurs de collecte de données d’Adobe. Cette réponse est également possible lorsque les demandes d’image codées en dur ne sont pas correctement formatées. Collaborez avec la personne ou l’équipe qui a mis en oeuvre Analytics pour résoudre ce problème.

## NS_BINDING_ABORTED dans les codes de réponse

Ce message se produit car la demande d’image de suivi des liens est conçue pour permettre au navigateur de passer à la page suivante avant d’attendre une réponse des serveurs de collecte de données d’Adobe.

La réponse d’Adobe à la demande d’image est une image transparente vide de 1x1 pixel, qui n’a pas de rapport avec le contenu de la page. If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached Adobe&#39;s servers. Il n’est pas nécessaire que la page attende plus longtemps.

Les moniteurs de paquets intégrés en tant que plug-in affichent rarement la réponse complète. Ils tendent à considérer la demande comme ayant été abandonnée, car la réponse n’a pas été reçue intégralement. Il convient également d’ajouter qu’ils distinguent rarement l’élément qui a été abandonné, à savoir : la demande ou la réponse. Un moniteur de paquets autonome comporte généralement des messages plus détaillés et indique plus précisément l’état. Un utilisateur peut, par exemple, recevoir un message dans *Charles* indiquant que « le client a mis fin à la connexion avant d’avoir reçu toute la réponse ». Cela signifie que les données ont atteint les serveurs Adobe, mais que le navigateur est passé à la page suivante avant la réception du pixel 1x1.

Si un moniteur de paquets externe signale que la demande de collecte de données est abandonnée, plutôt que la réponse, cela peut être source de préoccupation. Adobe [!DNL Customer Care] peut vous assister dans le cadre de la résolution des problèmes.
