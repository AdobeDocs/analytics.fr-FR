---
title: Analyseurs de paquets
description: Les analyseurs de paquets vous permettent de voir les données envoyées par votre mise en œuvre aux serveurs de collecte de données Adobe.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analyseurs de paquets

Les analyseurs de paquets vous permettent de voir les données envoyées par votre mise en œuvre aux serveurs de collecte de données Adobe.

Comme le débogueur Adobe Experience Cloud, un moniteur de paquets indique les paramètres de données transmis dans une demande d’image. Cependant, les moniteurs de paquets proposent des fonctions supplémentaires :

* Affichage d’un lien personnalisé pour suivre les demandes d’image
* Affichage des demandes d’image à l’aide de méthodes de mise en œuvre autres que JavaScript, comme les demandes d’image codées en dur ou [!DNL Appmeasurement]

Pour afficher les demandes Analytics, filtrez les demandes sortantes à l’aide de « b/ss ».

Il peut arriver, dans de très rares cas, que le débogueur signale une demande d’image alors qu’il n’y en pas sur les serveurs de traitement [!DNL Analytics] d’Adobe. L’utilisation d’un moniteur de paquets est un excellent moyen d’être sûr à 100 % qu’une demande d’image spécifique est déclenchée avec succès.

Bien qu’Adobe ne fournisse pas de moniteur de paquets officiel, il existe un grand nombre d’entre eux sur Internet. Voici quelques moniteurs de paquets que d&#39;autres ont trouvés utiles.

>[!NOTE] Ces listes destinées à informer sur les moniteurs utilisés fréquemment n’ont pas vocation à être exhaustives. Si vous disposez d&#39;un moniteur de paquets que vous utilisez avec succès et que vous trouvez utile, n&#39;hésitez pas à nous faire part de vos commentaires à l&#39;aide du [!UICONTROL Feedback] bouton situé à droite de cette fenêtre.

| Firefox | Internet Explorer | Chrome | autonome  |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (lecteur de balises) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (lecteur de balises) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE] Adobe NE prend PAS en charge et ne résout pas les problèmes que vous pouvez rencontrer avec ces moniteurs de paquets. Pour bénéficier d’une assistance, consultez le site d’origine de le moniteur de paquets.

## NS_BINDING_ABORTED dans les codes de réponse

Cette erreur se produit car la demande d’image de suivi des liens est conçue pour permettre au navigateur de passer à la page suivante avant d’attendre une réponse des serveurs de collecte de données Adobe.

La réponse d’Adobe à la demande d’image est simplement une image transparente vide 1x1, qui n’est pas pertinente pour le contenu de la page. Si un élément de ligne Adobe est affiché dans le moniteur de paquets avec une réponse **[!UICONTROL 200 OK]** ou **[!UICONTROL NS_BINDING_ABORTED]**, cela signifie que les données ont atteint les serveurs Adobe. Il n’est pas nécessaire que la page attende plus longtemps.

Les moniteurs de paquets intégrés en tant que plug-in affichent rarement la réponse complète. Ils ont tendance à considérer la demande comme abandonnée car la réponse complète n’a pas été reçue. Ces moniteurs font rarement la distinction entre la demande ou la réponse qui a été abandonnée. Un moniteur de paquets autonome comporte généralement des messages plus détaillés et signale l’état de manière plus précise. Par exemple, un utilisateur peut recevoir un message dans *Charles* indiquant que le client a fermé la connexion avant de recevoir une réponse complète. Cela signifie que les données ont atteint nos serveurs, juste le navigateur est passé à la page suivante avant la réception du pixel 1x1.

Si un renifleur de paquets externe est  que la demande de collecte de données est abandonnée, plutôt que la réponse, cela est un motif de préoccupation. Adobe [!DNL Customer Care] peut vous assister dans le cadre de la résolution des problèmes.
