---
description: Comment désactiver les comptes hérités pour les utilisateurs Analytics.
seo-description: Comment désactiver les comptes hérités pour les utilisateurs Analytics.
seo-title: Désactivation des comptes hérités
title: Désactivation des comptes hérités
uuid: 085874b2-10bf-4a56-a337-f3104428d71e
translation-type: tm+mt
source-git-commit: 56d27762320a752dff6ab4d9d763bbbf6e0deff5

---


# Désactivation des comptes hérités{#disable-legacy-logins}

Comment désactiver les comptes hérités pour les utilisateurs Analytics.

Une fois que vos utilisateurs ont migré du système de gestion des utilisateurs Analytics hérité vers Adobe Admin Console, vous pouvez désactiver leurs comptes hérités. La désactivation des comptes hérités redirige les utilisateurs vers le compte Experience Cloud lorsqu’ils tentent d’utiliser le compte hérité.

1. Open the Migration tool in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User ID Migration]**.
1. In the [!DNL User Information] section, locate the domain containing the users you want to work with, then click **[!UICONTROL Select Users]**.
1. Sélectionnez les utilisateurs pour lesquels vous souhaitez désactiver les comptes hérités.

   ![](assets/user-info.png)

   Les utilisateurs éligibles ont un état de sous *`Migrated`* la colonne Statut de migration. Vous ne pouvez pas désactiver le compte hérité d’un utilisateur tant qu’il n’a pas été migré.
1. Click **[!UICONTROL Disable Legacy Login]**, then click **[!UICONTROL Done]**.

   Désactiver le compte hérité indique lequel de vos utilisateurs peut continuer à utiliser ses nom d’utilisateur et mot de passe [!DNL my.omniture.com] hérités.

   Vous ne pouvez pas désactiver les compte hérité d’un utilisateur qui doit encore être migré. Une fois la désactivation effectuée, l’utilisateur devra utiliser son Experience Cloud ID afin de se connecter et accéder à Analytics.

