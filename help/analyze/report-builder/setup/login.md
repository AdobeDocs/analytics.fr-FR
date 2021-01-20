---
description: Informations sur les trois façons de se connecter au Report Builder.
title: Ouverture de session dans le Report Builder
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: 67108d1d51a75ae6f015b8808254cd88b6308fbf
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 100%

---


# Ouverture de session dans le Report Builder

Informations sur les trois façons de se connecter au Report Builder.

Actuellement, les options de connexion suivantes sont disponibles lorsque vous cliquez sur **[!UICONTROL Se connecter]** dans le Report Builder :

![](assets/login_screen.png)

* [Standard ](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Authentification unique](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)
* [Experience Cloud et authentification unique ](/help/analyze/report-builder/setup/login.md#section_1FA230F35AB54021A874A7A28DE4C850)

## Standard {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Utilisez cette méthode de connexion pour accéder au Report Builder à l’aide de vos informations d’identification d’Adobe Analytics.

**Connexion au Report Builder : définitions des champs**

| Champ | Définition |
|--- |--- |
| Société | Informations d’identification de connexion de l’entreprise que vous utilisez pour Adobe Analytics. |
| Nom d’utilisateur | Nom d’utilisateur servant pour Adobe Analytics. Les tâches planifiées d’un utilisateur sont liées à son nom. Vous pouvez consulter vos tâches planifiées à partir de tout ordinateur, en utilisant les mêmes informations d’identification pour vous connecter au Créateur de rapports. |
| Mot de passe | Votre mot de passe Analytics. |
| Se souvenir de moi | Les informations de connexion sont chiffrées et stockées dans un fichier de profils utilisateur sur l’ordinateur où est installé le Report Builder. Étant donné que ces informations sont enregistrées, toute personne utilisant le même ordinateur que le créateur du rapport qui ouvre une feuille de calcul contenant un rapport peut en actualiser et en modifier les données. N’activez pas cette option si vous partagez votre ordinateur et souhaitez préserver la confidentialité des données.  Pour désactiver le paramètre de connexion automatique, cliquez sur **[!UICONTROL Connexion avec des identifiants différents]** sur la barre d’outils et désactivez l’option **[!UICONTROL Se souvenir de moi]**. |
| Utiliser un serveur proxy | Activez cette option si vous accédez à Internet par le biais d’un serveur proxy et êtes invité à fournir un nom d’utilisateur et un mot de passe. |

## Authentification unique {#section_6970A5F926774976B85FFE576610E85F}

Cette authentification unique (héritée) vous connecte seulement à Adobe Analytics, et non à l’ensemble d’Experience Cloud.

Vous pouvez également entrer le nom d’un domaine ; le système reconnaîtra le domaine et vous réorientera vers la page de connexion de votre entreprise pour vous connecter à Adobe Analytics.

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

La connexion Experience Cloud vous permet d’utiliser votre Enterprise ID (adresse électronique et mot de passe) pour vous connecter à Adobe Experience Cloud. Cliquez sur **[!UICONTROL Se connecter]** > **[!UICONTROL Se connecter avec un Enterprise ID]** pour accéder à la page de connexion unique de votre entreprise. Pour en savoir plus sur l’Enterprise ID, cliquez [ici](https://helpx.adobe.com/fr/enterprise/kb/enterprise-id-faq.html#whatis).

![](assets/adobe_id_login.png)

>[!NOTE]
>
>La connexion à Experience Cloud repose sur une session ; le jeton expire après 30 jours.

