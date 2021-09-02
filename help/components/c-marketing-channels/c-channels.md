---
description: Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans canaux marketing, une configuration automatique vous permet de créer plusieurs canaux, ainsi que leurs règles. Vous pouvez modifier les canaux prédéfinis en fonction de vos besoins, ou créer vos propres canaux (avec un maximum de 25 canaux).
subtopic: Marketing channels
title: Gestion des canaux marketing
feature: Concepts de base de Reports & Analytics
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
source-git-commit: 2a63ff1072964df823edd09d844630e99c0afd8b
workflow-type: ht
source-wordcount: '750'
ht-degree: 100%

---

# Gestion des canaux marketing

>[!NOTE]
>
>Afin d’optimiser l’efficacité des canaux marketing pour Attribution IQ et Customer Journey Analytics, nous avons publié quelques [bonnes pratiques révisées](/help/components/c-marketing-channels/mchannel-best-practices.md).

Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans canaux marketing, une configuration automatique vous permet de créer plusieurs canaux, ainsi que leurs règles. Vous pouvez modifier les canaux prédéfinis en fonction de vos besoins, ou créer vos propres canaux (avec un maximum de 25 canaux).

L’ajout de canaux à la page [!UICONTROL Canaux marketing] est indépendant de la création de règles sur la page [Règles de traitement des canaux marketing](/help/components/c-marketing-channels/c-rules.md). Vous associez des règles aux canaux lors de la création de règles.

Voici quelques consignes concernant la création de canaux :

* Planifiez en dressant la liste de tous vos canaux afin que tous les accès des visiteurs soient classés dans le canal approprié.
* Incluez les canaux pour les catégories d’accès [interne](/help/components/c-marketing-channels/c-rules.md) et [direct](/help/components/c-marketing-channels/c-rules.md).
* Incluez un canal fourre-tout « Autres campagnes », à placer après les canaux payants et avant les canaux organiques.


## Conditions préalables {#prereqs}

* Configuration de l’accès aux dimensions du Canal marketing.

   Voir [autorisations des canaux marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

## Ajout de canaux marketing {#add-mktg-channels}

Ajoutez des canaux marketing dans le Gestionnaire de canaux marketing.

>[!NOTE]
>
>Il est impossible de supprimer un canal. Si vous ne souhaitez pas utiliser un canal, vous pouvez le désactiver ou le renommer, et le conserver pour une utilisation ultérieure.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sur la page [!UICONTROL Gestionnaire de Report Suites], sélectionnez une suite de rapports.

   Si vous sélectionnez plusieurs suites de rapports, choisissez un modèle à partir duquel copier les paramètres vers les suites de rapports sélectionnées.

   Voir   [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Canaux marketing]** > **[!UICONTROL Gestionnaire de canaux marketing]**.

   La page [Configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md) s’affiche si aucun canal n’est défini dans votre suite de rapports.

1. Sur la page [!UICONTROL Gestionnaire de canaux marketing], cliquez sur **[!UICONTROL Ajouter un canal]**.

   Cette option n’est pas disponible lorsque 25 canaux ont été définis.

1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Pour configurer les règles pour le canal, cliquez sur **[!UICONTROL Règles de traitement des canaux marketing]**.

   Reportez-vous à la section [Création de règles de traitement des canaux marketing](/help/components/c-marketing-channels/c-rules.md).

## Application des paramètres de canal {#mktg-channel-mgr}

Plusieurs paramètres peuvent être appliqués à chaque canal sur la page [!UICONTROL Gestionnaire de canaux marketing].

| Champ | Définition |
|--- |--- |
| Activé | Active ou désactive ce canal marketing. |
| Nom du canal | Nom convivial du canal marketing. |
| Remplacer le canal Dernière touche | Cette option vous permet d’indiquer si un canal Dernière touche persistant doit être remplacé ou non par le canal sélectionné. Si vous activez cette case à cocher, un canal quelconque (y compris Direct et Interne) remplacera un canal Dernière touche existant. Cela se traduit par l’attribution d’une conversion à un canal qui ne doit peut-être pas bénéficier de crédit. Par exemple, cette option peut garantir que le canal Direct n’a pas reçu de crédit pour la conversion si l’utilisateur provenait précédemment du canal Recherche naturelle. |
| Ventilation de canal | Permet de ventiler un canal en fonction de cette valeur. Vous pouvez ajouter d’éventuelles ventilations (sous-canaux) lors de la création des [classifications de canal marketing](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Type | Indique comment l’utilisateur est parvenu sur votre site. Vous pouvez sélectionner En ligne ou Hors ligne. Utilisez des canaux en ligne pour les visiteurs qui viennent par l’intermédiaire d’un moteur de recherche ou d’une campagne par courriel. Les canaux hors connexion s’appliquent aux visiteurs qui ont trouvé le site par l’intermédiaire de bons dans les journaux ou de publicités dans des magazines. Les canaux hors connexion incluent habituellement les données importées depuis les Sources de données des rapports. Voir [Sources de données](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=fr). Voir [Ajout de données hors ligne](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Couleur | Reports &amp; Analytics uniquement : couleur associée à ce canal marketing. Cette couleur représente le canal sur le rapport Canal marketing. |

### Bonnes pratiques : le remplacement

Il est recommandé de désélectionner l’option de remplacement Dernière touche pour les canaux Directs et Internes, afin qu’ils ne puissent pas s’attribuer le crédit d’autres canaux Dernière touche persistants (ou les uns des autres).

![](assets/int-channel2.png)

## Définition des règles de canal

Avant de pouvoir afficher les canaux et leurs données dans le rapport, créez les canaux et les règles sous-jacentes qui traitent les données. Vous pouvez également spécifier la [durée d’engagement du visiteur](/help/components/c-marketing-channels/visitor-engagement.md).

Lors d’une [configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md), Adobe fournit plusieurs canaux prédéfinis que vous pouvez modifier en fonction de vos besoins. De plus, vous pouvez modifier cette configuration et définir des règles personnalisées dans les [règles de traitement des canaux marketing](/help/components/c-marketing-channels/c-rules.md).

>[!NOTE]
>
>Adobe conseille de définir le rapport dans une suite de rapports à utiliser comme modèle pour les tests. Le modèle sera ensuite utilisé pour appliquer les ensembles de canaux et de règles globalement à une ou plusieurs suites de rapports de production.
>
>Voir   [Application des paramètres d’une suite de rapports modèle à plusieurs suites de rapports](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
