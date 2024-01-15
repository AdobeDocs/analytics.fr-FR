---
description: Les ID que vous soumettez ne couvrent pas toujours toutes les données d’accès qu’Analytics peut associer au titulaire de données. Analytics peut créer un ensemble étendu d’identifiants afin d’inclure ces données associées aux demandes relatives à la Confidentialité des données.
title: Extension d’ID
feature: Data Governance
role: Admin
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 96%

---

# Extension d’ID

Les ID que vous soumettez ne couvrent pas toujours toutes les données d’accès qu’Analytics peut associer au titulaire de données. Analytics peut créer un ensemble étendu d’ID pour inclure ces données associées aux demandes relatives à la Confidentialité des données. Vous pouvez utiliser cette option avec un paramètre facultatif pour chaque demande que vous soumettez en vertu de la Confidentialité des données, ajoutée à la demande JSON :

```
"expandIds": true
```

Pour plus de détails, consultez la [documentation de l’API relative aux Services de confidentialité](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=fr).


| Type | Considérations |
| --- | --- |
| Extension de l’ID de cookie | De nombreux clients et clientes Analytics utilisaient à l’origine le [cookie Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=fr) (hérité). Toutefois, ils utilisent désormais [Experience Cloud Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). Pour les visiteurs et visiteuses qui ont consulté leur site web pour la première fois après la transition, seul l’ECID existe. Toutefois, pour les personnes qui ont consulté le site pour la première fois alors que seul le cookie hérité était disponible, mais qui l’ont depuis consulté : certaines de leurs données comportent les deux cookies. Toutefois, les données plus anciennes ne comportent que le cookie Analytics et, dans de rares cas, les données les plus récentes pourraient n’avoir qu’un ECID.<p>Assurez-vous de trouver toutes les données pour un visiteur ou une visiteuse identifié(e) via un cookie ou un ECID Analytics (ID visiteur). Si vous utilisez l’ECID et avez utilisé le cookie Analytics par le passé, vous devez inclure les deux ID dans chaque requête que vous soumettez à l’aide de l’un des deux ID, ou spécifier l’option `expandIds`. Lorsque vous spécifiez `expandIds`, Adobe vérifie les autres cookies ECID ou Analytics correspondant à l’un des ID de cookies que vous fournissez. La demande est automatiquement étendue pour inclure ces ID de cookies nouvellement identifiés. |
| ID personnalisé pour l’extension de l’ID de cookie | Sur les sites web d’e-commerce, il n’est pas rare qu’un visiteur navigue, ajoute des articles à son panier, puis commence le processus de paiement avant de se connecter au site. Si l’ID utilisé pour identifier les utilisateurs ou les utilisatrices dans le cas d’une demande relative à la Confidentialité des données est stocké dans une variable personnalisée uniquement lorsque l’utilisateur ou l’utilisatrice se connecte, cette activité de pré-connexion n’est pas associée à l’ID. Avec l’ID de cookie Analytics, les clients peuvent choisir d’associer leur consultation du site avant la connexion à l’achat effectué après la connexion, puisque l’ID de cookie est conservé lors de la connexion.<p>Supposons que votre implémentation stocke un ID de connexion (ID CRM, nom d’utilisateur, numéro de fidélité, adresse e-mail, etc., ou un hachage de l’une de ces valeurs) dans une variable personnalisée (prop ou eVar) ou un identifiant visiteur personnalisé, puis utilise cet ID dans le cas d’une demande d’accès relative à la Confidentialité des données. Le ou la titulaire de données pourrait s’étonner que les informations relatives à sa navigation ne soient pas renvoyées dans le cadre d’une demande d’accès, surtout si vous lui avez présenté des articles consultés, mais pas encore achetés. Le traitement en vertu de la Confidentialité des données d’Analytics prend donc en charge l’extension d’ID, où Analytics trouve tous les ID de cookie qui apparaissent dans le même accès que tout ID personnalisé, puis étend la requête de manière à inclure également ces ID.<p>Lorsque `expandIDs` est spécifié avec un espace de noms autre qu’un espace de noms de cookie, la demande est étendue pour inclure tout ID de cookie (cookie ECID ou Analytics) trouvé dans les accès contenant l’un des ID spécifiés. L’extension d’ID de cookie, comme indiqué ci-dessus, est ensuite effectuée sur tout nouvel ID de cookie trouvé.<p>Quand l’option `expandIDs` est utilisée pour une demande d’accès et que l’ID spécifié comporte un libellé ID-PERSON, deux ensembles de fichiers seront alors renvoyés. Le premier ensemble (l’ensemble « person ») ne contient que des données provenant des accès dans lesquels l’ID spécifié a été trouvé. Le second ensemble (l’ensemble « device ») ne contient que des données provenant des accès des ID étendus, dans lesquels l’ID spécifié était absent. |

{style="table-layout:auto"}

## Quand utiliser l’extension d’ID

Au cours des premiers mois suivant l’entrée en vigueur de la confidentialité des données, la grande majorité des demandes relatives à la confidentialité des données Analytics n’ont pas requis d’extension d’ID. Cependant, il vous appartient de déterminer la valeur appropriée pour votre organisation. Consultez votre équipe juridique pour savoir si l’extension d’ID est requise pour vos données avec les ID que vous utilisez et les données que vous collectez dans Adobe Analytics.

Vous devez principalement prendre en compte le fait que sur un appareil partagé, depuis lequel plusieurs utilisateurs ou utiliatrices ont consulté votre site, l’utilisation d’extension d’ID inclut des données provenant d’autres utilisateurs ou utilisatrices de l’appareil dans les données renvoyées par les demandes d’accès (dans le fichier de l’appareil). Même si vous avez suivi les bonnes pratiques en matière d’étiquetage, par exemple, en excluant les données personnelles du fichier de l’appareil, telles que les pages visitées, ce dernier contiendra le nombre de pages visitées et l’heure associée à chacune de ces visites. Vous vous posez peut-être la question suivante : est-il acceptable de partager ces informations avec une personne qui n&#39;est peut-être pas le visiteur ou la visiteuse ?

Lorsque l’extension d’ID n’est *pas* utilisée pour une demande de suppression : si vous utilisez un ID sans cookie (tout ID autre que le cookie ECID ou Analytics) pour identifier les accès à supprimer et que cet ID possède un libellé ID-DEVICE, alors le nombre de visiteurs ou visiteuses uniques dans les rapports change. En effet, seules certaines instances des ID de cookie seront rendues anonymes, tandis que d’autres resteront inchangées. Si vous ne spécifiez aucune extension d’ID, il est recommandé d’utiliser soit un ID de cookie pour les requêtes, soit des ID possédant un libellé ID-PERSON.

Lorsqu’Adobe effectue une extension d’ID, elle peut nécessiter une analyse complète supplémentaire des données. Cela augmente le temps nécessaire à Adobe pour terminer la demander, ce qui a souvent pour effet d’ajouter une semaine au temps de traitement.

## Autres indicateurs de demandes relatives à la confidentialité des données

En plus de l’indicateur « expandIDs », Analytics prend en charge deux autres indicateurs qui peuvent être transmis dans le cadre d’une demande relative à la Confidentialité des données. Ces indicateurs avec leurs valeurs par défaut sont :

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

À l’avenir, la méthode `analyticsDeleteMethod` pourra prendre en charge une valeur « purge » en plus de la valeur par défaut « anonymize ». Lorsqu’elle est prise en charge, elle entraîne la suppression de l’accès complet plutôt que la simple mise à jour des valeurs des champs d’accès qui ont des libellés DEL.

En plus de sa valeur par défaut, le champ `priority` prend également en charge une valeur « low ». Vous devez spécifier cette valeur pour les demandes qui ne font pas suite à une demande du ou de la titulaire des données et qui ne sont donc pas soumises à une obligation légale de traitement dans un certain délai.

## Utilisations de l’API Privacy Service

>[!IMPORTANT]
>
>Adobe ne permet pas l’utilisation de l’[API Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=fr) pour des raisons autres que des demandes valides initiées par le ou la titulaire de données. L’API Privacy Service n’est pas un outil approprié pour le nettoyage ou la réparation des données. Toute utilisation abusive de l’API Privacy Service pour des demandes non initiées par un ou une titulaire de données aura des conséquences inattendues. L’API Privacy Service est fournie aux clients et clientes Adobe pour vous aider à répondre aux demandes urgentes relatives à la Confidentialité des données. L’utilisation de cette API à d’autres fins n’est pas prise en charge par Adobe et peut avoir une incidence sur la capacité d’Adobe à traiter en temps voulu des requêtes relatives à la Confidentialité des données pour d’autres clientes et clients d’Adobe. Nous vous demandons de ne pas utiliser l’API Privacy Service à d’autres fins, par exemple pour l’hygiène des données ou effacer des données qui ont été soumises accidentellement à de grands groupes de visiteurs et visiteuses.

Vous devez également savoir que tout visiteur ayant un accès supprimé (mis à jour ou rendu anonyme) à la suite d’une demande de suppression relative à la Confidentialité des données verra ses informations publiques réinitialisées. La prochaine fois que le visiteur reviendra sur votre site Web, il sera considéré comme un nouveau visiteur. Toutes les attributions d’eVar seront réinitialisées, tout comme les informations telles que le nombre de visites, les référents, la première page visitée, etc. Le résultat n’est pas souhaitable dans les situations où vous voulez effacer des champs de données et met en évidence une des raisons pour lesquelles l’API Privacy Service ne convient pas à cet usage.

Veuillez contacter votre équipe de compte d’Adobe pour la coordination avec notre équipe de conseillers en architecture d’ingénierie afin d’effectuer une révision plus approfondie et de fournir le niveau d’effort nécessaire pour supprimer les informations d’identification personnelles ou résoudre les problèmes de données.
