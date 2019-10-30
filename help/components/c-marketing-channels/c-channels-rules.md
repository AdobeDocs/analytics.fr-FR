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
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# À propos des canaux et des règles

Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également créer des montants de coûts et de budget pour les canaux associés, et spécifier la durée souhaitée d’engagement du visiteur. Les tâches de configuration du rapport sont effectuées dans les Outils d’administration.

Vous devez concevoir un canal comme un conteneur pour les visites. Les règles affectent des visites au conteneur approprié.

![](assets/buckets_2.png)

Adobe fournit plusieurs canaux prédéfinis au cours d’une [configuration automatique](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B), que vous pouvez modifier en fonction de vos besoins.

> [!NOTE] Adobe recommande de configurer votre rapport dans une suite de rapports que vous pouvez utiliser comme modèle à des fins de test. Le modèle sera ensuite utilisé pour appliquer les ensembles de canaux et de règles globalement à une ou plusieurs suites de rapports de production.
>
>Reportez-vous à la section [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

Consultez les sections suivantes :

* [Conditions préalables](../../components/c-marketing-channels/c-channels-rules.md#section_9913D2932E3140C099B7978CA95378B2)
* [Remarques importantes sur le traitement](../../components/c-marketing-channels/c-channels-rules.md#section_DE372EEF02314F2395750CF2892DAAE1)

## Conditions préalables {#section_9913D2932E3140C099B7978CA95378B2}

En cas de besoin, contactez l’assistance clientèle pour obtenir de l’aide au sujet des conditions préalables :

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Configurez l’accès des groupes d’utilisateurs au rapport **[!UICONTROL Canal marketing]**.

   See [Configure User Group Access](../../components/c-marketing-channels/t-user-groups.md#task_B156E7527FE94055A43A697338FE8C8C).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#section_DE372EEF02314F2395750CF2892DAAE1}

* Le système traite les règles dans l’ordre spécifié ; lorsqu’une règle est vérifiée, le système cesse le traitement des règles restantes.
* Les règles peuvent accéder aux variables que VISTA a définies, mais pas aux données que VISTA a supprimées.
* Les canaux n’enregistrent que les mesures de conversion. Les mesures de trafic ne sont pas disponibles.
* Un même événement (tel qu’un achat ou un clic) n’est jamais porté au crédit de deux canaux marketing. En cela, les canaux marketing diffèrent des eVars (car deux eVars peuvent recevoir le crédit d’un seul et même événement).
* Le rapport peut traiter jusqu’à 25 canaux simultanément.

