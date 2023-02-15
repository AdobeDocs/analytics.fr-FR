---
description: Les identifiants que vous soumettez ne couvrent pas toujours toutes les données d’accès qu’Analytics peut associer au titulaire de données. Analytics peut créer un ensemble étendu d’ID pour inclure ces données associées aux demandes relatives à la Confidentialité des données. Vous pouvez utiliser cette option avec un paramètre facultatif pour chaque demande que vous soumettez en vertu de la Confidentialité des données, ajoutée à la demande JSON.
title: Extension d’ID
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: 1ca7040156f7f2105a9625f921de3d90b4175056
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 33%

---

# Extension d’ID

Les identifiants que vous soumettez ne couvrent pas toujours toutes les données d’accès qu’Analytics peut associer au titulaire de données. Analytics peut créer un ensemble étendu d’ID pour inclure ces données associées aux demandes relatives à la Confidentialité des données. Vous pouvez utiliser cette option avec un paramètre facultatif pour chaque demande que vous soumettez en vertu de la Confidentialité des données, ajoutée à la demande JSON :

```
"expandIds": true
```

Pour plus de détails, consultez la [documentation de l’API relative aux Services de confidentialité](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=fr).


| Type | Considérations |
| --- | --- |
| Extension de l’ID de cookie | De nombreux clients Analytics utilisaient à l’origine le (hérité) [Cookie Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=en), mais utilisent désormais la variable [Experience Cloud Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). Pour les visiteurs qui ont consulté leur site web pour la première fois après la transition, seul l’ECID existe. Toutefois, pour les personnes qui ont consulté le site pour la première fois alors que seul le cookie hérité était disponible, mais qui l’ont depuis consulté : certaines de leurs données comportent les deux cookies. Toutefois, les données plus anciennes ne comportent que le cookie Analytics et, dans de rares cas, les données les plus récentes ne peuvent avoir qu’un ECID.<p>Assurez-vous de trouver toutes les données d’un visiteur identifié par un cookie ou un ECID Analytics (identifiant visiteur). Si vous utilisez actuellement l’ECID et avez précédemment utilisé le cookie Analytics, vous devez inclure les deux ID dans chaque requête que vous envoyez à l’aide de l’un ou l’autre des deux ID, ou spécifier la variable `expandIds` . Lorsque vous spécifiez `expandIds`, Adobe recherche d’autres cookies ECID ou Analytics qui correspondent aux ID de cookie que vous fournissez. La requête est automatiquement étendue pour inclure ces ID de cookie nouvellement identifiés. |
| ID personnalisé pour l’extension de l’ID de cookie | Sur les sites web d’e-commerce, il n’est pas rare qu’un visiteur navigue, ajoute des articles à son panier, puis commence le processus de paiement avant de se connecter au site. Si l’ID utilisé pour identifier les utilisateurs dans le cadre d’une demande relative à la Confidentialité des données est stocké dans une variable personnalisée uniquement lorsque l’utilisateur est connecté, cette activité de pré-connexion n’est pas associée à l’ID. Avec l’ID de cookie Analytics, les clients peuvent choisir d’associer leur consultation du site avant la connexion à l’achat effectué après la connexion, puisque l’ID de cookie est conservé lors de la connexion.<p>Supposons que votre implémentation stocke un ID de connexion (ID CRM, nom d’utilisateur, numéro de fidélité, adresse e-mail, etc., ou un hachage de l’une de ces valeurs) dans une variable personnalisée (prop ou eVar) ou un identifiant visiteur personnalisé, puis utilise cet ID dans le cas d’une demande d’accès relative à la Confidentialité des données. Le titulaire de données peut s’étonner que les informations sur sa navigation ne soient pas renvoyées dans le cadre d’une demande d’accès, en particulier si vous avez promu des articles qui ont été consultés mais qui n’ont pas encore été achetés. Le traitement en vertu de la Confidentialité des données d’Analytics prend donc en charge l’extension d’ID, où Analytics trouve tous les ID de cookie qui apparaissent dans le même accès que tout ID personnalisé, puis étend la demande de manière à inclure également ces ID.<p>When `expandIDs` est spécifié avec tout espace de noms autre qu’un espace de noms de cookie, la requête est étendue afin d’inclure tout ID de cookie (cookie ECID ou Analytics), trouvé dans les accès contenant l’un des ID spécifiés. L’extension de l’ID de cookie, comme décrit ci-dessus, est ensuite effectuée sur tout nouvel ID de cookie trouvé.<p>Lorsque la variable `expandIDs` est utilisée pour une demande d’accès et l’ID spécifié a une étiquette ID-PERSON, puis deux ensembles de fichiers seront renvoyés. Le premier ensemble (l’ensemble « person ») ne contient que des données provenant des accès dans lesquels l’ID spécifié a été trouvé. Le second ensemble (l’ensemble « device ») ne contient que des données provenant des accès des ID étendus, dans lesquels l’ID spécifié était absent. |

{style=&quot;table-layout:auto&quot;}

## Quand utiliser l’extension d’ID

Au cours des premiers mois suivant l’entrée en vigueur de la Confidentialité des données, la grande majorité des demandes relatives à la Confidentialité des données Analytics n’ont pas demandé d’extension d’ID. Cependant, il vous appartient de déterminer la valeur appropriée pour votre organisation. Consultez votre équipe juridique pour savoir si l’extension d’ID est requise pour vos données avec les ID que vous utilisez et les données que vous collectez dans Adobe Analytics.

Une considération Principale pourrait être : Sur un appareil partagé, à partir duquel plusieurs utilisateurs ont consulté votre site, l’extension d’ID inclut des données provenant des accès d’autres utilisateurs de l’appareil, dans les données renvoyées par les demandes d’accès (dans le fichier de l’appareil). Même si vous avez suivi les bonnes pratiques en matière d’étiquetage (par exemple, aucune donnée privée n’est incluse dans le fichier de l’appareil, comme les pages visitées), le fichier de l’appareil contient le nombre de pages visitées et l’heure de chacune de ces visites. Vous pouvez vous demander : Est-ce acceptable de partager ces informations avec une personne qui n’a peut-être pas été le visiteur ?

Lorsque l’extension d’ID est *not* utilisé pour une requête de suppression : si vous utilisez un ID sans cookie (tout ID autre que le cookie ECID ou Analytics) pour identifier les accès à supprimer et que cet ID possède une étiquette ID-DEVICE, alors le nombre de visiteurs uniques change dans les rapports. En effet, seules certaines instances des ID de cookie seront rendues anonymes, tandis que d’autres resteront inchangées. Si vous ne spécifiez pas d’extension d’ID, nous vous recommandons d’utiliser un ID de cookie pour les requêtes ou des ID avec une étiquette ID-PERSON.

Lorsque Adobe effectue une extension d’ID, elle peut nécessiter une analyse complète supplémentaire des données. Cela augmente le temps Adobe nécessaire pour terminer la requête, souvent en ajoutant une semaine au temps de traitement.

## Autres indicateurs de demandes relatives à la confidentialité des données

En plus de l’indicateur « expandIDs », Analytics prend en charge deux autres indicateurs qui peuvent être transmis dans le cadre d’une demande relative à la Confidentialité des données. Ces indicateurs avec leurs valeurs par défaut sont :

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

À l&#39;avenir, la `analyticsDeleteMethod` peut prendre en charge une valeur de &quot;purge&quot; en plus de la valeur par défaut de &quot;anonymize&quot;. Lorsqu’elle est prise en charge, elle entraîne la suppression de l’accès entier plutôt que de simplement mettre à jour les valeurs des champs d’accès qui possèdent des étiquettes DEL.

Outre sa valeur par défaut, la variable `priority` prend également en charge une valeur &quot;low&quot;. Vous devez spécifier cette valeur pour les demandes qui ne sont pas le résultat d’une demande du titulaire de données et qui ne sont donc pas soumises à une obligation légale de traitement dans un délai donné.

## Utilisations de l’API du Privacy Service

>[!IMPORTANT]
>
>L’Adobe ne permet pas l’utilisation de la variable [API Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=fr) pour des raisons autres que des demandes valides initiées par le titulaire de données. L’API du Privacy Service n’est pas un outil approprié pour le nettoyage ou la réparation des données. Toute utilisation abusive de l’API du Privacy Service pour des demandes non initiées par un titulaire de données aura des conséquences inattendues. L’API du Privacy Service est fournie pour Adobe aux clients afin de vous aider à répondre aux demandes relatives à la Confidentialité des données, qui sont urgentes. L’utilisation de cette API à d’autres fins n’est pas prise en charge par Adobe et peut avoir une incidence sur la capacité d’Adobe à traiter en temps voulu des demandes relatives à la Confidentialité des données pour d’autres clients Adobe. Nous vous demandons de ne pas utiliser l’API du Privacy Service à d’autres fins, comme l’hygiène des données ou l’effacement des données qui ont été soumises accidentellement à de grands groupes de visiteurs.

Vous devez également savoir que tout visiteur ayant un accès supprimé (mis à jour ou rendu anonyme) à la suite d’une demande de suppression relative à la Confidentialité des données verra ses informations publiques réinitialisées. La prochaine fois que le visiteur reviendra sur votre site Web, il sera considéré comme un nouveau visiteur. Toutes les attributions d’eVar seront réinitialisées, tout comme les informations telles que le nombre de visites, les référents, la première page visitée, etc. Le résultat n’est pas souhaitable dans les situations où vous souhaitez effacer des champs de données et met en évidence une des raisons pour lesquelles l’API du Privacy Service ne convient pas à cet usage.

Veuillez contacter votre gestionnaire de compte (CSM) pour qu’il vous mette en relation avec notre équipe de conseillers en architecture et ingénierie de données afin d’effectuer un examen plus approfondi et de fournir le niveau d’effort nécessaire pour supprimer les informations d’identification personnelles ou résoudre les problèmes de données.
