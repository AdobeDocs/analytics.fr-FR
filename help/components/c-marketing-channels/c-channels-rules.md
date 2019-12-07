---
description: Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également créer des montants de coûts et de budget pour les canaux associés, et spécifier la durée souhaitée d’engagement du visiteur. Les tâches de configuration du rapport sont effectuées dans les Outils d’administration.
subtopic: Marketing channels
title: À propos des canaux et des règles
topic: Reports and analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# À propos des canaux et des règles

Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également créer des montants de coûts et de budget pour les canaux associés, et spécifier la durée souhaitée d’engagement du visiteur. Les tâches de configuration du rapport sont effectuées dans les Outils d’administration.

Vous devez concevoir un canal comme un conteneur pour les visites. Les règles affectent des visites au conteneur approprié.

![](assets/buckets_2.png)

Adobe fournit plusieurs canaux prédéfinis au cours d’une [configuration automatique](/help/components/c-marketing-channels/c-channel-autosetup.md), que vous pouvez modifier en fonction de vos besoins.

>[!NOTE]
>
>Adobe conseille de définir le rapport dans une suite de rapports à utiliser comme modèle pour les tests. Le modèle sera ensuite utilisé pour appliquer les ensembles de canaux et de règles globalement à une ou plusieurs suites de rapports de production.
>
>Reportez-vous à la section [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](/help/components/c-marketing-channels/t-template.md).

Consultez les sections suivantes :

* [Conditions préalables](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [Remarques importantes concernant le traitement](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## Conditions préalables {#prereqs}

En cas de besoin, contactez l’assistance clientèle pour obtenir de l’aide au sujet des conditions préalables :

* Dans la Console d’administration (Paramètres généraux du compte), activez l’option **[!UICONTROL Niveau de conversion]** (commerce électronique) pour suite de rapports.

   Pour plus d’informations, consultez la section [Paramètres généraux du compte](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) dans l’aide d’Analytics.

* Configurez l’accès des groupes d’utilisateurs au rapport **[!UICONTROL Canal marketing]**.

   Voir [Configuration de l’accès au groupe d’utilisateurs](/help/components/c-marketing-channels/t-user-groups.md).

* Vérifiez que le gestionnaire de compte a bien activé les **[!UICONTROL rapports Canal]** pour votre suite de rapports.

## Remarques importantes concernant le traitement {#important-proc-rules}

* Le système traite les règles dans l’ordre spécifié ; lorsqu’une règle est vérifiée, le système cesse le traitement des règles restantes.
* Les règles peuvent accéder aux variables que VISTA a définies, mais pas aux données que VISTA a supprimées.
* Les canaux n’enregistrent que les mesures de conversion. Les mesures de trafic ne sont pas disponibles.
* Un même événement (tel qu’un achat ou un clic) n’est jamais porté au crédit de deux canaux marketing. En cela, les canaux marketing diffèrent des eVars (car deux eVars peuvent recevoir le crédit d’un seul et même événement).
* Le rapport peut traiter jusqu’à 25 canaux simultanément.

