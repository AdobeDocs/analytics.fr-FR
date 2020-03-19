---
title: Analyseurs de paquets
description: Les analyseurs de paquets vous permettent de voir les données envoyées par votre mise en œuvre aux serveurs de collecte de données Adobe.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Analyseurs de paquets

Les analyseurs de paquets vous permettent de voir les données envoyées par votre mise en œuvre aux serveurs de collecte de données Adobe.

Comme le débogueur Adobe Experience Cloud, un moniteur de paquets indique les paramètres de données transmis dans une demande d’image. Cependant, les moniteurs de paquets proposent des fonctions supplémentaires :

* Affichage d’un lien personnalisé pour suivre les demandes d’image
* Affichage des demandes d’image à l’aide de méthodes de mise en œuvre autres que JavaScript, comme les demandes d’image codées en dur ou [!DNL Appmeasurement]

Pour afficher les demandes Analytics, filtrez les demandes sortantes à l’aide de « b/ss ».

Il peut arriver, dans de très rares cas, que le débogueur signale une demande d’image alors qu’il n’y en pas sur les serveurs de traitement [!DNL Analytics] d’Adobe. L’utilisation d’un moniteur de paquets est un bon moyen de s’assurer totalement qu’une demande d’image spécifique est bien déclenchée.

Même si Adobe ne fournit pas un moniteur de paquets officiel, de nombreux moniteurs sont disponibles sur Internet. Voici quelques moniteurs de paquets que d’autres utilisateurs trouvent utiles.

> [!NOTE] Ces listes destinées à informer sur les moniteurs utilisés fréquemment n’ont pas vocation à être exhaustives. Si vous utilisez un moniteur de paquets qui vous donne entière satisfaction et que vous trouvez utile, n’hésitez pas à nous faire part de vos commentaires à l’aide du bouton [!UICONTROL Commentaires] situé dans la partie droite de cette fenêtre.

| Firefox | Internet Explorer | Chrome | Programmes autonomes |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (visionneuse de balises) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (visionneuse de balises) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

> [!NOTE] Adobe NE prend PAS en charge et ne résout pas les problèmes que vous pouvez rencontrer avec ces moniteurs de paquets. Pour bénéficier d’une assistance, consultez le site d’origine de le moniteur de paquets.

## NS_BINDING_ABORTED dans les codes de réponse

Cette erreur se produit, car la demande d’image de suivi des liens est conçue pour autoriser le navigateur à passer à la page suivante avant d’avoir reçu une réponse des serveurs de collecte de données d’Adobe.

La réponse d’Adobe à la demande d’image est une image transparente vide de 1x1 pixel, qui n’a pas de rapport avec le contenu de la page. Si un élément de ligne Adobe est affiché dans le moniteur de paquets avec une réponse **[!UICONTROL 200 OK]** ou **[!UICONTROL NS_BINDING_ABORTED]**, cela signifie que les données ont atteint les serveurs Adobe. Il n’est pas nécessaire que la page attende plus longtemps.

Les moniteurs de paquets intégrés en tant que plug-in affichent rarement la réponse complète. Ils tendent à considérer la demande comme ayant été abandonnée, car la réponse n’a pas été reçue intégralement. Il convient également d’ajouter qu’ils distinguent rarement l’élément qui a été abandonné, à savoir : la demande ou la réponse. Un moniteur de paquets autonome comporte généralement des messages plus détaillés et indique plus précisément l’état. Un utilisateur peut, par exemple, recevoir un message dans *Charles* indiquant que « le client a mis fin à la connexion avant d’avoir reçu toute la réponse ». Cela signifie que les données ont atteint les serveurs Adobe, mais que le navigateur est passé à la page suivante avant la réception du pixel 1x1.

Si un renifleur de paquets externe indique que la demande de collecte de données a été abandonnée, au lieu de la réponse, cela peut être une source de préoccupation. Adobe [!DNL Customer Care] peut vous assister dans le cadre de la résolution des problèmes.
