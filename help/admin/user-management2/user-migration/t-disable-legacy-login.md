---
description: Comment désactiver les comptes hérités pour les utilisateurs Analytics.
title: Désactivation des comptes hérités
uuid: 085874b2-10bf-4a56-a337-f3104428d71e
translation-type: tm+mt
source-git-commit: 1ec080acf65c31b077a3daf3846f233f01e011b8

---


# Désactivation des comptes hérités {#disable-legacy-logins}

Comment désactiver les comptes hérités pour les utilisateurs Analytics.

Une fois que vos utilisateurs ont migré du système de gestion des utilisateurs Analytics hérité vers Adobe Admin Console, vous pouvez désactiver leurs comptes hérités. La désactivation des comptes hérités redirige les utilisateurs vers le compte Experience Cloud lorsqu’ils tentent d’utiliser le compte hérité.

1. Ouvrez l’outil de migration dans **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Migration de l’ID utilisateur]**.
1. Dans la section [!DNL User Information], localisez le domaine contenant les utilisateurs que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Sélectionner les utilisateurs]**.
1. Sélectionnez les utilisateurs pour lesquels vous souhaitez désactiver les comptes hérités.

   ![](assets/user-info.png)

   Les utilisateurs éligibles auront l’état *`Migrated`* sous la colonne État de migration. Vous ne pouvez pas désactiver le compte hérité d’un utilisateur tant qu’il n’a pas été migré.
1. Cliquez sur **[!UICONTROL Désactiver le compte hérité]**, puis sur **[!UICONTROL Terminé]**.

   Désactiver le compte hérité indique lequel de vos utilisateurs peut continuer à utiliser ses nom d’utilisateur et mot de passe [!DNL my.omniture.com] hérités.

   Vous ne pouvez pas désactiver les comptes hérités d’un utilisateur qui doit encore être migré. Une fois la désactivation effectuée, l’utilisateur devra utiliser son Experience Cloud ID afin de se connecter et accéder à Analytics.

