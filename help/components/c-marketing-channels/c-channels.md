---
description: Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans canaux marketing, une configuration automatique vous permet de créer plusieurs canaux, ainsi que leurs règles. Vous pouvez modifier les canaux prédéfinis en fonction de vos besoins, ou créer vos propres canaux (avec un maximum de 25 canaux).
subtopic: Marketing channels
title: Gestion des canaux marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 86%

---


# Gestion des canaux marketing

Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans canaux marketing, une configuration automatique vous permet de créer plusieurs canaux, ainsi que leurs règles. Vous pouvez modifier les canaux prédéfinis en fonction de vos besoins, ou créer vos propres canaux (avec un maximum de 25 canaux).

L’ajout de canaux à la page [!UICONTROL Canaux marketing] est indépendant de la création de règles sur la page [Règles de traitement des canaux marketing](/help/components/c-marketing-channels/c-rules.md). Vous associez des règles aux canaux lors de la création de règles.

Voici quelques consignes concernant la création de canaux :

* Planifiez en dressant la liste de tous vos canaux afin que tous les accès des visiteurs soient classés dans le canal approprié.
* Include channels for the categories of [Internal](/help/components/c-marketing-channels/c-rules.md) hits and [Direct](/help/components/c-marketing-channels/c-rules.md) hits.
* Inclure un canal fourre-tout &quot;Autres campagnes&quot;, à placer après les canaux payés et avant les canaux organiques.


## Conditions préalables {#prereqs}

En cas de besoin, contactez l’assistance clientèle pour obtenir de l’aide au sujet des conditions préalables :

* Dans la Console d’administration (Paramètres généraux du compte), activez l’option **[!UICONTROL Niveau de conversion]** (commerce électronique) pour suite de rapports.

   Pour plus d’informations, consultez la section [Paramètres généraux du compte](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/general-acct-settings-admin.html) dans l’aide d’Analytics.

* Configuration de l’accès aux dimensions du Canal marketing.

   Voir [autorisations des canaux marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

* Vérifiez que le gestionnaire de compte a bien activé les **[!UICONTROL rapports Canal]** pour votre suite de rapports.

## Ajout de canaux marketing {#add-mktg-channels}

Ajoutez des canaux marketing dans le Gestionnaire de canaux marketing.

>[!NOTE]
>
>Il est impossible de supprimer un canal. Si vous ne souhaitez pas utiliser un canal, vous pouvez le désactiver ou le renommer, et le conserver pour une utilisation ultérieure.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sur la page [!UICONTROL Gestionnaire de Report Suites], sélectionnez une suite de rapports.

   Si vous sélectionnez plusieurs suites de rapports, choisissez un modèle à partir duquel copier les paramètres vers les suites de rapports sélectionnées.

   Reportez-vous à la section [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Canaux marketing]** > **[!UICONTROL Gestionnaire de canaux marketing]**.

   La page [Configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md) s’affiche si aucun canal n’est défini dans votre suite de rapports.

1. Sur la page [!UICONTROL Gestionnaire de canaux marketing], cliquez sur **[!UICONTROL Ajouter un canal]**.

   Cette option n’est pas disponible lorsque 25 canaux ont été définis.

1. Cliquez sur **[!UICONTROL Enregistrer.]**
1. Pour configurer les règles pour le canal, cliquez sur **[!UICONTROL Règles de traitement des canaux marketing]**.

   Reportez-vous à la section [Création de règles de traitement des canaux marketing](/help/components/c-marketing-channels/c-rules.md).

## Appliquer les paramètres de canal {#mktg-channel-mgr}

Plusieurs paramètres peuvent être appliqués à chaque canal sur la page Gestionnaire [!UICONTROL de Canaux] marketing.

| Champ | Définition |
|--- |--- |
| Activé | Active ou désactive ce canal marketing. |
| Nom du canal | Nom convivial du canal marketing. |
| Remplacer le canal Dernière touche | Cette option vous permet d’indiquer si un canal Dernière touche persistant doit être remplacé ou non par le canal sélectionné. Si vous activez cette case à cocher, un canal quelconque (y compris Direct et Interne) remplacera un canal Dernière touche existant. Cela se traduit par l’attribution d’une conversion à un canal qui ne doit peut-être pas bénéficier de crédit. Par exemple, cette option peut garantir que le canal Direct n’a pas reçu de crédit pour la conversion si l’utilisateur provenait précédemment du canal Recherche naturelle. |
| Ventilation de canal | Permet de ventiler un canal en fonction de cette valeur. Vous pouvez ajouter d’éventuelles ventilations (sous-canaux) lors de la création des [classifications de canal marketing](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Type | Indique comment l’utilisateur est parvenu sur votre site. Vous pouvez sélectionner En ligne ou Hors ligne. Utilisez des canaux en ligne pour les visiteurs qui viennent par l’intermédiaire d’un moteur de recherche ou d’une campagne par courriel. Les canaux hors connexion s’appliquent aux visiteurs qui ont trouvé le site par l’intermédiaire de bons dans les journaux ou de publicités dans des magazines. Les canaux hors connexion incluent habituellement les données importées depuis les Sources de données des rapports. Voir [Sources de données](https://docs.adobe.com/content/help/fr-FR/analytics/import/data-sources/datasrc-home.html). Voir [Ajout de données hors ligne](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Couleur | Rapports et Analytics uniquement : Couleur associée à ce canal marketing. Cette couleur représente le canal sur le rapport Canal marketing. |

### Bonnes pratiques : le remplacement

Il est recommandé de désélectionner l’option de remplacement Dernière touche pour les canaux Directs et Internes, afin qu’ils ne puissent pas s’attribuer le crédit d’autres canaux Dernière touche persistants (ou les uns des autres).

![](assets/int-channel2.png)

## Définir des règles de canal

Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également spécifier la durée [d’engagement du](/help/components/c-marketing-channels/visitor-engagement.md) visiteur.

Adobe fournit plusieurs canaux prédéfinis lors d’une configuration [](/help/components/c-marketing-channels/c-getting-started-mchannel.md) automatique que vous pouvez modifier en fonction de vos besoins. De plus, vous pouvez modifier cette configuration et définir des règles personnalisées dans les règles [de traitement](/help/components/c-marketing-channels/c-rules.md)Marketing Canal.

>[!NOTE]
>
>Adobe conseille de définir le rapport dans une suite de rapports à utiliser comme modèle pour les tests. Le modèle sera ensuite utilisé pour appliquer les ensembles de canaux et de règles globalement à une ou plusieurs suites de rapports de production.
>
>Reportez-vous à la section [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

