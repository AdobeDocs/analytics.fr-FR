---
description: Répertorie les interfaces API affectées par la migration des utilisateurs
title: Interfaces API affectées par la migration des utilisateurs
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
source-git-commit: b90356050a6ff39e1688a10f6aa0af284284e2a6
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# Interfaces API affectées par la migration des utilisateurs{#apis-affected-by-the-migration}

Adobe procède à la migration de toutes les entreprises se connectant actuellement à Analytics sur [!DNL my.omniture.com] vers une authentification via Adobe Experience Cloud. Une fois la migration d’une entreprise en cours, la création et la gestion programmatiques d’utilisateurs par le biais d’autorisations spécifiques à Analytics et de méthodes `GetLoginKey` disponibles via les versions 1.3 et 1.4 de l’API Admin ne seront plus prises en charge. Ces actions seront désormais permises dans l’environnement Experience Cloud via [!DNL adobe.io].

## Méthodes d’API affectées {#methods}

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

## Actions possibles {#actions}

Si votre entreprise utilise actuellement ces méthodes, vous recevrez une notification vous informant de la migration, à compter du 31 mars 2018. La notification vous sera envoyée au moins 30 jours avant la date de début de la migration de votre entreprise vers l’authentification via Experience Cloud. Ces méthodes ne seront plus prises en charge à compter de cette date.

Si votre entreprise n’utilise aucune de ces méthodes, veillez simplement à ne pas commencer à les utiliser.

Pour en savoir plus :

* [Généralités sur la gestion des utilisateurs](https://helpx.adobe.com/fr/enterprise/help/users.html)
* [Forum à propos des API de gestion des utilisateurs](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migration de l’accès et de la gestion des utilisateurs d’Analytics vers Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=fr)
