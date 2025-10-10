---
title: Migration de l’extension de balise Adobe Analytics vers l’extension de balise Web SDK
description: Mettez à jour votre implémentation Analytics sur les balises de la collecte de données Adobe Experience Platform pour utiliser l’extension Web SDK.
exl-id: 691c29ca-d169-4ef8-9f91-d0375166796d
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1706'
ht-degree: 6%

---

# Migration de l’extension de balise Adobe Analytics vers l’extension de balise Web SDK

Ce chemin d’implémentation implique une approche de migration méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise Web SDK. D’autres chemins d’implémentation sont abordés sur des pages distinctes :

* [Bibliothèque JavaScript AppMeasurement vers Web SDK &#x200B;](appmeasurement-to-web-sdk.md) : approche fluide et méthodique de la migration vers Web SDK, sauf qu’elle n’utilise pas de balises. Au lieu de cela, vous supprimez manuellement la bibliothèque de collecte de données Adobe Analytics (`AppMeasurement.js`) et la remplacez par la bibliothèque JavaScript Web SDK (`alloy.js`).
* [Extension de balise Web SDK](web-sdk-tag-extension.md) : nouvelle installation de Web SDK dans laquelle vous gérez l’implémentation à l’aide de balises dans la collecte de données Adobe Experience Platform. Le groupe de champs Adobe Analytics ExperienceEvent, qui comprend des variables Analytics standard à inclure dans votre schéma XDM, est nécessaire.
* [Bibliothèque Web SDK JavaScript](web-sdk-javascript-library.md) : nouvelle installation de Web SDK à l’aide de la bibliothèque Web SDK JavaScript (`alloy.js`). Gérez la mise en œuvre vous-même au lieu d’utiliser l’interface utilisateur des balises. Le groupe de champs Adobe Analytics ExperienceEvent, qui comprend des variables Analytics standard à inclure dans votre schéma XDM, est nécessaire.

## Avantages et inconvénients de ce chemin de mise en œuvre

L’utilisation de cette approche de migration présente à la fois des avantages et des inconvénients. Évaluez soigneusement chaque option pour décider quelle approche est la meilleure pour votre organisation.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Aucune modification de code sur votre site** : puisque des balises sont déjà installées dans votre implémentation, toutes les mises à jour de migration peuvent être effectuées dans l’interface des balises.</li><li>**Utilise votre implémentation existante** : cette approche ne nécessite pas de nouvelle implémentation. Bien qu’il nécessite de nouvelles actions de règle, vous pouvez réutiliser vos éléments de données et conditions de règle existants avec un minimum de modifications.</li><li>**Ne nécessite pas de schéma** : pour cette étape de la migration vers le Web SDK, vous n’avez pas besoin de schéma XDM. Vous pouvez plutôt renseigner l’objet `data` , qui envoie directement les données à Adobe Analytics. Une fois la migration vers Web SDK terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage des flux de données pour renseigner les champs XDM applicables. Si un schéma était requis à cette étape du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM Adobe Analytics. L’utilisation de ce schéma rend plus difficile, pour votre organisation, l’utilisation de votre propre schéma à l’avenir.</li></ul> | <ul><li>**Dette technique d’implémentation** : étant donné que cette approche utilise une forme modifiée de votre implémentation existante, il peut être plus difficile de suivre la logique d’implémentation et d’effectuer des modifications si nécessaire. Le code personnalisé peut être particulièrement difficile à déboguer.</li><li>**Nécessite un mappage pour l’envoi de données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet `data` soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui évite toute modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez déjà d’une implémentation utilisant l’extension de balise Adobe Analytics. Si vous disposez d’une implémentation utilisant AppMeasurement, suivez [Migration d’AppMeasurement vers le SDK Web](appmeasurement-to-web-sdk.md) à la place.
* Vous avez l’intention d’utiliser Customer Journey Analytics à l’avenir, mais vous ne souhaitez pas remplacer votre implémentation Analytics par une implémentation de SDK Web à partir de zéro. Le remplacement de votre implémentation à partir de zéro sur le Web SDK nécessite le plus d’efforts, mais offre également l’architecture d’implémentation à long terme la plus viable. Si votre entreprise est prête à passer par une implémentation propre de Web SDK, consultez [Ingestion de données via le SDK web Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) dans le guide d’utilisation de Customer Journey Analytics.

## Étapes requises pour migrer vers Web SDK

Les étapes suivantes contiennent des objectifs concrets à atteindre. Cliquez sur chaque étape pour obtenir des instructions détaillées sur la manière de procéder.

+++**1. Créer et configurer un flux de données**

Créez un flux de données dans la collecte de données Adobe Experience Platform. Lorsque vous envoyez des données à ce flux de données, il transfère les données vers Adobe Analytics. À l’avenir, ce même flux de données transfèrera des données à Customer Journey Analytics.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Collecte de données]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Flux de données]**.
1. Sélectionnez **[!UICONTROL Nouveau flux de données]**.
1. Saisissez le nom souhaité, puis sélectionnez **[!UICONTROL Enregistrer]**.
1. Une fois le flux de données créé, sélectionnez **[!UICONTROL Ajouter un service]**.
1. Dans le menu déroulant Service, sélectionnez **[!UICONTROL Adobe Analytics]**.
1. Saisissez le même identifiant de suite de rapports que le site auquel vous envoyez actuellement des données d’analyse. Cliquez sur **[!UICONTROL Enregistrer]**.

![Ajouter un service Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à Adobe Analytics.

+++

+++**2. Ajoutez l’extension Web SDK à la propriété de balise**

Cette section prépare votre balise pour l’essentiel de la migration effectuée à l’étape suivante.

1. Cliquez sur l’icône hamburger en haut à gauche de l’interface de Adobe Experience Platform, puis sélectionnez **[!UICONTROL Balises]**.
1. Sélectionnez la propriété de balise de votre choix.
1. Dans le volet de navigation de gauche de la propriété de balise, sélectionnez **[!UICONTROL Extensions]**.
1. Sélectionnez **[!UICONTROL Catalogue]** en haut pour afficher la liste de toutes les extensions disponibles.
1. Recherchez et sélectionnez l’extension **[!UICONTROL Adobe Experience Platform Web SDK]**, puis cliquez sur **[!UICONTROL Installer]** à droite.

   ![Catalogue](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Les paramètres de configuration de l’extension s’affichent. Recherchez la section Flux de données et sélectionnez le flux de données que vous avez créé à l’étape précédente.

   ![Sélection du flux de données](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Sélectionnez **[!UICONTROL Enregistrer]**.

Le SDK Web est désormais installé sur la propriété de balise.

+++

+++**3. Créez un élément de données d’objet de données**

L’élément de données d’objet de données fournit un cadre intuitif pour configurer une payload que le SDK Web utilise pour envoyer à un flux de données. La plupart des règles que vous mettez à jour à l’étape suivante interagissent avec cet élément de données.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Éléments de données]**.
1. Sélectionnez **[!UICONTROL Ajouter un élément de données]**
1. Définissez les paramètres suivants pour l’élément de données :
   * [!UICONTROL Nom] : tout ce que vous souhaitez, tel que « Couche de données » ou « Objet de données ».
   * [!UICONTROL Extension] : [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Type d’élément de données] : [!UICONTROL Variable]
   * Les cases à cocher peuvent rester en l’état
1. Sur la droite, sélectionnez les paramètres suivants :
   * Bouton radio de propriété : [!UICONTROL Data]
   * Solution : [!UICONTROL Adobe Analytics]
1. Sélectionnez **[!UICONTROL Enregistrer]**.

![Créer un élément de données](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Votre propriété de balise dispose désormais de tout ce dont vous avez besoin pour mettre à jour chaque règle.

+++

+++**4. Mettez à jour les règles pour utiliser l’extension Web SDK au lieu de l’extension Analytics**

Cette étape contient l’essentiel de l’effort requis pour migrer vers Web SDK et nécessite des connaissances sur le fonctionnement de votre implémentation. Vous trouverez ci-dessous un exemple de modification d’une règle de balise standard. Mettez à jour toutes les règles de balise dans votre mise en œuvre pour remplacer toutes les références à l’extension Adobe Analytics par l’extension Web SDK.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Règles]**.
1. Sélectionnez une règle à modifier.
1. Sélectionnez l’action **[!UICONTROL Adobe Analytics - Définir les variables]**
1. Notez toutes les variables Analytics définies dans cette règle. Incluez les variables définies dans les menus déroulants et les variables définies dans le code personnalisé.
1. Modifiez la [!UICONTROL Configuration de l’action] pour les paramètres suivants :
   * [!UICONTROL Extension] : [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Type d’action] : Mettre à jour la variable
1. Assurez-vous que votre objet de données est sélectionné dans la liste déroulante de droite.
1. Définissez les variables Analytics sur leurs mêmes valeurs respectives telles qu’elles ont été configurées dans l’extension Analytics.
   * Les variables définies dans l’interface des balises peuvent être traduites directement en valeurs identiques.
   * Les variables de chaîne définies dans le code personnalisé nécessitent des ajustements minimaux. Au lieu d’utiliser l’objet `s`, utilisez `data.__adobe.analytics` à la place. Par exemple, `s.eVar1` se traduirait par `data.__adobe.analytics.eVar1`.
   * Les variables de configuration Analytics et les appels de méthode dans le code personnalisé peuvent nécessiter une logique d’implémentation modifiée. Voir chaque [variable](/help/implement/vars/overview.md) respective pour déterminer comment obtenir son équivalent à l’aide de Web SDK.
1. Une fois toute la logique des règles répliquée à l’aide de l’extension Web SDK, sélectionnez **[!UICONTROL Conserver les modifications]**.
1. Répétez ces étapes pour chaque configuration d’action qui utilise l’extension Adobe Analytics pour définir des valeurs. Cette étape comprend à la fois des variables définies à l’aide de l’interface des balises et des variables définies à l’aide de code personnalisé. Les blocs de code personnalisé ne peuvent pas référencer l’objet `s` où que ce soit.

Les étapes ci-dessus s’appliquent uniquement aux règles qui définissent des valeurs. Les étapes suivantes remplacent toutes les actions qui utilisent l’[!UICONTROL Configuration de l’action] [!UICONTROL Envoyer la balise].

1. Sélectionnez une règle qui envoie une balise.
1. Sélectionnez l’action **[!UICONTROL Adobe Analytics - Envoyer la balise]**.
1. Notez la valeur actuelle du bouton radio [!UICONTROL Tracking] à droite ([`s.t()`](../../vars/functions/t-method.md) ou [`s.tl()`](../../vars/functions/tl-method.md)).
1. Modifiez la [!UICONTROL Configuration de l’action] pour les paramètres suivants :
   * [!UICONTROL Extension] : [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Type d’action] : [!UICONTROL Envoyer l’événement]
1. Sur la droite, modifiez les paramètres d’action comme suit :
   * [!UICONTROL Type] : par `s.t()`, utilisez **[!UICONTROL Pages vues de détails sur la page web]**. Par `s.tl()`, utilisez **[!UICONTROL Clics sur les liens d’interaction web]**. Si vous utilisez [`s.tl()`](../../vars/functions/tl-method.md), vous devez également inclure les champs suivants dans votre objet de données. Ces champs sont répertoriés sous [!UICONTROL Propriétés supplémentaires] lors de l’exécution de la configuration d’action [!UICONTROL Mettre à jour la variable] :
      * [Nom du lien](../../vars/functions/tl-method.md)
      * [Type de lien  &#x200B;](../../vars/functions/tl-method.md)
      * [URL du lien](../../vars/config-vars/linkurl.md)
1. Sélectionnez **[!UICONTROL Conserver les modifications]**.
1. Répétez ces étapes pour chaque configuration d’action qui utilise Adobe Analytics pour envoyer une balise.

+++

+++**5. Publiez les règles mises à jour**

La publication des règles mises à jour suit le même workflow que toute autre modification de votre configuration de balises.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Flux de publication]**.
1. Sélectionnez **[!UICONTROL Ajouter une bibliothèque]**.
1. Attribuez un nom à cette validation de balise, par exemple « Mettre à niveau vers Web SDK ».
1. Sélectionnez **[!UICONTROL Ajouter toutes les ressources modifiées]**.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Le workflow de publication affiche un point orange, indiquant qu’il est en cours de création. Une fois le point vert affiché, vos modifications sont disponibles dans votre environnement de développement.
1. Testez les modifications apportées à votre environnement de développement pour vous assurer que toutes les règles se déclenchent correctement et que l’objet de données est renseigné avec les valeurs attendues.
1. Une fois prête, envoyez la bibliothèque pour approbation, créez-la vers l’évaluation, puis approuvez-la et publiez-la en production.

![Flux de publication](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Désactivez l’extension Analytics**

Une fois que votre implémentation de balise est entièrement sur le Web SDK, vous pouvez désactiver l’extension Adobe Analytics.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Extensions]**.
1. Recherchez et sélectionnez l’extension [!UICONTROL Adobe Analytics]. Sur la droite, sélectionnez **[!UICONTROL Désactiver]**.
1. Suivez le même workflow de publication ci-dessus pour publier la suppression de l’extension [!UICONTROL Adobe Analytics].
1. Une fois l’extension désactivée en production, vous pouvez la désinstaller entièrement. Sélectionnez l’extension, sélectionnez le menu à trois points sur la droite, puis sélectionnez **[!UICONTROL Désinstaller]**.
1. Suivez le même workflow de publication ci-dessus pour publier ces modifications en production.

+++

À ce stade, votre implémentation Analytics se trouve entièrement sur le Web SDK et est correctement préparée pour passer à Customer Journey Analytics à l’avenir.
