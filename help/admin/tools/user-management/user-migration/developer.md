---
description: Répertorie les interfaces API affectées par la migration des utilisateurs
title: Interfaces API affectées par la migration des utilisateurs
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 32%

---

# Interfaces API affectées par la migration des utilisateurs{#apis-affected-by-the-migration}

Adobe migre toutes les sociétés de connexion Analytics de [!DNL my.omniture.com] à l’authentification via Adobe CX Enterprise. Une fois la migration d’une entreprise en cours, la création et la gestion programmatiques d’utilisateurs par le biais d’autorisations spécifiques à Analytics et de méthodes `GetLoginKey` disponibles via les versions 1.3 et 1.4 de l’API Admin ne seront plus prises en charge. Ces actions seront désormais activées dans toute l’entreprise CX via `adobe.io`.

## Méthodes d’API affectées {#methods}

Les méthodes d’API suivantes dans les versions 1.3 et 1.4 de l’API Admin ne seront plus prises en charge une fois la migration des utilisateurs commencée :

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

Si votre entreprise utilise actuellement ces méthodes, recherchez une notification préalable à la migration à compter du 31 mars 2018. La notification sera envoyée au moins 30 jours avant que votre entreprise ne commence la migration vers l’authentification CX Enterprise. À ce stade, ces méthodes ne seront plus prises en charge.

Si votre entreprise n’utilise aucune de ces méthodes, aucune action n’est requise, à part vous assurer que vous ne commencez pas à utiliser ces méthodes.

Pour plus d’informations :

* [Informations générales sur User Management](https://helpx.adobe.com/fr/enterprise/help/users.html)
* [Forum de l’API User Management](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migration de l’accès utilisateur et de la gestion Analytics vers CX Enterprise](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
