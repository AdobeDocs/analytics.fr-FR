---
description: Réponses aux questions pouvant survenir lors de la mise en œuvre d’Audience Analytics.
solution: Experience Cloud
title: Questions fréquentes à Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: 750c4b0ffb52c3f2cf25abcd76ef149a4521109e
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 30%

---

# Questions fréquentes

Réponses aux questions pouvant survenir lors de la mise en œuvre d’Audience Analytics.

## Questions fréquentes d’ordre juridique {#legal}

+++ Comment savoir si des informations d’identification personnelle figurent dans mes données Analytics ? Et si oui, que dois-je faire à ce sujet ?

Si vous avez des emails/adresses/etc dans une prop ou un eVar, envisagez de hacher les données lors de la collecte. Si votre pays considère que l’adresse IP est une donnée personnelle personnelle, [activation de l’obscurcissement des adresses IP](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html?lang=fr). Contactez votre administrateur Analytics pour voir ce que vous collectez. Contactez votre service juridique pour savoir ce qu’il considère comme des informations d’identification personnelles.

+++

+++ Comment savoir si mes suites de rapports effectuent une personnalisation sur site ou un ciblage sur site/hors site ?

Elles ne s’appliquent pas à l’envoi de données Adobe Analytics vers Adobe Audience Manager. Demandez-vous :

* Partagez-vous un segment partagé Analytics avec une dimension MCA vers l’Experience Cloud ?

* Effectuez-vous une exportation (par exemple via le flux de données) vers un système Business Intelligence (BI) exploité dans ce but ?

+++

## Questions fréquentes spécifiques à Adobe Audience Manager {#aam-specific}

+++ Comment créer une destination Analytics en Audience Manager ?

Voir [Configuration d’une destination Analytics dans Adobe Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=fr)&quot;.

+++

+++ Après avoir créé et enregistré une destination Analytics, combien de temps faut-il pour que les données apparaissent dans mes suites de rapports sélectionnées ?

Plusieurs heures peuvent s’écouler avant que les nouvelles données n’apparaissent dans vos suites de rapports.

+++

+++ J’ai créé une destination Analytics, mais je ne la vois pas dans la section Mappages des destinations de mes segments disponibles. Où cette destination est-elle allée ou comment la trouver ?

Une destination Analytics disparaît de la section Mises en correspondance de destinations d’un segment lorsque vous sélectionnez la variable **[!UICONTROL Mappage automatique de tous les segments actuels et futurs]** dans **[!UICONTROL Mappages de segments]**. Pour éviter ceci, sélectionnez **[!UICONTROL Mapper les segments manuellement]** au lieu de l’option de mappage automatique.

+++

Toutes les informations de Adobe Audience Manager seront-elles alors disponibles dans Analytics ?

Non, seules les données relatives aux personnes qui consultent votre site pendant ou après l’activation d’audiences Audience Manager et pendant/après la qualification des segments sont incluses.

+++

+++ Cela me donnera-t-il une audience adressable totale par segment ?

Pas exactement. Elles vous indiquent le nombre de visiteurs de ce segment qui ont visité votre site pendant ou après la qualification du segment.

+++

+++ En quoi cette fonctionnalité diffère-t-elle de la destination des cookies hérités dans Analytics ?

Les segments sont qualifiés et renvoyés en temps réel au cours du même accès. Les noms conviviaux sont affichés automatiquement.

+++

+++ Que se passe-t-il si certaines de mes suites de rapports contiennent des données personnelles et d’autres pas ?&lt;

Conseil : créez deux destinations. Ajoutez les suites de rapports contenant des données personnelles à l’une des destinations et celles n’en contenant pas à l’autre destination.

+++

## Questions fréquentes spécifiques à Analytics  {#aa-specific}

+++ Cette intégration apparaîtra-t-elle en tant que dimension ou segment dans Analytics ?

En tant que dimensions : ID d’audience et Nom d’audience.

+++

+++Où puis-je utiliser ces dimensions dans Analytics ?

Partout, ils sont traités comme toute autre dimension collectée dans Analytics.

+++

+++ Pourquoi les données ne sont-elles pas visibles dans Analytics ?

Il existe probablement un conflit entre les contrôles de confidentialité de Adobe Audience Manager entre la source de données et la destination.

+++

+++ Pourquoi certains de mes segments sont-ils manquants dans Analytics, même si j’ai choisi d’envoyer tous les segments ?&lt;

* Les contrôles de l’exportation des données Adobe Audience Manager sur la destination et dans les sources de données des segments peuvent être contradictoires, ce qui empêche l’envoi de certains segments.

* Si vous utilisez des caractéristiques de données tierces dans vos segments, ces segments ne peuvent pas être partagés avec des destinations (un jeu de suites de rapports) contenant des données personnelles.

+++

+++ Pourquoi la mention &quot;Limite d’audience atteinte&quot; s’affiche-t-elle dans mon rapport Analytics ? (Remarque : ceci sera également représenté sous la forme ID d’audience = -1 et `::max_audiences_exceeded::` en Data Warehouse)

Par défaut, l’intégration d’Audience Analytics pour Adobe Audience Manager envoie à Analytics tous les segments pour lesquels un visiteur est admissible, par accès. Si un visiteur appartient à plus de 150 segments Adobe Audience Manager sur un seul accès, la variable **150 segments les plus récemment qualifiés** sont envoyées à Analytics, tandis que la liste restante est tronquée. Un indicateur supplémentaire signifiant que la liste de segments a été tronquée est envoyé à Analytics. Celui-ci s’affiche sous la forme de la mention « Limite d’audience atteinte » dans la dimension Nom d’audience et de « -1 » dans la dimension ID d’audience.

Il est peu probable qu’un visiteur soit admissible pour plus de 150 segments au cours d’un accès particulier, mais cela peut se produire dans un nombre réduit de cas. Si la mention « Limite d’audience atteinte » apparaît dans vos rapports, vous avez deux possibilités :

* Option 1 : Continuez à laisser l’intégration fonctionner dans son état d’usine, en envoyant les 150 segments les plus récemment qualifiés pour un visiteur particulier.

* Option 2 : dans Adobe Audience Manager, sélectionnez les 150 segments qui comptent le plus pour votre entreprise pour l’intégration. Adobe Audience Manager vérifie ensuite les visiteurs par rapport à ces 150 segments seulement. Cette approche présente l’inconvénient que vous recevez uniquement ces 150 segments pour tous les visiteurs. En revanche, l’approche de l’option 1 peut fournir un nombre illimité de segments du fait que l’intégration repose sur les accès.

+++

+++ Des appels au serveur supplémentaires seront-ils facturés à Analytics pour cette intégration ?

Non. Les audiences Adobe Audience Manager sont intégrées dans l’accès Analytics côté serveur. Cela ne génère aucun appel (primaire ou secondaire) au serveur supplémentaire vers Analytics.

+++

## Questions fréquentes sur la redirection côté serveur  {#SSF}

+++ Si la redirection côté serveur héritée est mise en oeuvre, dois-je également accéder à l’administrateur Analytics et activer la redirection côté serveur pour les suites de rapports ?

Oui. Dans la configuration des destinations Adobe Audience Manager, seules les suites de rapports pour lesquelles la redirection côté serveur est activée sont visibles.

+++

+++ Pourquoi ne puis-je pas activer la redirection côté serveur pour certaines suites de rapports dans Analytics Admin ?

La redirection côté serveur peut être activée uniquement pour les suites de rapports qui sont mappées sur votre organisation Experience Cloud.

Pour plus de questions fréquentes sur ce sujet, consultez la [FAQ sur la redirection côté serveur](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md).

+++

## Questions fréquentes d’ordre général {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Pourquoi les nombres de visiteurs de segments diffèrent-ils entre Audience Manager et Analytics ?

Voir [Différences entre les nombres de visiteurs](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ Quelle est la différence entre &quot;audiences&quot; dans Adobe Audience Manager et &quot;segments&quot; dans Analytics ?

Voir [Présentation des segments dans Analytics et Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md). Les audiences Adobe Audience Manager sont envoyées et partagées en tant que composants de &quot;dimension&quot; à utiliser dans Analytics. Elles ne s’affichent pas en tant que segments dans le créateur de segments, mais en tant que dimensions avec lesquelles vous pouvez créer des segments.

+++

+++ Quelle est la différence entre les attributs du client et les données client intégrées à partir de Adobe Audience Manager ?

Les attributs du client ne sont pas basés sur le temps ; ils s’appliquent rétroactivement et continuent. Les données intégrées à Adobe Audience Manager reposent uniquement sur le temps et ne sont disponibles qu’à l’avenir. En outre, les attributs du client sont un tableau de recherche pour les identifiants visiteur Experience Cloud, tandis que l’intégration Adobe Audience Manager est une combinaison de données pour chaque accès pour un visiteur.

+++

+++ Qu’en est-il des approches héritées en la matière, par exemple, l’ancienne version bêta ou la consultation des destinations de cookie de module externe ?

Il est recommandé de mettre en œuvre la nouvelle intégration et de supprimer les autres destinations.

+++
