---
description: Affiche les liens préférés des visiteurs de votre site. La page d’accueil, par exemple, comporte probablement plusieurs liens qui permettent d’afficher la même page, notamment un lien graphique et un lien texte. Ce rapport indique le pourcentage des visiteurs qui utilisent le lien graphique plutôt que le lien texte.
title: Syntaxe
topic: Reports
uuid: 2e0d0175-d5e4-4919-b601-3f488ef3e090
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Syntaxe

Affiche les liens préférés des visiteurs de votre site. La page d’accueil, par exemple, comporte probablement plusieurs liens qui permettent d’afficher la même page, notamment un lien graphique et un lien texte. Ce rapport indique le pourcentage des visiteurs qui utilisent le lien graphique plutôt que le lien texte.

Les liens spécifiques dont vous souhaitez effectuer le suivi doivent être modifiés à l’aide de balises spéciales ; voir [Suivi des liens](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html).

Vous pouvez utiliser le rapport [!UICONTROL Liens personnalisés] pour :

* optimiser la conception de votre site en sachant quels sont les types de liens préférés par les visiteurs ;
* valider la nécessité de disposer de liens redondants vers des pages uniques.

## Noms des liens SDK mobiles {#section_70C91FE794104B5FBF289B19CC02EA8E}

Les [SDK mobiles](https://marketing.adobe.com/resources/help/en_US/mobile/home.html) utilisent des liens personnalisés pour effectuer un suivi sur les actions et les mesures de cycle de vie. Dans les suites de rapports utilisées pour mesurer les applications mobiles, les noms de lien suivants définis par le SDK peuvent s’afficher :

| ADBINTERNAL:Lifecycle | Envoyé par l’appel de cycle de vie dans les SDK 4.x. |
|---|---|
| AMACTION:[nom de l’action] | Envoyé par la méthode trackAction() dans les SDK 4.x, où le nom de l’action correspond au nom défini à l’appel de la méthode. |
| ADMS BP Event | Envoyé par l’appel de cycle de vie dans les SDK 3.x. |

