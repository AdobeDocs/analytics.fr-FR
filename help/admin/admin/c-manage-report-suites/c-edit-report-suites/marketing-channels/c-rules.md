---
title: Règles de traitement des canaux marketing
description: Les règles de traitement des canaux marketing déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal. Les règles traitent tous les accès qu’un visiteur effectue sur votre site. Si une règle ne satisfait pas les critères d’un canal, ou si les règles ne sont pas configurées correctement, le système affecte l’accès à « Aucun canal identifié ».
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: 09c1484f3f1f1a7f5e25aa24a333dbaabb4dc9d0
workflow-type: tm+mt
source-wordcount: '1878'
ht-degree: 91%

---

# Règles de traitement des canaux marketing

Les règles de traitement des canaux marketing déterminent si un accès visiteur satisfait les critères affectés à un canal en traitant chaque accès visiteur sur votre site. Les règles sont traitées dans l’ordre spécifié et, lorsqu’une règle est vérifiée, le système cesse le traitement des règles restantes.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Canaux marketing]** > **[!UICONTROL Règles de traitement des canaux marketing]**.

![](assets/buckets_2.png)

Remarques supplémentaires sur le traitement :

* Les données collectées avec ces règles sont permanentes. Les règles modifiées après la collecte de données ne sont pas rétroactives. Adobe vous conseille vivement d’étudier toutes les possibilités et de les prendre en compte avant d’enregistrer les [!UICONTROL règles de traitement des canaux marketing] afin de limiter la collecte de données dans des canaux incorrects.
* Vous pouvez configurer jusqu’à 25 canaux marketing distincts.
* Les règles peuvent accéder aux variables que VISTA a définies, mais pas aux données que VISTA a supprimées.
* Un même événement (tel qu’un achat ou un clic) n’est jamais porté au crédit de deux canaux marketing. En cela, les canaux marketing diffèrent des eVars (car deux eVars peuvent recevoir le crédit d’un seul et même événement).
* En cas de manque de couverture de vos règles, il est possible qu’[aucun canal ne soit identifié](/help/components/c-marketing-channels/c-faq.md).

## Conditions préalables

* Consultez les informations conceptuelles dans la section [Prise en main des Canaux marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
* Créez un ou plusieurs canaux auxquels attribuer des règles. Reportez-vous à la section [Ajouter des canaux marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).
* Examinez les bonnes pratiques relatives à l’utilisation des [!UICONTROL canaux marketing] avec [!UICONTROL Attribution].

## Création de règles de traitement des canaux marketing

Créez des règles de traitement des canaux marketing qui déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
2. Sélectionnez une suite de rapports.

   La page [!UICONTROL Canaux marketing : Configuration automatique] s’affiche si aucun canal n’est défini dans votre suite de rapports.

   Voir [Exécuter la configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

3. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Canaux marketing]** > **[!UICONTROL Règles de traitement des canaux marketing]**. Si vous avez exécuté la configuration automatique, un ensemble de canaux et de règles a été automatiquement défini pour vous.

   ![Résultat de l’étape](assets/marketing_channel_rules.png)

4. Si vous souhaitez ajouter une nouvelle règle, sélectionnez un type dans le menu **[!UICONTROL Ajouter un nouveau jeu de règles]**. Si vous sélectionnez un canal, un modèle de règle vous est attribué et si vous sélectionnez Personnalisé, vous démarrez à partir d’une ardoise vide. Les deux options vous permettent de modifier le jeu de règles selon vos besoins.

   ![Résultat de l’étape](assets/example_email.png)

5. Pour continuer à créer des règles, cliquez sur **[!UICONTROL Ajouter un nouveau jeu de règles]**.
6. Pour classer les règles par priorité, faites-les glisser à l’emplacement souhaité.
7. Cliquez sur **[!UICONTROL Enregistrer]**.

### Définir la valeur d’un canal marketing

**[!UICONTROL Définir la valeur du canal]** définit la dimension détaillée du canal marketing disponible pour ce canal.

### Critères de règle

Ce tableau de référence définit les champs, options et attributs d’accès que vous pouvez utiliser pour définir les règles de traitement des canaux marketing.

>[!NOTE]
>
>Tout champ de texte que vous définissez, tel que le paramètre de chaîne de requête ou les listes de valeurs à comparer, est évalué sous forme de valeurs **insensibles à la casse**. Par exemple, si vous avez une règle où le paramètre de chaîne de requête est `cmp = abc123`, toutes les variantes majuscules et minuscules de `cmp` et `abc123` correspondent.

| Terme | Définition |
|--- |--- |
| Tous | N’active ce canal que lorsque tous les critères de la règle sont vrais. |
| Tous | Active ce canal lorsqu’au moins un des critères de la règle est vrai. Cette option n’est disponible que s’il existe plusieurs critères dans la règle. |
| ID AMO | Code de suivi principal utilisé par les intégrations Adobe Advertising et Advertising Analytics. Lorsque l’une de ces intégrations est activée, le préfixe de code de suivi peut être utilisé pour identifier les canaux spécifiques à Advertising. Utilisez un &quot;AMO ID&quot; commençant par &quot;AL&quot; pour Search and Social ou &quot;AC&quot; pour Display. Lorsque l’AMO ID est utilisé dans les canaux marketing, les mesures de clics/coûts/impressions peuvent être attribuées au canal approprié. Lorsque l’AMO ID n’est pas configuré, ces mesures sont définies sur Direct ou Aucun. |
| AMO EF ID | Code de suivi secondaire utilisé par Adobe Advertising. Le principal objectif de ce code de suivi est de servir de clé pour renvoyer les données à Advertising. Il peut toutefois également être utilisé pour identifier les clics publicitaires et les affichages publicitaires comme deux canaux marketing distincts. Pour ce faire, définissez la logique du canal marketing pour &quot;AMO EF ID&quot; se termine par `:d` pour les clics publicitaires ou &quot;AMO EF ID&quot; se termine par `:i` pour les affichages publicitaires. Si vous ne souhaitez pas diviser Affichage en deux canaux, utilisez plutôt la dimension AMO ID. |
| Variables de conversion | Comprend des variables eVar activées pour cette suite de rapports et ne s’applique que lorsque ces variables sont définies au moyen du code Adobe sur la page. |
| Existe | Plusieurs sélections sont disponibles, notamment :<ul><li>**N’existe pas** : indique que l’attribut de visite n’existe pas pour la demande. Dans un domaine référent par exemple, si l’utilisateur saisit une URL ou clique sur un signet, l’attribut de domaine référent n’existe pas.</li><li>**Est vide** : indique que l’attribut de visite existe, généralement sous la forme d’un paramètre de chaîne de requête ou eVar, mais qu’aucune valeur associée à l’attribut de visite n’est attribuée.</li><li>**Ne contient pas** : permet d’indiquer, par exemple, qu’un domaine référent ne contient pas de valeur spécifique (contrairement à l’utilisation de l’option « Contient »).</li></ul> |
| Identifier le canal comme | Associe la règle à un canal marketing ajouté à la page Gestionnaire de canaux marketing. |
| Fait correspondre les règles de détection des recherches payées | Une recherche payante détectée par Adobe. Lors des recherches payantes, les sociétés paient une somme au moteur de recherche pour répertorier leur site. Les recherches payantes figurent habituellement en haut ou à droite des résultats de la recherche. |
| Fait correspondre les règles de détection des recherches naturelles | Une recherche non payante détectée par Adobe. |
| Le référent correspond aux filtres d’URL internes | Une visite dont l’URL de page correspond à un filtre d’URL interne, tel qu’il est défini pour la suite de rapports dans les Outils d’administration. |
| Le référent ne correspond pas aux filtres d’URL internes | L’URL référente ne correspond pas à un filtre d’URL interne, tel qu’il est défini pour la suite de rapports dans les Outils d’administration. Vous pouvez utiliser ce paramètre avec URL de la page et Existe afin de configurer une règle fourre-tout, de telle sorte qu’aucune visite ne figure dans la section Aucun canal identifié du rapport. |
| Ignorer les visites correspondant aux filtres URL internes | (Pour les référents) Effectue uniquement le suivi des visites provenant de sites externes. En règle générale, ce paramètre doit rester activé, à moins que vous ne souhaitiez inclure le trafic interne. |
| Est la première page de la visite | La première page d’une visite détectée par Adobe. |
| Page | Dimension [Page](/help/components/dimensions/page.md). |
| Domaine de page | Le domaine de la page à laquelle accède le visiteur, tel que `products.example.com`. |
| Domaine et chemin de page | Domaine et chemin d’accès, comme par exemple `products.example.com/mens/pants/overview.html`. |
| Domaine racine de page (TLD+1) | Domaine racine de la page à laquelle accède le visiteur, tel que exemple.co.uk . |
| URL de la page | L’URL d’une page Web de votre site. |
| Domaine référent | Dimension [Domaine référent](/help/components/dimensions/referring-domain.md) |
| Paramètre de chaîne de requête | Utilisez un paramètre de chaîne de requête individuel. Vous ne pouvez spécifier qu’un seul paramètre de chaîne de requête par critère. Pour ajouter des paramètres de chaîne de requête supplémentaires, utilisez `ANY` comme opérateur, puis ajoutez les paramètres de chaîne de requête à la règle. |
| Référent | L’emplacement de la page Web (adresse URL complète) sur laquelle vos visiteurs se trouvaient avant de consulter votre site. Il existe un référent en dehors de votre domaine défini. |
| Domaine et chemin référents | Une concaténation de « Domaine référent » et « Chemin d’accès à l’URL ». Voici quelques exemples :    `www.example.com/products/id/12345` ou `ad.example.com/foo` |
| Paramètre de référent | Un paramètre de chaîne de requête sur l’URL de renvoi. Par exemple, si vos visiteurs proviennent de `example.com/?page=12345&cat=1`, alors « page » et « chat » sont les paramètres référents. |
| Domaine racine référent | Le domaine racine du référent. Il existe un référent en dehors de votre domaine défini. |
| Moteur de recherche | Moteur de recherche, tel que Google ou Yahoo!, qui a dirigé les visiteurs sur votre site. |
| Mots-clés de recherche | Mot utilisé dans une recherche en utilisant un moteur de recherche. |
| Moteur de recherche - Mots-clés | Une concaténation de « Mot-clé de recherche » et de « Moteur de recherche » pour identifier avec exactitude le moteur de recherche. Par exemple, si vous cherchez le mot « ordinateur », le moteur de recherche et le mot-clé sont identifiés comme suit : `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Note :** n = naturel; p = payant |
| Définir la valeur du canal comme | Définit la dimension [Détails du canal marketing](/help/components/dimensions/marketing-detail.md). Vous déterminez la valeur la mieux adaptée au contexte de la règle. Par exemple, l’identifiant de bannière publicitaire, le mot-clé de recherche ou la campagne par e-mail. |

## Définitions et ordre des règles de canal marketing {#channel-rules}

Les règles de canal sont traitées dans l’ordre indiqué. Adobe recommande de placer les canaux payants ou gérés en premier (tels que : référencement payant, référencement naturel, affichage ou email) afin qu’ils soient privilégiés par rapport aux canaux organiques (tels que les domaines directs, internes, référents).

Vous trouverez ci-dessous l’ordre recommandé pour les règles de canal, ainsi que des exemples de définitions :

### Référencement payant {#paid-search}

Un référencement payant est un mot ou une expression pour qui vous payez un moteur de recherche pour apparaître dans les résultats de la recherche. Ce canal est généralement défini en fonction du paramètre de chaîne de requête (voir l’exemple Affichage de canal) ou des règles de détection de référencement payant.

#### Détection de recherche payante

Pour créer une correspondance avec les règles de détection de recherche payante, le canal marketing utilise les paramètres configurés sur la page [!UICONTROL Détection de recherche payante]. ( **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Détection de recherche payée]**). L’URL de destination correspond à la règle de détection de la recherche payante existante pour ce moteur de recherche.

Pour la règle du canal marketing, les paramètres de la [!UICONTROL recherche payante] sont les suivants :

![](assets/example_paid_search.png)

Pour plus d’informations, reportez-vous à la section [Détection de référencement payant](../general/paid-search-detection/paid-search-detection.md).

### Référencement naturel {#natural-search}

Un référencement naturel est comptabilisé quand les visiteurs et visiteuses trouvent votre site Internet à la suite d’une recherche sur le web, où le moteur de recherche a classé votre site sans que vous ayez eu à payer pour figurer dans la liste.

Adobe détermine le trafic de recherche en fonction d’une recherche interne des moteurs de recherche. Si un référent correspond aux critères d’un moteur de recherche, il détermine s’il est payant ou naturel en utilisant les règles [Détection de référencement payant](../general/paid-search-detection/paid-search-detection.md) que vous avez configurées. Un accès est considéré comme un référencement naturel lorsqu’il ne correspond à aucune règle de détection de référencement payant.

Pour la règle du canal marketing, les paramètres de la recherche naturelle sont les suivants :

![](assets/example_natural_search.png)

### Afficher  {#display}

Cette règle identifie les visiteurs et visiteuses provenant de bannières publicitaires. Elle est identifiée par un paramètre de chaîne de requête dans l’URL de destination, dans ce cas *`Ad_01`* : Le paramètre de chaîne de requête et les valeurs recherchées sont évalués en tant que valeurs insensibles à la casse.

![](assets/example_display.png)

### Courriel  {#email}

Cette règle identifie les visiteurs provenant de campagnes par e-mail. Elle est identifiée par un paramètre de chaîne de requête dans l’URL de destination, dans ce cas *`eml`* :

![](assets/example_email.png)

### Affilié  {#afilliates}

Cette règle identifie les visiteurs envoyés par un ensemble donné de domaines référents. Faites figurer dans la règle la liste des domaines d’affiliés dont vous souhaitez effectuer le suivi, de la manière suivante :

![](assets/example_affiliates.png)

### Autres campagnes {#other-campaigns}

Une bonne pratique consiste à inclure un canal « Autres campagnes » qui suit toutes les règles de canal payant. Ce canal sert de fourre-tout pour le trafic payant non classé.

![](assets/other-campaigns.png)

### Réseaux sociaux   {#social-networks}

Cette règle identifie les visiteurs et visiteuses provenant d’un réseau social, tel que Facebook. Le canal est souvent renommé Social organique. Les paramètres peuvent être les suivants :

![](assets/example_social.png)

### Canal interne (Actualisation de session) {#internal}

Cette règle s’applique aux visiteurs dont l’URL de référence correspond aux filtres d’URL internes configurés dans l’Admin Console, ce qui signifie que la visite a commencé depuis ce même site. Ce canal est souvent renommé Actualisation de session.

![](assets/int-channel1.png)

Pour plus d’informations sur ce canal, consultez [Raisons d’utiliser le canal interne (actualisation de session)](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-faq.html?lang=fr#internal).

### Direct  {#direct}

Cette règle identifie les visiteurs sans domaine référent, dont les visiteurs venus sur votre site directement, depuis un lien Favoris ou en collant un lien dans leur navigateur, par exemple. Ce canal est souvent renommé Tapé/marqué directement.

![](assets/example_direct.png)

### Canal de domaine référent {#referring-domains}

Le canal de domaine référent identifie les visiteurs avec domaine référent. Ensemble, les canaux internes, directs et de domaine référent agissent comme un fourre-tout pour tous les accès qui n’ont pas encore été classés dans un canal.

![](assets/referring-domains.png)
