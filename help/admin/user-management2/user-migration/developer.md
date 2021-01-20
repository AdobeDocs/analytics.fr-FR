---
description: API de listes affectées par la migration des utilisateurs
title: API affectées par la migration des utilisateurs
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
translation-type: tm+mt
source-git-commit: f2fe11eeafc7b188ff7a886847b33a82ab80e47a
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 92%

---


# API affectées par la migration des utilisateurs{#apis-affected-by-the-migration}

Adobe procède à la migration de toutes les entreprises se connectant actuellement à Analytics sur [!DNL my.omniture.com] vers une authentification via Adobe Experience Cloud. Une fois la migration d’une entreprise en cours, la création et la gestion programmatiques d’utilisateurs par le biais d’autorisations spécifiques à Analytics et de méthodes `GetLoginKey` disponibles via les versions 1.3 et 1.4 de l’API Admin ne seront plus prises en charge. Ces actions seront désormais permises dans l’environnement Experience Cloud via [!DNL adobe.io].

## Méthodes d’API affectées {#section-d19051ac26cc49aeb124f767c4760254}

Les méthodes d’API des versions 1.3 et 1.4 de l’API Admin suivantes ne seront plus prises en charge une fois que la migration des utilisateurs aura été lancée :

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## Actions possibles {#section-8b0b89a862614f729ebdbe092ce99027}

Si votre entreprise utilise actuellement ces méthodes, vous recevrez une notification vous informant de la migration, à compter du 31 mars 2018. La notification vous sera envoyée au moins 30 jours avant la date de début de la migration de votre entreprise vers l’authentification via Experience Cloud. Ces méthodes ne seront plus prises en charge à compter de cette date.

Si votre entreprise n’utilise aucune de ces méthodes, veillez simplement à ne pas commencer à les utiliser.

Pour en savoir plus :

* [Généralités sur la gestion des utilisateurs](https://helpx.adobe.com/fr/enterprise/help/users.html)
* [API de gestion des utilisateurs via adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [Forum à propos des API de gestion des utilisateurs](https://forums.adobe.com/community/umapi/overview)
* [Migration de l’accès et de la gestion des utilisateurs d’Analytics vers Experience Cloud](https://docs.adobe.com/content/help/fr-FR/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html)

