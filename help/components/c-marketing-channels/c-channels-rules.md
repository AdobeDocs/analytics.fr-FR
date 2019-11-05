---
description: Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également créer des montants de coûts et de budget pour les canaux associés, et spécifier la durée souhaitée d’engagement du visiteur. Les tâches de configuration du rapport sont effectuées dans les Outils d’administration.
seo-description: Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également créer des montants de coûts et de budget pour les canaux associés, et spécifier la durée souhaitée d’engagement du visiteur. Les tâches de configuration du rapport sont effectuées dans les Outils d’administration.
seo-title: À propos des canaux et des règles
solution: Analytics
subtopic: Canaux marketing
title: À propos des canaux et des règles
topic: Reports & Analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# À propos des canaux et des règles

Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également créer des montants de coûts et de budget pour les canaux associés, et spécifier la durée souhaitée d’engagement du visiteur. Les tâches de configuration du rapport sont effectuées dans les Outils d’administration.

Vous devez concevoir un canal comme un conteneur pour les visites. Les règles affectent des visites au conteneur approprié.

![](assets/buckets_2.png)

Adobe fournit plusieurs canaux prédéfinis au cours d’une [configuration automatique](/help/components/c-marketing-channels/c-channel-autosetup.md), que vous pouvez modifier en fonction de vos besoins.

>[!NOTE]
>
> Adobe recommande de configurer votre rapport dans une suite de rapports que vous pouvez utiliser comme modèle à des fins de test. Le modèle sera ensuite utilisé pour appliquer les ensembles de canaux et de règles globalement à une ou plusieurs suites de rapports de production.
>
>Reportez-vous à la section [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](/help/components/c-marketing-channels/t-template.md).

Consultez les sections suivantes :

* [Conditions préalables](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [Remarques importantes sur le traitement](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## Conditions préalables {#prereqs}

En cas de besoin, contactez l’assistance clientèle pour obtenir de l’aide au sujet des conditions préalables :

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Configurez l’accès des groupes d’utilisateurs au rapport **[!UICONTROL Canal marketing]**.

   See [Configure User Group Access](/help/components/c-marketing-channels/t-user-groups.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#important-proc-rules}

* Le système traite les règles dans l’ordre spécifié ; lorsqu’une règle est vérifiée, le système cesse le traitement des règles restantes.
* Les règles peuvent accéder aux variables que VISTA a définies, mais pas aux données que VISTA a supprimées.
* Les canaux n’enregistrent que les mesures de conversion. Les mesures de trafic ne sont pas disponibles.
* Un même événement (tel qu’un achat ou un clic) n’est jamais porté au crédit de deux canaux marketing. En cela, les canaux marketing diffèrent des eVars (car deux eVars peuvent recevoir le crédit d’un seul et même événement).
* Le rapport peut traiter jusqu’à 25 canaux simultanément.

