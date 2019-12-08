---
description: Si vous êtes un nouvel utilisateur, découvrez ce que vous devez savoir sur la mise en œuvre d’Adobe Analytics.
keywords: Getting Started
subtopic: Analysis Workspace
title: Fenêtre modale de mise en œuvre simplifiée
topic: Reports and analytics
uuid: 6fad2c1f-476c-4985-90df-7c222e751ddc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fenêtre modale de mise en œuvre simplifiée

Si vous êtes un nouvel utilisateur, découvrez ce que vous devez savoir sur la mise en œuvre d’Adobe Analytics.

<!-- 

<p>https://activation.adobedtm.com/index.php?redirected=1 </p>

 -->

Les nouveaux utilisateurs peuvent rapidement créer leur première suite de rapports [!DNL Analytics] (référentiel de données) à l’aide de cette fenêtre modale de configuration *`Getting Started with Adobe Analytics`*. Vous pouvez ensuite déployer le code [!DNL Analytics] à l’aide de [!DNL Dynamic Tag Management].

[!DNL Dynamic Tag Management] permet de gérer la mise en œuvre d’Adobe Analytics sans avoir à apporter des modifications à votre site. Si vous mettez en œuvre une application mobile, vous pouvez vous procurer le kit SDK dont vous avez besoin pour collecter des données précieuses de vos applications.

Cette procédure permet d’effectuer les opérations suivantes :

* Créer votre première [suite de rapports](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html)
* Déployez [!DNL Analytics] et le service [d’](https://marketing.adobe.com/resources/help/en_US/mcvid/)identité.

* Exécuter des rapports sur des données de niveau de page standard.

> [!NOTE] Avant de commencer, vérifiez qu’Analytics est [activé dans Adobe Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html) (le processus d’attribution des privilèges d’accès aux solutions). Si vous avez reçu un message vous invitant à vous connecter à Analytics dans Enterprise Dashboard, cela signifie que vous avez rempli cette condition préalable requise.

**Pour exécuter la fenêtre modale de mise en œuvre simplifiée :**

1. Log in to the [!DNL Adobe Experience Cloud] ( [experiencecloud.adobe.com](https://experiencecloud.adobe.com)).

   Lorsque vous accédez à [!DNL Analytics], le système détermine si vous disposez d’une suite de rapports. Si ce n’est pas le cas, la page [!UICONTROL Prise en main d’Adobe Analytics] s’affiche.

   ![](assets/analytics-implementation-rs-wizard.png)

   Vous pouvez également effectuer cette configuration dans [!DNL Analytics] en cliquant sur **[!UICONTROL Aide]** &gt; **[!UICONTROL Bienvenue dans Adobe Analytics]**.

1. Indiquez les informations de base suivantes relatives à votre entreprise :

   <table id="table_1741878A1B284CB78D297D531DC703D6"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Élément </th> 
       <th colname="col2" class="entry"> Description </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Type de la propriété </p> </td> 
       <td colname="col2"> <p>Votre mise en œuvre est-elle pour le web, le mobile ou les deux ? </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Secteurs d’activité </p> </td> 
       <td colname="col2"> <p>Indiquez quelle est l’activité de votre entreprise (produits, services client, prospects, notoriété des marques et publicités). </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Couche de données </p> </td> 
       <td colname="col2"> <p>(Recommandé) Tableau JavaScript utilisé pour stocker des informations. Si vous effectuez la configuration automatique à l’aide de Dynamic Tag Management, vous utiliserez une couche de données. </p> <p>Pour consulter un blog sur les couches de données, accédez à <a href="https://blogs.adobe.com/digitalmarketing/analytics/data-layers-buzzword-best-practice/"> Data Layer: From Buzzword to Best Practice</a> (en anglais). </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Référentiel de données (suite de rapports) </p> </td> 
       <td colname="col2"> <p> Une <a href="https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html">suite de rapports</a> est un jeu de données distinct qui correspond généralement à une seule propriété (site ou application) ou marque. Chaque suite de rapports possède ses propres ensembles de rapports et de mesures. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Fuseau horaire </p> </td> 
       <td colname="col2"> <p>Le fuseau horaire local : (détecté automatiquement) </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Estimation du nombre de pages vues </p> </td> 
       <td colname="col2"> <p>Nombre de pages vues reçues par votre site par jour. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Devise de base </p> </td> 
       <td colname="col2"> <p>Devise utilisée par votre entreprise. </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Cliquez sur **[!UICONTROL Suivant]**.

   Le système crée une suite de rapports.

1. Pour commencer le déploiement, cliquez sur **[!UICONTROL Suivant]**, puis sur l’une des options suivantes :

   <table id="table_71C7F7B9677346CD8D5130519D32464B"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Élément </th> 
       <th colname="col2" class="entry"> Description </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Déploiement </p> </td> 
       <td colname="col2"> <p> Lance <span class="keyword">Dynamic Tag Management</span> dans laquelle vous pouvez vous connecter et déployer Analytics. Ce processus met automatiquement en œuvre le fichier <span class="filepath"> AppMeasurement.js</span> et le service d’identité (<span class="filepath"> VisitorAPI.js</span>). </p> <p> <p>Important : dans un nouvel onglet de navigateur, une page d’aide vous guide tout au long du déploiement d’<span class="keyword">Adobe Analytics</span> via Dynamic Tag Management. </p> </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Télécharger </p> </td> 
       <td colname="col2"> <p> Télécharge le fichier d’installation appelé <span class="filepath">INSTALL-ME &lt;nom de la suite de rapports&gt;.js</span>. Cette option est destinée aux utilisateurs expérimentés qui comprennent la <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html">mise en œuvre de JavaScript</a>. </p> <p> <p>Important : Le téléchargement du code n’est pas un déploiement d’<span class="keyword">Analytics</span>. Il s’agit d’un déploiement manuel que vous effectuez sur les pages de votre site ou par le bais des services de conseil Adobe. </p> </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Exécution d’un rapport.

   Une fois l’outil Analytics déployé, vous pouvez exécuter un rapport dans les Reports &amp; Analytics pour vérifier que des données arrivent à votre site. (Reportez-vous à la section   [Connexion et navigation](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/analytics-navigation.html) pour vous familiariser avec l’interface d’Analytics.)

   Par exemple, un rapport **[!UICONTROL Mesures du site]** &gt; **[!UICONTROL Temps réel]** permet d’afficher les données immédiates.

   >[!NOTE]
   >
   >Une configuration du rapport en [!UICONTROL temps réel] est nécessaire avant son exécution. Voir [Configuration d’un rapport en temps réel](https://marketing.adobe.com/resources/help/en_US/reference/t_realtime_admin.html).

**Exemple de rapport en temps réel**

![](assets/real-time-report.png)
