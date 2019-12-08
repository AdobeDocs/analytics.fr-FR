---
description: Déployez Adobe Analytics à l’aide de Dynamic Tag Management en créant l’outil Adobe Analytics et en configurant le code de page automatiquement ou manuellement. La méthode automatique est recommandée pour la plupart des utilisateurs.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
title: Ajout de l’outil Adobe Analytics
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ajout de l’outil Adobe Analytics

Déployez Adobe Analytics à l’aide de Dynamic Tag Management en créant l’outil Adobe Analytics et en configurant le code de page automatiquement ou manuellement. La méthode automatique est recommandée pour la plupart des utilisateurs.

> [!NOTE] Pour améliorer le suivi des visiteurs, nous vous recommandons vivement d’activer le service [d’identité](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Ajout d’un outil Adobe Analytics {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Cliquez sur **[!UICONTROL *`Web Property Name`*]** &gt; **[!UICONTROL Aperçu]** &gt; **[!UICONTROL Ajouter un outil]** &gt; **[!UICONTROL Adobe Analytics]**.

   ![](assets/dtm-add-analytics-tool.png)

1. Renseignez les champs suivants :

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Type d’outil </p> </td> 
   <td colname="col2">Le type d’outil, par exemple <span class="keyword">Adobe Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de l’outil </p> </td> 
   <td colname="col2">Nom explicite de cet outil. Ce nom apparaît dans la section <span class="wintitle">Outils installés</span> de l’onglet <span class="wintitle">Aperçu</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Méthode de configuration </p> </td> 
   <td colname="col2"> <p> <b>Automatique</b> (recommandé) : utilisez Dynamic Tag Management pour gérer la configuration. Cette méthode active la synchronisation automatique des suites de rapports <span class="keyword">Adobe Analytics</span> par l’intermédiaire d’un identifiant de connexion à <span class="keyword">Experience Cloud</span> ou d’un identifiant à des services web, et gère le code AppMeasurement. </p> <p>Une fois les comptes connectés, Dynamic Tag Management exporte les identifiants et noms des suites de rapports <span class="keyword">Adobe Analytics</span> dans l’interface de configuration de l’outil, permettant une vitesse accrue de déploiement de l’outil avec moins de risques d’erreurs de l’utilisateur. </p> <p> <p>Remarque : Vous devez choisir l’option <span class="wintitle">Automatique</span> si vous êtes un client <span class="keyword">Adobe Analytics Premium.</span> </p> </p> <p>Renseignez les champs spécifiques à la configuration automatique : </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b> : (valeur par défaut) utilise la connexion unique de <span class="keyword">Experience Cloud</span>. Indiquez votre Experience Cloud ID et votre mot de passe. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Services web</b> : indiquez le nom d’utilisateur et le secret partagé. </p> <p>Shared secret credentials are located in <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Company Settings</span> &gt; <a href="https://docs.adobe.com/content/help/en/analytics/admin/company-settings/web-services-admin.html"> Web Services</a>. </p> <p>Développeurs, voir <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api">Obtention de l’accès aux services web pour l’API d’entreprise</a> pour de l’aide sur l’obtention des informations d’identification des services web. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manuel</b> : permet de gérer le code AppMeasurement manuellement. Vous pouvez télécharger le code <span class="keyword">Analytics</span> <span class="keyword">AppMeasurement</span> depuis <span class="ignoretag"><span class="uicontrol">Outils d’administration</span> &gt; <span class="uicontrol">Gestionnaire de code</span></span>. </p> <p>Cliquez sur <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html">JavaScript (nouveau)</a> pour obtenir des informations sur le téléchargement du code en local afin de le copier et le coller dans le champ <span class="wintitle">Modifier le code</span> de <a href="/help/implement/c-implement-with-dtm/c-aa-tool/library-management.md">Gestion des bibliothèques</a>. </p> <p>Renseignez les champs spécifiques à une configuration manuelle : </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>ID du compte de production :</b> (obligatoire) compte de production pour la collecte des données. Pour Analytics, il s’agit de votre identifiant de suite de rapports. Dynamic Tag Management installe automatiquement le compte correct dans l’environnement de production et d’évaluation. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID du compte d’évaluation :</b> (obligatoire) utilisé dans l’environnement de développement ou de test. Pour Analytics, il s’agit de votre identifiant de suite de rapports. Un compte d’évaluation permet de séparer les données de test de la production. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Serveur de suivi  :</b> indiquez les informations relatives au serveur de suivi  </p> <p>Les variables <span class="wintitle">Serveur de suivi</span> et <span class="wintitle">Serveur de suivi SSL</span> sont utilisées pour l’implémentation des cookies propriétaires afin de spécifier le domaine sur lequel la demande d’image et le cookie sont écrits. Pour plus d’informations, voir l’article <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html">Définition correcte des variables trackingServer et trackingServerSecure</a>. </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>Serveur de suivi SSL :</b> indiquez les informations relatives au serveur de suivi SSL. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Cliquez sur **[!UICONTROL Créer l’outil]** pour créer l’outil et l’afficher en vue de sa modification.

   Les outils s’affichent dans l’onglet [!UICONTROL Aperçu] sous [!UICONTROL Outils installés].

1. (Conditionnel) Configurez l’outil selon les besoins en suivant les instructions des sections suivantes ([!UICONTROL Général], [!UICONTROL Gestion des bibliothèques], [!UICONTROL Variables globales], [!UICONTROL Pages vues et contenu], [!UICONTROL Suivi de liens], [!UICONTROL Référents et campagnes], [!UICONTROL Cookies] et [!UICONTROL Personnaliser le code de page]).

Reportez-vous à la section [FAQ à propos de l’outil Adobe Analytics](/help/implement/faq.md) pour obtenir davantage d’informations sur cet outil.

## Modification d’un outil Adobe Analytics existant {#section_148B16AF429B4949B06238D90635B726}

Vous pouvez modifier un outil Adobe Analytics existant afin de changer ses paramètres de configuration.

1. Cliquez sur l’icône ![](assets/settings_gear.png) située en regard d’un outil installé dans l’onglet [!UICONTROL Aperçu].
1. Modifiez les champs selon vos besoins.

   Le tableau ci-après comprend uniquement les éléments différents de ceux qui sont disponibles lors de la création d’un outil Analytics, comme il est indiqué plus haut. Vous pouvez toutefois modifier n’importe quel élément sur la page, comme il est indiqué dans les deux tableaux.

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Activer la configuration automatique </p> </td> 
   <td colname="col2"> <p>Remarque : L’activation de ce paramètre modifie une implémentation configurée manuellement en la méthode de configuration automatique décrite dans <span class="term">Méthode de configuration</span>. </p> <p>Cette option permet à Dynamic Tag Management de récupérer automatiquement la configuration de votre compte <span class="keyword">Adobe Analytics</span>. </p> <p>Le code AppMeasurement le plus récent est utilisé et des notifications de mise à niveau s’affichent pour sélection lorsque de nouvelles versions deviennent disponibles. Vous pouvez également restaurer les versions antérieures d’AppMeasurement, le cas échéant, par exemple pour des raisons de compatibilité. Un maximum de cinq versions antérieures s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mettre à jour les informations d’identification </p> </td> 
   <td colname="col2"> <p>Actualisez l’API, par exemple pour mettre à jour des suites de rapports associées à un utilisateur. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Conditionnel) Configurez l’outil selon les besoins en suivant les instructions des sections suivantes ([!UICONTROL Général], [!UICONTROL Gestion des bibliothèques], [!UICONTROL Variables globales], [!UICONTROL Pages vues et contenu], [!UICONTROL Suivi de liens], [!UICONTROL Référents et campagnes], [!UICONTROL Cookies] et [!UICONTROL Personnaliser le code de page]).
1. Cliquez sur **[!UICONTROL Enregistrer les modifications]**.
