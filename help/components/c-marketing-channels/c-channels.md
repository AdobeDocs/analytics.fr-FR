---
description: Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans marketing, une configuration automatique vous permet de créer plusieurs  pour vous, ainsi que leurs règles. Vous pouvez modifier des  prédéfinies en fonction de vos besoins ou créer les vôtres (jusqu’à 25 au total).
subtopic: Marketing channels
title: Gestion des canaux marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gestion des canaux marketing

Ajoutez ou activez des canaux marketing dans le Gestionnaire de canaux marketing. Dans le cas des suites de rapports sans marketing, une configuration automatique vous permet de créer plusieurs  pour vous, ainsi que leurs règles. Vous pouvez modifier des  prédéfinies en fonction de vos besoins ou créer les vôtres (jusqu’à 25 au total).

Voici quelques conseils pour créer des  de :

* Planifiez l&#39;avance en faisant un  de tous vos  de, de sorte que tous vos accès desoient classés selon la bonne .
* Incluez toujours des  pour le des accès [internes](/help/components/c-marketing-channels/c-faq.md) et [directs](/help/components/c-marketing-channels/c-faq.md) .

L’ajout d’ à la [!UICONTROL Marketing Channels] page s’effectue indépendamment de la création de règles sur la page Règles [de traitement des](/help/components/c-marketing-channels/c-rules.md) demarketing. Vous associez des règles aux  de lors de la création de la règle.

## Ajout de canaux marketing {#add-mktg-channels}

Ajoutez des canaux marketing dans le Gestionnaire de canaux marketing.

>[!NOTE] Il est impossible de supprimer un canal. Si vous ne souhaitez pas utiliser un canal, vous pouvez le désactiver ou le renommer, et le conserver pour une utilisation ultérieure.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Sur la [!UICONTROL Report Suite Manager] page, sélectionnez une suite de rapports.

   Si vous sélectionnez plusieurs suites de rapports, sélectionnez un modèle qui copie les paramètres du modèle vers les suites de rapports sélectionnées.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Cliquez sur **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   La page [Configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md) s’affiche si aucun canal n’est défini dans votre suite de rapports.

1. Sur la [!UICONTROL Marketing Channel Manager] page, cliquez sur **[!UICONTROL Add Channel]**.

   Cette option n’est pas disponible lorsque 25 canaux ont été définis.

1. Cliquez sur **[!UICONTROL Save.]**
1. Pour configurer les règles du , cliquez sur **[!UICONTROL Marketing Channel Processing Rules]**.

   Reportez-vous à la section [Création de règles de traitement des canaux marketing](/help/components/c-marketing-channels/c-rules.md).

## Gestionnaire de canaux marketing - Définitions de l’interface {#mktg-channel-mgr}

Définition des champs de la [!UICONTROL Marketing Channel Manager] page.

| Champ | Définition |
|--- |--- |
| Activé | Active ou désactive cette  marketing. |
| Nom du canal | Nom convivial du marketing. |
| Remplacer le canal Dernière touche | Vous permet de choisir de remplacer un Dernière touche persistant existant par le sélectionné. Si vous cochez cette case, tout  de (y compris Direct et Interne) remplacera un Dernière touche existant. La conversion est alors attribuée à un qui ne mérite peut-être pas d’être crédité. Par exemple, cette option permet de s’assurer que le  Direct ne reçoit pas de crédit pour la conversion si l’utilisateur a déjà été acquis via le de recherche naturelle. |
| Décomposition de canal | Permet de ventiler un  par cette valeur. Vous pouvez ajouter d’éventuelles ventilations de  (sous-canaux) lors de la création de classifications [de](/help/components/c-marketing-channels/classifictions-mchannel.md)marketing. |
| Type | Indique comment l’utilisateur est venu sur votre site. Vous pouvez sélectionner En ligne ou Hors ligne. Utilisez le en ligne pour les qui passent par un moteur de recherche ou une campagne par courriel. Les  hors ligne s’appliquent aux qui ont trouvé votre site par l’intermédiaire de coupons de journaux ou de publicités dans des magazines. Les  hors ligne incluent généralement les données importées par l’intermédiaire de  sources de données. Voir [Sources de données](https://docs.adobe.com/content/help/fr-FR/analytics/import/data-sources/datasrc-home.html). Voir [ Ajout de données hors ligne](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Couleur | Couleur associée à ce marketing. Cette couleur représente le canal sur le rapport Canal marketing. |

## Définir 

Avant de pouvoir afficher les données de  et de  de dans le rapport, vous devez créer le  et les règles sous-jacentes qui traitent les données. Vous pouvez également créer des montants de coût et de budget pour les  de associées et spécifier la durée d’engagement du. Vous effectuez des  de configuration de rapport dans les Outils d’administration.

Imaginez un comme un  pour les visites. Les règles attribuent des visites à la  appropriée.

![](assets/buckets_2.png)

Adobe fournit plusieurs canaux prédéfinis au cours d’une  [configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md), que vous pouvez modifier en fonction de vos besoins.

>[!NOTE]
>
>Adobe conseille de définir le rapport dans une suite de rapports à utiliser comme modèle pour les tests. Vous pouvez utiliser ce modèle pour appliquer globalement des  et des jeux de règles à une ou plusieurs suites de rapports de production.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Conditions préalables {#prereqs}

En cas de besoin, contactez l’assistance clientèle pour obtenir de l’aide au sujet des conditions préalables :

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   Pour plus d’informations, consultez la section [Paramètres généraux du compte](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/general-acct-settings-admin.html) dans l’aide d’Analytics.

* Configurez l’accès aux dimensions du marketing .

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### Remarques importantes concernant le traitement {#important-proc-rules}

* Le système traite les règles dans l’ordre indiqué. Lorsqu’une règle est respectée, le système arrête de traiter les règles restantes.
* Les règles peuvent accéder aux variables que VISTA a définies, mais pas aux données que VISTA a supprimées.
*  ne stockent que les mesures de conversion. Les mesures de trafic ne sont pas disponibles.
* Deux marketing ne reçoivent jamais de crédit pour le même  de (achats ou clics, par exemple). De cette manière, les  marketing diffèrent des eVars (où deux eVars peuvent recevoir du crédit pour le même  de).
* Le rapport peut traiter jusqu’à 25  à la fois.

