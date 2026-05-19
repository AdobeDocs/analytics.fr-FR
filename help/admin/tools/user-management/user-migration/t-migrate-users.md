---
description: Migration des utilisateurs du système de gestion des utilisateurs Analytics hérité vers Adobe Admin Console.
title: Migration de comptes d’utilisateurs Analytics sous la forme d’Adobe ID
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
TQID: https://experienceleague.adobe.com/bD-qiEI3KbDBNe4aO01-MqzjoZ-OMcGAnd9vnMTBmZs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 405
ht-degree: 72%

---

# Migration de comptes d’utilisateurs Analytics sous la forme d’Adobe ID

Effectuez la migration des utilisateurs du système de gestion des utilisateurs Analytics hérité vers Adobe Admin Console.

>[!NOTE]
>
>Si un administrateur qui n’est pas connecté à CX Enterprise tente d’accéder à l’outil Migration de l’ID utilisateur, il est redirigé vers la page de connexion CX Enterprise.

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Migration de l’ID utilisateur]**.

   ![](/help/admin/tools/user-management/user-migration/assets/migration-progress.png)

   La page Migration de l’ID utilisateur comporte deux sections : *Progression de la migration* et *Informations utilisateur*.

## Progression de la migration

<table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Phase </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Migrations effectuées </p> </td> 
      <td colname="col2"> <p>Les utilisateurs ont accepté l'invitation. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Connexion héritée désactivée </p> </td> 
      <td colname="col2"> <p>La connexion héritée à l’aide d’un ID d’entreprise est désactivée. Les utilisateurs accèdent désormais à CX Enterprise à l’aide de leur Adobe ID ou Enterprise ID. Lorsque tous vos utilisateurs ont atteint cette phase, la migration est terminée. </p> <p>Lors de la migration, la connexion héritée est désactivée. Les utilisateurs sont redirigés vers <span class="filepath"> experiencecloud.adobe.com</span> et doivent se connecter à l’aide de l’Adobe ID ou de l’Enterprise ID. </p> </td> 
   </tr> 
   </tbody> 
   </table>

## Informations sur l&#39;utilisateur

Informations sur l’utilisateur décrit les utilisateurs de votre organisation, séparés par nom de domaine.

<table id="table_3822E27AF81E4A188562FEB5131548A5"> 
<thead> 
<tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
</tr>
</thead>
<tbody> 
<tr> 
   <td colname="col1"> <p>Domaine </p> </td> 
   <td colname="col2"> <p>Les domaines sont spécifiques aux ID d’e-mail de la base d’utilisateurs Analytics actuelle. Un domaine ne peut être déposé que par une seule organisation et seuls les administrateurs système peuvent déposer un domaine. Pour plus d’informations, voir <a href="https://helpx.adobe.com/fr/enterprise/help/request-access-to-claimed-domain.html"> Demande d’accès à un domaine déposé</a>. </p> </td> 
</tr> 
<tr> 
   <td colname="col1"> <p>Domaine déposé </p> </td> 
   <td colname="col2"> <p>Vous devez être administrateur système pour migrer des utilisateurs sous la forme d’Enterprise ID ou de Federated ID, et déposer un domaine disponible par le biais d’Adobe Admin Console avant d’effectuer la migration. En savoir plus <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> ici</a>. </p> <p>Si vous ne souhaitez pas déposer de domaine en Enterprise ID ou Federated ID, passez cette étape et migrez les utilisateurs en Adobe ID. Pour en savoir plus sur les types d’ID, cliquez <a href="https://helpx.adobe.com/fr/enterprise/using/identity.html"> ici</a>. </p> </td> 
</tr> 
</tbody> 
</table>

1. Localisez le domaine contenant les ID utilisateur que vous souhaitez migrer, puis sous **[!UICONTROL Migration requise]**, cliquez sur **[!UICONTROL Sélectionner les utilisateurs]**.
1. Sur la page [!DNL Users], sélectionnez les utilisateurs que vous souhaitez migrer, puis cliquez sur **[!UICONTROL Migrer]**.

   Lorsque vous cliquez sur **[!UICONTROL Migrer]**, les utilisateurs reçoivent une invitation (Migration commencée) et doivent l’accepter. L’état de leur ID utilisateur passe alors à Migration terminée. Vous pouvez alors désactiver l’accès à `[!DNL my.omniture.com].` de leur compté hérité

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

1. Indiquez le type d’ID selon lequel vous voulez migrer les utilisateurs (Adobe ID ou Enterprise ID)

   Après la migration des utilisateurs, l’état de la colonne État de migration passe de *`Not Initiated`* à *`Migrated`*.

   Si *`Failed`* s’affiche, pointez sur l’icône pour une description de l’échec de la migration.
