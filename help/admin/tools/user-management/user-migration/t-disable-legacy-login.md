---
description: Découvrez comment désactiver les comptes hérités pour les utilisateurs d’Analytics.
title: Désactiver les comptes hérités
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
TQID: 'https://experienceleague.adobe.com/xwLXKuaeoKB5-TSVC7FLQXdUsBEeOg-zuITMa8Z3OIo'
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
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 60%

---

# Désactiver les comptes hérités

Découvrez comment désactiver les comptes hérités pour les utilisateurs d’Analytics.

Une fois que vos utilisateurs ont migré de l’ancien système de gestion des utilisateurs Analytics vers Adobe Admin Console, vous pouvez désactiver leurs comptes hérités. La désactivation des comptes hérités redirige les utilisateurs vers le compte CX Enterprise s’ils tentent d’utiliser le compte hérité.

1. Ouvrez l’outil de migration dans **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Migration de l’ID utilisateur]**.
1. Dans la section [!DNL User Information], localisez le domaine contenant les utilisateurs que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Sélectionner les utilisateurs]**.
1. Sélectionnez les utilisateurs pour lesquels vous souhaitez désactiver les comptes hérités.

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

   Les utilisateurs éligibles auront l’état *`Migrated`* sous la colonne État de migration. Vous ne pouvez pas désactiver le compte hérité d’un utilisateur tant qu’il n’a pas été migré.
1. Cliquez sur **[!UICONTROL Désactiver le compte hérité]**, puis sur **[!UICONTROL Terminé]**.

   Désactiver le compte hérité indique lequel de vos utilisateurs peut continuer à utiliser ses nom d’utilisateur et mot de passe [!DNL my.omniture.com] hérités.

   Vous ne pouvez pas désactiver les comptes hérités d’un utilisateur qui doit encore être migré. Une fois désactivé, l’utilisateur doit utiliser son Experience Cloud ID pour se connecter et accéder à Analytics.
