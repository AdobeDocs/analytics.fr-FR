---
title: Mesures du cycle de vie mobile
description: Mesures basées sur les données collectées à l’aide du SDK Mobile.
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 10%
---
# Mesures du cycle de vie mobile

>[!BEGINSHADEBOX]

*Cette page fait référence aux données suivies couramment via Adobe Experience Platform Mobile SDK. Pour les dimensions suivies à l’aide de Mobile SDK, voir [Dimensions du cycle de vie mobile](../dimensions/lifecycle-dimensions.md). Pour plus d’informations sur les appareils mobiles à l’aide de l’agent utilisateur, voir [Dimensions de recherche mobile](../dimensions/mobile-dimensions.md).*

>[!ENDSHADEBOX]

| Nom de la mesure du cycle de vie | Description | Variable de données contextuelles |
| --- | --- | --- |
| **[!UICONTROL Premiers lancements]** | Nombre de fois où l’application a été exécutée pour la première fois après avoir été installée ou réinstallée. | `a.InstallEvent` |
| **[!UICONTROL Mises à niveau]** | Nombre de fois où l’application a été exécutée pour la première fois après une mise à niveau ou après modification de son numéro de version. | `a.UpgradeEvent` |
| **[!UICONTROL Lancements]** | Nombre d’exécutions de l’application, y compris les exécutions après des blocages et des installations. Un lancement est également comptabilisé lorsque l’application reprend en arrière-plan après le dépassement du délai d’expiration de la session du cycle de vie. | `a.LaunchEvent` |
| **[!UICONTROL Blocages]** | Nombre de fois où l’application s’est bloquée avant d’être fermée. Le blocage est signalé au prochain démarrage de l’application. | `a.CrashEvent` |
| **[!UICONTROL Durée totale de la session]** | Nombre total de secondes pendant lesquelles les sessions de l’application ont duré, en fonction de la durée d’ouverture de l’application et de son affichage au premier plan. Chaque lancement signale la durée de la session précédente ; cette mesure correspond à la somme de ces valeurs. | `a.PrevSessionLength` |
| **[!UICONTROL Durée totale de l’action]** | Nombre total de secondes (temps d’horloge) entre le début et la fin d’une action minutée, entre les sessions. Renseigné par les méthodes `trackTimedAction` dans l’ancien SDK Mobile Services (4.x). | `a.action.time.total` |
| **[!UICONTROL Durée de l’action dans l’application]** | Nombre de secondes passées dans l’application entre le début et la fin d’une action minutée, entre les sessions. Renseigné par les méthodes `trackTimedAction` dans l’ancien SDK Mobile Services (4.x). | `a.action.time.inapp` |
| **[!UICONTROL Valeur de durée de vie (événement)]** | Valeur de durée de vie d’un utilisateur, telle que les achats de durée de vie, les vues de publicités, les vidéos terminées ou les partages sur les réseaux sociaux. Renseigné par la méthode `trackLifetimeValueIncrease` dans l’ancien SDK Mobile Services (4.x). | `a.ltv.amount` |

>[!NOTE]
>
>Les mesures [!UICONTROL Total de la durée d’action], [!UICONTROL Durée d’action dans l’application] et [!UICONTROL Valeur de durée de vie (événement)] sont renseignées par des méthodes dans l’ancien SDK Mobile Services (4.x), qui n’est plus pris en charge. Adobe Experience Platform Mobile SDK ne renseigne pas automatiquement ces mesures. Voir [Migration de la bibliothèque mobile Adobe (v4) vers Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) pour des alternatives aux actions temporisées et au suivi de la valeur de la durée de vie.
