---
description: valeur nulle
title: Conformité GDPR/ePrivacy et transfert côté serveur
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conformité GDPR/ePrivacy et transfert côté serveur

Cette section décrit les récentes améliorations apportées au transfert côté serveur, rendues essentielles après l’entrée en vigueur le 30 septembre 2017 du [règlement de l’UE sur les cookies](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm).

Server-side forwarding is used to share data from Adobe Analytics to other [!DNL Experience Cloud Solutions], such as Audience Manager, in real time. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.

Jusqu’à récemment, le transfert côté serveur ne pouvait pas faire la distinction entre les événements/accès postconsentement et préconsentement. Depuis le 1er novembre 2018, en tant que responsable du traitement des données (client Adobe Analytics), vous avez la possibilité de restreindre les données préconsentement à Adobe Analytics et d’empêcher qu’elles ne soient transférées à AAM. Une nouvelle variable contextuelle de mise en œuvre permet d’identifier les accès pour lesquels aucun consentement n’a été reçu. La variable, une fois définie, empêche l’envoi de ces accès vers AAM jusqu’à réception du consentement.

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. Inversement, si cette chaîne n’apparaît pas sur un accès, celui-ci est transféré à AAM.

Le transfert côté serveur est bidirectionnel, ce qui signifie que lorsqu’il est appliqué à un accès et que cet accès est transféré à AAM, Audience Analytics reçoit d’AAM les informations de segments pour cet accès et les renvoie à Analytics. Par conséquent, tout accès qui n’est pas transféré côté serveur d’Analytics vers AAM ne sera pas enrichi avec la liste des identifiants de segments d’AAM. Il existera ainsi un sous-ensemble de trafic/accès qui n’obtiendra pas d’informations sur les identifiants de segments de la part d’AAM.

## Détails de mise en œuvre {#section_FFA8B66085BF469FAB5365C944FE38F7}

Selon votre méthode de mise en œuvre, procédez comme suit.

| Méthode de mise en œuvre | Étapes |
|--- |--- |
| Adobe Experience Platform Launch | En supposant que l’extension Adobe Analytics soit installée, ajoutez la définition de variable de données contextuelles suivante à l’éditeur de code personnalisé dans la configuration Action d’une règle : <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Remarque :  Définissez la variable contextdata et définissez-la sur 1 si un client ne consent pas à un marketing ciblé. Set the `contextdata` variable to *0* for customers who consented to targeted marketing. |
| Gestion dynamique des balises | Ajoutez la définition de la variable de données contextuelles à l’éditeur Code de page personnalisé : <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Remarque : Définissez la variable contextdata sur 1 si un client ne consent pas au marketing ciblé. Définissez-la sur 0 pour les clients qui ont consenti au marketing ciblé. |
| AppMeasurement | Ajoutez la définition de la variable de données contextuelles au fichier AppMeasurement.js :  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Remarque : Définissez la variable contextdata sur 1 si un client ne consent pas au marketing ciblé. Définissez-la sur 0 pour les clients qui ont consenti au marketing ciblé. |

## Reporting (facultatif) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Vous pouvez utiliser Adobe Analytics pour obtenir un rapport sur la part de votre trafic basée sur le consentement et, par conséquent, sur le serveur transférée, par rapport à la part de votre trafic qui n’est pas basée sur le consentement et qui n’a pas été transférée à AAM.

Pour configurer ce type de reporting, mappez la nouvelle variable contextuelle à une variable de trafic personnalisé (prop) par l’intermédiaire de règles de traitement. Procédure à suivre :

1. Implémentez la variable "cm.ssf" (comme illustré ci-dessus).
1. [Activez la prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilisez les règles de traitement pour mapper la variable contextuelle à la prop.

   1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** , then select a report suite.
   1. Click  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. Cliquez sur **[!UICONTROL Ajouter une règle.]**
   1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable "cm.ssf(Context Data)".
   1. Cliquez sur **[!UICONTROL Enregistrer]**.

