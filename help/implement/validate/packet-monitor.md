---
title: Analyseurs de paquets
description: Les analyseurs de paquets vous permettent de voir les données envoyées par votre mise en œuvre aux serveurs de collecte de données Adobe.
keywords: renifleur de paquets, statut http, 200, 302, charles
feature: Validation
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 100%

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
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/fr-FR/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe ne prend PAS en charge et ne résout pas les problèmes que vous pouvez rencontrer avec ces moniteurs de paquets. Pour bénéficier d’une assistance, consultez le site d’origine du moniteur de paquets.

## Codes d’état de réponse HTTP standard

Lorsqu’AppMeasurement envoie des données aux serveurs de collecte de données d’Adobe, les serveurs répondent avec un code d’état de réponse.

* **200 OK** : réponse la plus courante des serveurs de collecte de données. La demande d’image a été reçue avec succès et une image transparente a été renvoyée.
* **302 FOUND** : il existe plusieurs explications à cette réponse :
   * Première demande d’image d’un visiteur : une redirection a lieu lorsqu’un utilisateur consulte votre site pour la première fois. Cette redirection consiste à obtenir un cookie de visiteur. Elle n’affecte pas la collecte de données.
   * Intégration entre Comscore et Adobe : si votre entreprise utilise une intégration Comscore/Analytics, chaque demande d’image génère une réponse 302.
* **404 NOT FOUND** : cette réponse signifie que la demande d’image est introuvable et que les données ne sont pas envoyées aux serveurs de collecte de données d’Adobe. Cette réponse est également possible lorsque les demandes d’image codées en dur ne sont pas correctement formatées. Collaborez avec la personne ou l’équipe responsable de la mise en œuvre d’Analytics pour résoudre ce problème.

## NS_BINDING_ABORTED dans les codes de réponse

Vous recevez ce message, car la demande d’image de suivi des liens est conçue pour autoriser le navigateur à passer à la page suivante avant d’avoir reçu une réponse des serveurs de collecte de données d’Adobe.

La réponse d’Adobe à la demande d’image est une image transparente vide de 1x1 pixel, qui n’a pas de rapport avec le contenu de la page. Si un élément de ligne Adobe s’affiche dans le moniteur de paquets avec une réponse **[!UICONTROL 200 OK]** ou **[!UICONTROL NS_BINDING_ABORTED]**, cela signifie que les données ont atteint les serveurs d’Adobe. Il n’est pas nécessaire que la page attende plus longtemps.

Les moniteurs de paquets intégrés en tant que plug-in affichent rarement la réponse complète. Ils tendent à considérer la demande comme ayant été abandonnée, car la réponse n’a pas été reçue intégralement. Il convient également d’ajouter qu’ils distinguent rarement l’élément qui a été abandonné, à savoir : la demande ou la réponse. Un moniteur de paquets autonome comporte généralement des messages plus détaillés et indique plus précisément l’état. Un utilisateur peut, par exemple, recevoir un message dans *Charles* indiquant que « le client a mis fin à la connexion avant d’avoir reçu toute la réponse ». Cela signifie que les données ont atteint les serveurs Adobe, mais que le navigateur est passé à la page suivante avant la réception du pixel 1x1.

Si un moniteur de paquets externe indique que la demande de collecte de données a été abandonnée, au lieu de la réponse, cela peut être une source de préoccupation. Adobe [!DNL Customer Care] peut vous assister dans le cadre de la résolution des problèmes.
