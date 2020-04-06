---
description: Vous pouvez exclure de vos rapports les données d’adresses IP spécifiques (activités internes du site web, tests du site et utilisation par les employés, par exemple). L’exclusion des données améliore la précision du rapport en excluant les données d’adresse IP. De plus, vous pouvez supprimer des données du déni de service ou d’autres  malveillants qui peuvent biaiser les données de rapport. Vous pouvez configurer l’exclusion ou à l’aide de votre pare-feu.
title: Exclure par adresse IP
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Exclure par adresse IP

Vous pouvez exclure de vos rapports les données d’adresses IP spécifiques (activités internes du site web, tests du site et utilisation par les employés, par exemple). L’exclusion des données améliore la précision du rapport en excluant les données d’adresse IP. De plus, vous pouvez supprimer des données du déni de service ou d’autres  malveillants qui peuvent biaiser les données de rapport. Vous pouvez configurer l’exclusion ou à l’aide de votre pare-feu.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE] Les accès exclus par adresse IP sont facturés en tant qu’[appels au serveur](https://marketing.adobe.com/resources/help/fr_FR/reference/primary_server_calls.html).

## Exclure par cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Vous permet d’exclure cet ordinateur du suivi dans votre compte. Si vous choisissez d’exclure votre ordinateur, aucune donnée générée à partir de celui-ci n’est comptabilisée.

Cette fonction vous permet (à vous ainsi qu’à vos collègues) de visiter votre site sans biaiser vos données de trafic. Vous pouvez utiliser cette fonctionnalité si vous n’avez pas d’adresse IP statique (comme une connexion Internet par ligne commutée via un) et souhaitez vous exclure des données de votre compte.

| Elément | Description |
|--- |--- |
| [!UICONTROL Add CNAME] | Génère un lien d’exclusion que vous pouvez utiliser pour exclure votre domaine. Pour obtenir de l’aide, veuillez contacter l’assistance clientèle de votre société. <br>Vous pouvez exclure votre trafic de la création de rapports dans vos suites de rapports en consultant la page d’exclusion de votre société et en choisissant d’exclure votre navigateur de la mesure. <br>Si votre implémentation utilise des cookies tiers, votre page d’exclusion se trouve [ici](https://democorp.112.2o7.net/optout.html?locale=fr_FR&amp;popup=true) : |

>[!NOTE] L’exclusion par ordinateur ne fonctionne que dans les cas suivants :
>
> * Vous accédez au site Web à partir du même poste de travail.
> * Les cookies sont activés dans le navigateur que vous utilisez.
> * Les cookies ne sont pas supprimés. Si les cookies sont supprimés, vous devez vous exclure de nouveau.


## Exclure par adresse IP {#section_609FB6461529409D840111A32FEF5C3D}

Une adresse IP est une adresse Internet. Tous les utilisateurs d’Internet se voient attribuer des adresses IP numériques (généralement par l’intermédiaire de Internet) qui agissent efficacement comme identifiants électroniques.

Les  de page sont comptabilisées et les de page uniques sont identifiés par le biais d’adresses IP. En excluant les adresses IP du comptage, vous pouvez empêcher Adobe de suivre les fréquents. Cette fonctionnalité peut vous permettre, ainsi qu’à vos collègues, de visiter votre site sans biaiser vos données de trafic. Vous pouvez exclure jusqu&#39;à 50 adresses IP différentes.

Vous pouvez utiliser des indicateurs génériques (*) pour exclure une plage d’adresses. Par exemple, `[!DNL 0.0.*.0]` exclut toutes les adresses IP comprises entre `[!DNL 0.0.0.0]` et `[!DNL 0.0.255.0]`. Vous pouvez exclure jusqu’à 50 adresses IP différentes.

## Exclure par pare-feu {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

Vous pouvez également bloquer la collecte de données à partir d’adresses IP spécifiques par le biais d’un pare-feu.

Reportez-vous à l’article Adresses [IP utilisées dans Experience Cloud](https://marketing.adobe.com/resources/help/fr_FR/home/index.html#kb-adobe-ip-addresses) .

## Impact de l’obscurcissement des adresses IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si l’obscurcissement d’IP est activé, l’exclusion de l’adresse IP survient avant l’obscurcissement ; ainsi, les clients n’ont rien à changer lorsqu’ils activent cette option.

Si le dernier octet est supprimé, cela se fait avant le filtrage IP. Ainsi, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour pour correspondre aux adresses IP avec un zéro à la fin. Le * correspondant doit correspondre à 0.
