---
description: valeur nulle
seo-description: valeur nulle
seo-title: API affectés par la migration
title: API affectés par la migration
uuid: 9 a 5 d 43 be-e 146-476 b -961 e -49 ea 0 a 30 b 500
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# API affectés par la migration{#apis-affected-by-the-migration}

## API affectés par la migration {#topic-8d34296a67d74b1081c3f7e8f650f3ce}

Adobe procède à la migration de toutes les entreprises se connectant actuellement à Analytics sur [!DNL my.omniture.com] vers une authentification via Adobe Experience Cloud. Une fois la migration d’une entreprise en cours, la création et la gestion programmatiques d’utilisateurs par le biais d’autorisations spécifiques à Analytics et de méthodes `GetLoginKey` disponibles via les versions 1.3 et 1.4 de l’API Admin ne seront plus prises en charge. Ces actions seront désormais permises dans l’environnement Experience Cloud via [!DNL adobe.io].

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

* [Généralités sur la gestion des utilisateurs](https://helpx.adobe.com/enterprise/help/users.html)
* [API de gestion des utilisateurs via adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [Forum à propos des API de gestion des utilisateurs](https://forums.adobe.com/community/umapi/overview)
* [Migration de l’accès et de la gestion des utilisateurs d’Analytics vers Experience Cloud](https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/)

