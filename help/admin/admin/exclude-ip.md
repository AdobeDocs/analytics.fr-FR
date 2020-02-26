---
description: Vous pouvez exclure de vos rapports les données d’adresses IP spécifiques (activités internes du site web, tests du site et utilisation par les employés, par exemple). L’élimination de données améliore la précision du rapport en excluant des données d’adresse IP. De plus, vous pouvez supprimer les données des attaques par déni de service ou autres événements malveillants susceptibles de biaiser les résultats de vos rapports. Vous pouvez configurer l’exclusion en utilisant votre pare-feu.
title: Exclure par adresse IP
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Exclure par adresse IP

Vous pouvez exclure de vos rapports les données d’adresses IP spécifiques (activités internes du site web, tests du site et utilisation par les employés, par exemple). L’élimination de données améliore la précision du rapport en excluant des données d’adresse IP. De plus, vous pouvez supprimer les données des attaques par déni de service ou autres événements malveillants susceptibles de biaiser les résultats de vos rapports. Vous pouvez configurer l’exclusion en utilisant votre pare-feu.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclure par IP]**

> [!NOTE] Les accès exclus par adresse IP sont facturés en tant qu’[appels au serveur](https://marketing.adobe.com/resources/help/fr_FR/reference/primary_server_calls.html).

## Exclure par cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Cette fonction vous permet d’exclure cet ordinateur du suivi dans votre compte. Si vous choisissez d’exclure votre ordinateur, aucune donnée générée à partir de celui-ci n’est prise en compte.

Cette fonction vous permet (à vous ainsi qu’à vos collègues) de visiter votre site sans biaiser vos données de trafic. Utilisez cette fonctionnalité si vous n’avez pas d’adresse IP statique (connexion à Internet par ligne commutée via un fournisseur d’accès Internet, par exemple) et si vous souhaitez vous exclure des données de compte.

| Élément | Description |
|--- |--- |
| [!UICONTROL Ajouter CNAME] | Génère un lien d’exclusion que vous pouvez utiliser pour exclure votre domaine. Pour obtenir de l’aide, veuillez contacter l’assistance clientèle de votre société. <br>Vous pouvez exclure votre trafic de la création de rapports dans vos suites de rapports en consultant la page d’exclusion de votre société et en choisissant d’exclure votre navigateur de la mesure. <br>Si votre implémentation utilise des cookies tiers, votre page d’exclusion se trouve [ici](https://democorp.112.2o7.net/optout.html?locale=fr_FR&amp;popup=true) : |

> [!NOTE] L’exclusion par ordinateur ne fonctionne que dans les cas suivants :
>
> * Vous accédez au site web à partir du même poste de travail.
> * Les cookies sont activés dans le navigateur que vous utilisez.
> * Les cookies ne sont pas supprimés. Si les cookies sont supprimés, vous devez vous exclure de nouveau.


## Exclure par adresse IP {#section_609FB6461529409D840111A32FEF5C3D}

Une adresse IP est une adresse Internet. Des adresses IP numériques sont attribuées à tous les utilisateurs d’Internet (généralement par l’intermédiaire de fournisseurs d’accès Internet). Ces adresses font office d’identifiants électroniques.

Les pages vues sont comptabilisées et les visiteurs de pages uniques sont identifiés au moyen de leurs adresses IP. En excluant les adresses IP du comptage, vous pouvez empêcher Adobe d’effectuer le suivi des visiteurs fréquents. Cette fonction vous permet, ainsi qu’à vos collègues, de visiter votre site sans biaiser les données de trafic. Vous pouvez exclure jusqu’à 50 adresses IP différentes.

Vous pouvez utiliser des caractères de remplacement pour exclure une plage d’adresses. Par exemple, `[!DNL 0.0.*.0]` exclut toutes les adresses IP comprises entre `[!DNL 0.0.0.0]` et `[!DNL 0.0.255.0]`. Vous pouvez exclure jusqu’à 50 adresses IP différentes.

## Exclure par pare-feu {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

Vous pouvez également bloquer la collecte de données à partir d’adresses IP spécifiques par le biais d’un pare-feu.

Reportez-vous à l’article [Adresses IP utilisées dans Experience Cloud](https://marketing.adobe.com/resources/help/fr_FR/home/index.html#kb-adobe-ip-addresses).

## Impact de l’obscurcissement des adresses IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si l’obscurcissement d’IP est activé, l’exclusion de l’adresse IP survient avant l’obscurcissement ; ainsi, les clients n’ont rien à changer lorsqu’ils activent cette option.

Si le dernier octet est supprimé, ceci a lieu avant le filtrage IP. Par conséquent, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour afin de correspondre aux adresses IP avec un zéro à la fin. Le * correspondant doit correspondre à 0.
