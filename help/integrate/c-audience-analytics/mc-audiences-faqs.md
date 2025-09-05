---
description: Réponses aux questions pouvant survenir lors de la mise en œuvre d’Audience Analytics.
solution: Experience Cloud
title: Questions fréquentes sur Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 30%

---

# Questions fréquentes

Réponses aux questions pouvant survenir lors de la mise en œuvre d’Audience Analytics.

## Questions fréquentes d’ordre juridique {#legal}

+++ Comment savoir si mes données Analytics contiennent des informations d’identification personnelle (PII) ? Et si oui, qu&#39;est-ce que je fais ?

Si vous disposez d’e-mails/adresses/etc. dans une prop ou une eVar, envisagez de hacher les données lors de la collecte. Si votre pays considère les adresses IP comme des informations d’identification personnelles, [activez l’obscurcissement d’adresses IP](/help/admin/tools/exclude-ip.md). Contactez votre administrateur Analytics pour voir ce que vous collectez. Parlez à votre service juridique pour savoir ce qu’il considère comme des PII.

+++

+++ Comment savoir si mes suites de rapports effectuent une personnalisation sur site ou un ciblage hors site/sur site ?

Elles ne s’appliquent pas à l’envoi de données Adobe Analytics à Adobe Audience Manager. Demandez-vous :

* Partagerez-vous un segment partagé avec Analytics avec une dimension MCA avec Experience Cloud ?

* Effectuez-vous une exportation (par exemple via le flux de données) vers un système Business Intelligence (BI) exploité dans ce but ?

+++

## Questions fréquentes spécifiques à Adobe Audience Manager {#aam-specific}

+++ Comment créer une destination Analytics dans Audience Manager ?

Voir [ Configuration d’une destination Analytics dans Adobe Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=fr) ».

+++

+++ Après la création et l’enregistrement d’une destination Analytics, combien de temps faut-il pour que les données apparaissent dans mes suites de rapports sélectionnées ?

Plusieurs heures peuvent s’écouler avant que les nouvelles données n’apparaissent dans vos suites de rapports.

+++

+++ J’ai créé une nouvelle destination Analytics, mais je ne la vois pas dans la section Mappages de destination de mes segments disponibles. Où est passée cette destination ou comment l&#39;ai-je trouvée ?

Une destination Analytics disparaît de la section Mappages de destination d’un segment lorsque vous sélectionnez l’option **[!UICONTROL Mapper automatiquement tous les segments actuels et futurs]** dans **[!UICONTROL Mappages de segments]**. Pour éviter ceci, sélectionnez **[!UICONTROL Mapper les segments manuellement]** au lieu de l’option de mappage automatique.

+++

Cela me donnera-t-il toutes les informations de Adobe Audience Manager, dans Analytics ?

Non, seules les données relatives aux personnes qui consultent votre site pendant ou après l’activation d’audiences Audience Manager et pendant/après la qualification de segment sont incluses.

+++

+++ Cela me donnera-t-il une audience adressable totale par segment ?

Pas exactement. Elles vous indiquent le nombre de personnes de ce segment qui ont visité votre site pendant ou après la qualification de segment.

+++

+++ En quoi cela diffère-t-il de la destination des cookies hérités à Analytics ?

Les segments sont qualifiés pour et renvoyés en temps réel, sur le même accès. Les noms conviviaux sont affichés automatiquement.

+++

+++ Que se passe-t-il si certaines de mes suites de rapports contiennent des données personnelles et d’autres non ?&lt;

Conseil : créez deux destinations. Ajoutez les suites de rapports contenant des données personnelles à l’une des destinations et celles n’en contenant pas à l’autre destination.

+++

## Questions fréquentes spécifiques à Analytics  {#aa-specific}

+++ Cette intégration apparaîtra-t-elle en tant que dimension ou segment dans Analytics ?

En tant que dimensions : Identifiant des audiences et Nom des audiences.

+++

+++Où puis-je utiliser ces dimensions dans Analytics ?

Partout ; elles sont traitées comme n’importe quelle autre dimension collectée dans Analytics.

+++

+++ Pourquoi est-ce que je ne vois pas les données qui arrivent dans Analytics ?

Les contrôles de confidentialité de Adobe Audience Manager entre la source de données et la destination sont probablement conflictuels.

+++

+++ Pourquoi certains de mes segments sont-ils manquants dans Analytics, même si j’ai choisi d’envoyer tous les segments ?&lt;

* Vos contrôles d’exportation de données Adobe Audience Manager sur la destination et dans les sources de données des segments peuvent être en conflit, empêchant l’envoi de certains segments.

* Si vous utilisez des caractéristiques de données tierces dans vos segments, ces segments ne peuvent pas être partagés avec des destinations (un jeu de suites de rapports) contenant des données personnelles.

+++

+++ Pourquoi est-ce que je vois « Limite d’audience atteinte » dans mon rapport Analytics ? (Remarque : ceci sera également représenté sous la forme ID d’audience = -1 et `::max_audiences_exceeded::` dans Data Warehouse)

Par défaut, l’intégration d’Audience Analytics pour Adobe Audience Manager envoie à Analytics tous les segments pour lesquels un visiteur est qualifié, par accès. Si un visiteur appartient à plus de 150 segments Adobe Audience Manager sur un seul accès, les 150 segments qualifiés les plus récemment **** sont envoyés à Analytics, tandis que la liste restante est tronquée. Un indicateur supplémentaire signifiant que la liste de segments a été tronquée est envoyé à Analytics. Celui-ci s’affiche sous la forme de la mention « Limite d’audience atteinte » dans la dimension Nom d’audience et de « -1 » dans la dimension ID d’audience.

Il est peu probable qu’un visiteur soit admissible pour plus de 150 segments au cours d’un accès particulier, mais cela peut se produire dans un nombre réduit de cas. Si la mention « Limite d’audience atteinte » apparaît dans vos rapports, vous avez deux possibilités :

* Option 1 : continuez à laisser l’intégration fonctionner dans son état prêt à l’emploi, en envoyant les 150 segments qualifiés les plus récemment pour un visiteur particulier.

* Option 2 : dans Adobe Audience Manager, choisissez les 150 segments qui comptent le plus pour votre entreprise pour l’intégration. Adobe Audience Manager ne vérifie ensuite que les visiteurs et visiteuses par rapport à ces 150 segments. Cette approche présente l’inconvénient que vous recevez uniquement ces 150 segments pour tous les visiteurs. En revanche, l’approche de l’option 1 peut fournir un nombre illimité de segments du fait que l’intégration repose sur les accès.

+++

+++ D’autres appels au serveur seront-ils facturés à Analytics pour cette intégration ?

Non. Les audiences Adobe Audience Manager sont intégrées à l’accès Analytics côté serveur. Cela ne génère aucun appel (primaire ou secondaire) au serveur supplémentaire vers Analytics.

+++

## Questions fréquentes sur la redirection côté serveur  {#SSF}

+++ Si l’ancien fichier SSF est implémenté, dois-je également accéder à l’administration Analytics et activer le fichier SSF de la suite de rapports ?

Oui. Dans la configuration de la destination Adobe Audience Manager, seules les suites de rapports pour lesquelles SSF est activé s’affichent.

+++

+++ Pourquoi ne puis-je pas activer certaines suites de rapports pour SSF dans Analytics Admin ?

La redirection côté serveur peut être activée uniquement pour les suites de rapports qui sont mappées sur votre organisation Experience Cloud.

Pour plus de questions fréquentes sur ce sujet, consultez la [FAQ sur la redirection côté serveur](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md).

+++

## Questions fréquentes d’ordre général {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Pourquoi le nombre de visiteurs du segment est-il différent entre Audience Manager et Analytics ?

Voir [ Différences entre les nombres de visiteurs ](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ Quelle est la différence entre « audiences » dans Adobe Audience Manager et « segments » dans Analytics ?

Voir [Présentation des segments dans Analytics et Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md). Les audiences Adobe Audience Manager sont envoyées et partagées en tant que composants de « dimension » à utiliser dans Analytics. Elles ne s’affichent pas sous la forme de segments dans le créateur de segments, par exemple, mais sous la forme de dimensions avec lesquelles vous pouvez créer des segments.

+++

+++ Quelle est la différence entre les attributs du client et les données client intégrées à partir de Adobe Audience Manager ?

Les attributs du client ne sont pas basés sur le temps ; ils s’appliquent rétroactivement et vont de l’avant. Les données intégrées de Adobe Audience Manager sont uniquement basées sur le temps et ne sont pas progressives. En outre, les attributs du client sont une table de recherche des ID de visiteur Experience Cloud, tandis que l’intégration de Adobe Audience Manager regroupe des données pour chaque accès d’un visiteur.

+++

+++ Qu’en est-il des approches héritées de ce problème, par exemple les anciennes destinations Beta ou les destinations de cookie du plug-in Consulting ?

Il est recommandé de mettre en œuvre la nouvelle intégration et de supprimer les autres destinations.

+++
