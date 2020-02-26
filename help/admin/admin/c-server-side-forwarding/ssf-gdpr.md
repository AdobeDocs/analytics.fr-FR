---
description: 'null'
title: Conformité au RGPD et à la directive vie privée et communications électroniques et transfert côté serveur
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conformité au RGPD et à la directive vie privée et communications électroniques et transfert côté serveur

Cette section décrit les récentes améliorations apportées au transfert côté serveur, rendues essentielles après l’entrée en vigueur le 30 septembre 2017 du [règlement de l’UE sur les cookies](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm).

Le transfert côté serveur permet de partager en temps réel des données d’Adobe Analytics vers d’autres [!DNL Experience Cloud Solutions], telles qu’Audience Manager. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.

Jusqu’à récemment, le transfert côté serveur ne pouvait pas faire la distinction entre les événements/accès postconsentement et préconsentement. Depuis le 1er novembre 2018, en tant que responsable du traitement des données (client Adobe Analytics), vous avez la possibilité de restreindre les données préconsentement à Adobe Analytics et d’empêcher qu’elles ne soient transférées à AAM. Une nouvelle variable contextuelle de mise en œuvre permet d’identifier les accès pour lesquels aucun consentement n’a été reçu. Une fois définie, la variable empêche l’envoi de ces accès vers AAM jusqu’à réception du consentement.

Quand cette nouvelle variable contextuelle `cm.ssf=1` existe sur un accès, cet accès est identifié et n’est pas transféré côté serveur vers AAM. Inversement, si cette chaîne n’apparaît pas sur un accès, celui-ci est transféré à AAM.

Le transfert côté serveur est bidirectionnel, ce qui signifie que lorsqu’il est appliqué à un accès et que cet accès est transféré à AAM, Audience Analytics reçoit d’AAM les informations de segments pour cet accès et les renvoie à Analytics. Par conséquent, tout accès qui n’est pas transféré côté serveur d’Analytics vers AAM ne sera pas enrichi avec la liste des identifiants de segments d’AAM. Il existera ainsi un sous-ensemble de trafic/accès qui n’obtiendra pas d’informations sur les identifiants de segments de la part d’AAM.

## Détails de mise en œuvre {#section_FFA8B66085BF469FAB5365C944FE38F7}

Selon votre méthode de mise en œuvre, procédez comme suit.

| Méthode de mise en œuvre | Étapes |
|--- |--- |
| Adobe Experience Platform Launch | En supposant que l’extension Adobe Analytics soit installée, ajoutez la définition de variable de données contextuelles suivante à l’éditeur de code personnalisé dans la configuration Action d’une règle : <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/> Remarque : définissez la variable contextdata sur 1 si un client ne consent pas au marketing ciblé. Définissez la variable `contextdata` sur *0* pour les clients qui ont consenti au marketing ciblé. |
| Gestion dynamique des balises | Ajoutez la définition de la variable de données contextuelles à l’éditeur Code de page personnalisé : <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Remarque : définissez la variable contextdata sur 1 si un client ne consent pas au marketing ciblé. Définissez-la sur 0 pour les clients qui ont consenti au marketing ciblé. |
| AppMeasurement | Ajoutez la définition de la variable de données contextuelles au fichier AppMeasurement.js :  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Remarque : définissez la variable contextdata sur 1 si un client ne consent pas au marketing ciblé. Définissez-la sur 0 pour les clients qui ont consenti au marketing ciblé. |

## Reporting (facultatif) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

À l’aide d’Adobe Analytics, vous pouvez établir des rapports sur la quantité du trafic pour lequel un consentement a été donné et par conséquent a été transféré côté serveur comparativement à la quantité de trafic sans consentement qui n’a pas été transféré vers AAM.

Pour configurer ce type de reporting, mappez la nouvelle variable contextuelle à une variable de trafic personnalisé (prop) par l’intermédiaire de règles de traitement. Procédure à suivre :

1. Mettez en œuvre la variable « cm.ssf » (comme indiqué ci-dessus).
1. [Activez la prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilisez les règles de traitement pour mapper la variable contextuelle à la prop.

   1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**, puis sélectionnez une suite de rapports.
   1. Cliquez sur **[!UICONTROL Modifier la Report Suite]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de traitement]** .
   1. Cliquez sur **[!UICONTROL Ajouter une règle.]**
   1. Sous **[!UICONTROL Toujours exécuter]**, remplacez la valeur de la prop que vous avez activée par la variable contextuelle « cm.ssf(Context Data) ».
   1. Cliquez sur **[!UICONTROL Enregistrer]**.

