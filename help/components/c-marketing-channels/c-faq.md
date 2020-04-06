---
description: Découvrez les bonnes pratiques et les exemples utilisables pour renseigner les différentes règles que vous pouvez configurer pour vos canaux marketing.
title: FAQ et exemples sur les  marketing
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# FAQ et exemples sur les  marketing

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## Questions fréquentes {#faq}

Chaque implémentation des règles de traitement des  marketing peut différer, selon vos codes de suivi. La configuration de règles qui fournissent les résultats que vous recherchez peut nécessiter une réflexion créative pour résoudre les problèmes.

**Question**: Mes codes de suivi ne suivent pas de schéma, et j&#39;en ai des milliers qui doivent être spécifiées pour mes  affiliés.

* Utilisez le processus d&#39;élimination. Si votre de courriels et d’affiliés  utilisent le même paramètre de chaîne de  de, mais que vous ne disposez que de quelques codes , vous pouvez spécifier les codes de dans un jeu de règles définissant le courrier électronique. Vous classez ensuite tous les autres codes de suivi avec  *`affiliates.`*
* Dans votre système de messagerie, ajoutez un paramètre de chaîne de requête à toutes les URL de page d’accueil, comme *`&ch=eml`*. Créez un ensemble de règles qui détectera si le paramètre de requête ch est égal à *`eml`*. S’il ne contient pas *`eml`*, il s’agit d’un affilié.

**Question** : les domaines référents contiennent plus de données que prévu.

* Les domaines référents peuvent être trop élevés dans le  de règles de traitement. Il doit s’agir de l’un des derniers ensembles de règles (ou du dernier), car l’ordre de traitement est important.

**Question**: J&#39;ai créé une règle qui correspond à un paramètre de chaîne de  et elle ne fonctionne pas.

* Assurez-vous que le nom du paramètre est spécifié dans les champs de paramètre de chaîne de  (généralement une valeur alphanumérique). Assurez-vous également que la valeur du paramètre est spécifiée après l’opérateur, comme illustré dans l’exemple suivant d’une règle de courrier électronique.

   ![](assets/example_email.png)

**Question**: Pourquoi tout mon trafic Dernière touche est-il attribué à un domaine interne ?

* Vous disposez d’une règle qui correspond au trafic interne. Gardez à l’esprit que ces règles traitent chaque accès qu’un effectue sur votre site, et pas seulement la première visite. Dans le cas d’une règle telle que  *`Page URL exists`* sans aucun autre critère, une correspondance est établie avec ce canal lors de chaque visite successive sur votre site, car il existe toujours une URL de page.

**Question**: Comment déboguer le trafic qui s’affiche dans  Aucun identifié sur le rapport ?

*  Les règles sont traitées dans l’ordre. Si aucun critère spécifique ne correspond, les accès sont classés dans l’un des trois  de suivants :

1. Aucun référent (visite directe).

2. Référent interne, sur la première page de la visite.

3. Défaut de traitement sur la page.

Assurez-vous de disposer d’un  pour ces trois possibilités. Par exemple, créez des règles qui disent :

1. **[!UICONTROL Referrer]** et **[!UICONTROL Does Not Exist]** et **[!UICONTROL Is First Page of Visit]**. (Voir [Direct.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Referrer Matches Internal URL Filters]** et **[!UICONTROL Is First page of Visit]**. (Voir [Interne](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referrer]** et **[!UICONTROL Exists]** et **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Enfin, créez un canal *Other* qui capture les autres accès, comme indiqué dans la section [Aucun canal identifié](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Aucun canal identifié  {#no-channel-identified}

When your rules do not capture data, or if rules are not configured correctly, the report displays the data in the [!UICONTROL No Channel Identified] row on the report. Vous pouvez créer un jeu de règles appelé *Autre*, par exemple, à la fin de l’ordre de traitement, qui identifie également le trafic interne.

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. Veillez à ne pas créer de règles identifiant également le trafic interne. Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

>[!NOTE] Il est possible qu’une certaine partie du trafic de canaux soit classée dans la catégorie Aucun canal identifié. Par exemple : un visiteur sur le site marque une page comme favori puis, au cours de la même visite, revient sur cette page en passant par les favoris. Puisqu’il ne s’agit pas de la première page de la visite, elle n’ira ni dans le  direct, ni dans l’autre  car il n’y a pas de domaine référent.

## Recherche payante {#paid-search}

Une recherche payante est un mot ou une expression que vous payez à un moteur de recherche pour le placer dans les résultats de la recherche. To match paid search detection rules, the marketing channel uses settings configured on the [!UICONTROL Paid Search Detection] page. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). L&#39;URL de destination correspond à la règle de détection de recherche payante existante pour ce moteur de recherche.

Pour la règle  du marketing, les [!UICONTROL Paid Search] paramètres sont les suivants :

![](assets/example_paid_search.png)

Pour plus d’informations, voir Détection [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) de recherche payante dans Admin.

## Recherche naturelle  {#natural-search}

Une recherche naturelle se produit lorsque les trouvent votre site Web par le biais d&#39;une recherche Web, où le moteur de recherche a classé votre site sans que vous ayez à payer pour la liste. Vous pouvez contrôler l&#39;URL de destination utilisée par le moteur de recherche pour créer un lien vers votre site. ce qui permet à Analytics de déterminer si une recherche est naturelle.

Il n’existe aucune détection de recherche naturelle dans Analytics. Après avoir configuré la détection de recherche payante, le système sait que si un de recherche n’était pas un  de recherche payante, il doit s’agir d’un  de recherche naturelle. Pour une recherche naturelle, l&#39;URL de destination ne correspond pas à la règle de détection de recherche payante existante pour ce moteur de recherche.

Pour la règle  du marketing, les paramètres de recherche naturelle sont les suivants :

![](assets/example_natural_search.png)

Pour plus d’informations, voir Détection [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) de recherche payante dans Admin.

## Affilié  {#afilliates}

Une règle d’affilié identifie les visiteurs envoyés par un ensemble donné de domaines référents. Dans la règle, vous  les domaines des affiliés dont vous souhaitez effectuer le suivi, comme suit :

![](assets/example_affiliates.png)

## Réseaux sociaux  {#social-networks}

Cette règle identifie les provenant d’un réseau social, tel que Facebook*. Les paramètres peuvent être les suivants :

![](assets/example_social.png)

## Afficher  {#display}

Cette règle identifie les visiteurs provenant de bannières publicitaires. Elle est identifiée par un paramètre de chaîne de requête dans l’URL de destination, dans ce cas  *`Ad_01`*.

![](assets/example_display.png)

## Interne {#internal}

Cette règle identifie les visiteurs renvoyés par un référent qui correspond aux filtres d’URL internes de la suite de rapports.

![](assets/example_internal.png)

## Courriel  {#email}

Pour configurer cette règle, indiquez le paramètre de chaîne de requête de votre campagne par courriel. Dans cet exemple, le paramètre est  *`eml`* :

![](assets/example_email.png)

Si votre règle contient Codes de suivi, entrez une valeur par ligne, comme illustré ici :

![](assets/tracking_code.png)

## Direct  {#direct}

Cette règle identifie les qui n’ont aucun domaine référent. Cette règle inclut les qui se rendent directement sur votre site, par exemple à partir d’un lien Favoris ou en collant un lien dans leur navigateur.

![](assets/example_direct.png)

