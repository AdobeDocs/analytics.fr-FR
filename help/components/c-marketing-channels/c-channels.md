---
description: Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans canaux marketing, une configuration automatique vous permet de créer plusieurs canaux, ainsi que leurs règles. Vous pouvez modifier les canaux prédéfinis en fonction de vos besoins, ou créer vos propres canaux (avec un maximum de 25 canaux).
seo-description: Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans canaux marketing, une configuration automatique vous permet de créer plusieurs canaux, ainsi que leurs règles. Vous pouvez modifier les canaux prédéfinis en fonction de vos besoins, ou créer vos propres canaux (avec un maximum de 25 canaux).
seo-title: Gestion des canaux marketing
solution: Analytics
subtopic: Canaux marketing
title: Gestion des canaux marketing
topic: Reports & Analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Gestion des canaux marketing

Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans canaux marketing, une configuration automatique vous permet de créer plusieurs canaux, ainsi que leurs règles. Vous pouvez modifier les canaux prédéfinis en fonction de vos besoins, ou créer vos propres canaux (avec un maximum de 25 canaux).

Voici quelques consignes concernant la création de canaux :

* Planifiez en dressant la liste de tous vos canaux afin que tous les accès des visiteurs soient classés dans le canal approprié.
* Incluez toujours les catégories d’accès [Interne](/help/components/c-marketing-channels/c-faq.md) et [Direct](/help/components/c-marketing-channels/c-faq.md).

L’ajout de canaux à la page [!UICONTROL Canaux marketing] est indépendant de la création de règles sur la page [Règles de traitement des canaux marketing](/help/components/c-marketing-channels/t-rules.md). Vous associez des règles aux canaux lors de la création de règles.

## Ajout de canaux marketing {#add-mktg-channels}

Ajoutez des canaux marketing dans le Gestionnaire de canaux marketing.

> [!NOTE] Vous ne pouvez pas supprimer un canal. Si vous ne souhaitez pas utiliser un canal, vous pouvez le désactiver ou le renommer, et le conserver pour une utilisation ultérieure.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Sur la page [!UICONTROL Gestionnaire de Report Suites], sélectionnez une suite de rapports.

   Si vous sélectionnez plusieurs suites de rapports, choisissez un modèle à partir duquel copier les paramètres vers les suites de rapports sélectionnées.

   Reportez-vous à la section [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](/help/components/c-marketing-channels/t-template.md).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](/help/components/c-marketing-channels/c-channel-autosetup.md) page displays.

1. Sur la page [!UICONTROL Gestionnaire de canaux marketing]**, cliquez sur[!UICONTROL Ajouter un canal]**.

   Cette option n’est pas disponible lorsque 25 canaux ont été définis.

1. Cliquez sur **[!UICONTROL Enregistrer.]**
1. Pour configurer les règles pour le canal, cliquez sur **[!UICONTROL Règles de traitement des canaux marketing]**.

   See [Create Marketing Channel processing rules](/help/components/c-marketing-channels/t-rules.md).

## Marketing Channel Manager - interface definitions {#mktg-channel-mgr}

Définition des champs de la page [!UICONTROL Gestionnaire de canaux marketing].

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Champ </p> </th> 
   <th colname="col2" class="entry"> <p>Définition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Activé </p> </td> 
   <td colname="col2"> <p> Active ou désactive ce canal marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom du canal </p> </td> 
   <td colname="col2"> <p>Nom convivial du canal marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remplacer le canal Dernière touche </p> </td> 
   <td colname="col2"> <p> Cette option vous permet d’indiquer si un canal Dernière touche persistant doit être remplacé ou non par le canal sélectionné. Si vous activez cette case à cocher, un canal quelconque (y compris Direct et Interne) remplacera un canal Dernière touche existant. Cela se traduit par l’attribution d’une conversion à un canal qui ne doit peut-être pas bénéficier de crédit. Par exemple, cette option peut garantir que le canal Direct n’a pas reçu de crédit pour la conversion si l’utilisateur provenait précédemment du canal Recherche naturelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ventilation de canal </p> </td> 
   <td colname="col2"> <p>Permet de ventiler un canal en fonction de cette valeur. Vous pouvez ajouter d’éventuelles ventilations (sous-canaux) lors de la création des classifications de canal marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type </p> </td> 
   <td colname="col2"> <p> Indique comment l’utilisateur est parvenu sur votre site. Vous pouvez sélectionner <span class="uicontrol">En ligne</span> ou <span class="uicontrol">Hors ligne</span>. Utilisez des canaux en ligne pour les visiteurs qui viennent par l’intermédiaire d’un moteur de recherche ou d’une campagne par courriel. Les canaux hors connexion s’appliquent aux visiteurs qui ont trouvé le site par l’intermédiaire de bons dans les journaux ou de publicités dans des magazines. Les canaux hors connexion incluent habituellement les données importées depuis les Sources de données des rapports. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/"  >Sources de données</a>. </p> <p>See <a href="/help/components/c-marketing-channels/t-offline-data.md"   > Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Couleur </p> </td> 
   <td colname="col2"> <p>La couleur associée à ce canal marketing. Cette couleur représente le canal sur le rapport <span class="wintitle">Canal marketing</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

