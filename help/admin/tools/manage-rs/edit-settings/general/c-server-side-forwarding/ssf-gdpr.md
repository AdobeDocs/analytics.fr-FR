---
description: Explique les améliorations apportées au transfert côté serveur, rendues essentielles par le règlement de l’UE sur les cookies.
title: Conformité au RGPD et à la directive vie privée et communications électroniques et transfert côté serveur
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 55%

---

# Conformité au RGPD et à la directive vie privée et communications électroniques et transfert côté serveur

Cette section décrit les améliorations apportées au transfert côté serveur, rendues essentielles après l’entrée en vigueur le 30 septembre 2017 du [règlement de l’UE sur les cookies](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+et+technologies+similaires).

Le transfert côté serveur permet de partager en temps réel des données d’Adobe Analytics vers d’autres [!DNL Experience Cloud Solutions], telles qu’Audience Manager. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.

Auparavant, le transfert côté serveur ne pouvait pas faire la distinction entre les événements/accès postconsentement et préconsentement. Depuis le 1er novembre 2018, vous avez la possibilité, en tant que contrôleur de données (client Adobe Analytics), de limiter les données de consentement préalable à Adobe Analytics et d’empêcher leur transfert vers Adobe Audience Manager. Une nouvelle variable contextuelle de mise en œuvre permet d’identifier les accès pour lesquels aucun consentement n’a été reçu. Lorsqu’elle est définie, la variable empêche l’envoi de ces accès à Adobe Audience Manager jusqu’à réception du consentement.

Lorsque cette nouvelle variable de contexte, `cm.ssf=1`, existe sur un accès, cet accès est marqué et n’est pas transféré côté serveur vers Adobe Audience Manager. À l’inverse, si cette chaîne n’apparaît pas sur un accès, l’accès est transféré vers Adobe Audience Manager.

Le transfert côté serveur est bidirectionnel, ce qui signifie que lorsqu’il est appliqué à un accès et que cet accès est transféré vers Adobe Audience Manager, Audience Analytics reçoit les informations sur le segment pour cet accès de Adobe Audience Manager et les renvoie à Analytics. Par conséquent, tous les accès qui ne sont pas côté serveur transférés d’Analytics vers Adobe Audience Manager ne seront pas enrichis de la liste des identifiants de segment de Adobe Audience Manager. Par conséquent, un sous-ensemble de trafic/accès n’obtiendra pas d’informations d’identifiant de segment de Adobe Audience Manager.

## Détails de mise en œuvre {#section_FFA8B66085BF469FAB5365C944FE38F7}

Selon votre méthode de mise en œuvre, procédez comme suit.

| Méthode de mise en œuvre | Étapes |
|--- |--- |
| Balises dans Adobe Experience Platform | En supposant que l’extension Adobe Analytics soit installée, ajoutez la définition de variable de données contextuelles suivante à l’éditeur de code personnalisé dans la configuration Action d’une règle : <br/>`s.contextData['cm.ssf'] = '1'` <br/>Remarque : définissez la variable contextdata sur 1 si un client ne consent pas au marketing ciblé. Définissez la variable `contextdata` sur *0* pour les clients qui ont consenti au marketing ciblé. |
| AppMeasurement | Ajoutez la définition de la variable de données contextuelles au fichier AppMeasurement.js : <br/>`s.contextData['cm.ssf'] = '1'` <br/>Remarque : définissez la variable contextdata sur 1 si un client ne consent pas au marketing ciblé. Définissez-la sur 0 pour les clients qui ont consenti au marketing ciblé. |

## Reporting (facultatif) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Vous pouvez utiliser Adobe Analytics pour générer des rapports sur la part de votre trafic qui est basée sur le consentement et qui a donc été transférée côté serveur, par rapport à la part de votre trafic qui n’est pas basée sur le consentement et qui n’a pas été transférée vers Adobe Audience Manager.

Pour configurer ce type de reporting, mappez la nouvelle variable contextuelle à une variable de trafic personnalisé (prop) par l’intermédiaire de règles de traitement. Procédure à suivre :

1. Mettez en œuvre la variable « cm.ssf » (comme indiqué ci-dessus).
1. [Activez la prop.](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
1. Utilisez les règles de traitement pour mapper la variable contextuelle à la prop.

   1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**, puis sélectionnez une suite de rapports.
   1. Cliquez sur **[!UICONTROL Modifier la Report Suite]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de traitement]**.
   1. Cliquez sur **[!UICONTROL Ajouter une règle]**.
   1. Sous **[!UICONTROL Toujours exécuter]**, remplacez la valeur de la prop que vous avez activée par la variable contextuelle « cm.ssf(Context Data) ».
   1. Cliquez sur **[!UICONTROL Enregistrer]**.
