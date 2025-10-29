---
title: Règles de traitement des canaux marketing
description: Utilisez des règles pour déterminer à quel canal marketing un accès appartient.
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 3%

---

# Règles de traitement des canaux marketing

_Cette page fait référence aux règles de traitement qui attribuent un canal marketing à un accès. Voir [Règles de traitement](../general/processing-rules/pr-overview.md) pour la fonctionnalité qui vous permet d’ajuster la manière dont les données sont collectées._

Les règles de traitement des canaux marketing vous permettent de créer une logique qui détermine la valeur des dimensions [Canal marketing](/help/components/dimensions/marketing-channel.md) et [Détails du canal marketing](/help/components/dimensions/marketing-detail.md). Utilisez le [gestionnaire de canaux marketing](c-channels.md) pour déterminer les canaux marketing que vous utilisez, puis utilisez des règles de traitement pour déterminer comment chaque canal est défini.

![Intervalles de canaux marketing](assets/buckets_2.png)

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Canaux marketing]** > **[!UICONTROL Règles de traitement des canaux marketing]**

Une fois que la [configuration automatique](/help/components/c-marketing-channels/c-getting-started-mchannel.md) s’exécute, elle crée une règle pour chaque canal généré lors de la configuration.

![&#x200B; Règles par défaut &#x200B;](assets/marketing_channel_rules.png)

Vous pouvez utiliser plusieurs règles pour définir un canal marketing unique. L’utilisation de plusieurs règles pour un seul canal peut s’avérer bénéfique si vous souhaitez définir les détails du canal différemment en fonction des conditions des règles. Vous pouvez également utiliser plusieurs conditions pour définir une seule règle.

## Définitions de règle

Chaque règle contient une condition et une affectation :

* **[!UICONTROL Si toutes les conditions suivantes sont vraies]** : si vous ajoutez plusieurs conditions à une seule règle, vous pouvez déterminer si toutes les conditions doivent être remplies ou si l’une des conditions doit être remplie pour définir le canal et la valeur associée.
* **Conditions des règles** : spécifiez une ou plusieurs conditions de règle qui doivent être remplies. En règle générale, vous spécifiez une dimension à laquelle un accès doit correspondre pour être qualifié pour le canal marketing.
* **[!UICONTROL Procédez ensuite comme suit]** : lorsque les conditions de la règle correspondent, définissez [Canal marketing](/help/components/dimensions/marketing-channel.md) ([!UICONTROL Identifier le canal comme &#x200B;]) et [Détails du canal marketing](/help/components/dimensions/marketing-detail.md) ([!UICONTROL Définir la valeur du canal]).

## Conditions de la règle

Les options suivantes sont disponibles lors de la définition des conditions de la règle.

>[!NOTE]
>
>Tous les champs de texte sont évalués comme **non-respect de la casse**. Par exemple, si vous utilisez une condition de règle dans laquelle le paramètre de chaîne de requête `cmp` est égal à `abc123`, le paramètre de chaîne de requête et la valeur peuvent utiliser n’importe quelle combinaison de majuscules et de minuscules.

**Conditions détectées par Adobe** ne contiennent pas d’options ni de champs permettant de saisir du texte.

| Condition détectée par Adobe | Description |
|---|---|
| **[!UICONTROL Correspond aux règles de détection de référencement payant]** | L’accès provenait d’un moteur de recherche reconnu et correspondait [Règles de détection de référencement payant](../general/paid-search-detection/paid-search-detection.md). |
| **[!UICONTROL Correspond aux règles de détection de recherche naturelle]** | L’accès provenait d’un moteur de recherche reconnu et ne correspondait pas aux règles de détection de référencement payant. |
| **[!UICONTROL Le référent correspond aux filtres d’URL internes]** | L’accès contenait un [référent](/help/components/dimensions/referrer.md) correspondant [filtres d’URL internes](../general/internal-url-filter-admin.md). |
| **[!UICONTROL Le Référent Ne Correspond Pas Aux Filtres D’URL Internes]** | L’accès contenait un référent qui ne correspondait pas aux filtres d’URL internes. |
| **[!UICONTROL Est le premier accès de la visite]** | L’accès a été le premier d’une visite. |
| **[!UICONTROL Référent Est Un Réseau Social]** | Le [type de référent](/help/components/dimensions/referrer-type.md) est « Réseaux sociaux ». |
| **[!UICONTROL Référent N’Est Pas Un Réseau Social]** | Le type de référent n’est pas « Réseaux sociaux ». |
| **[!UICONTROL Le référent est l’IA dédiée à la conversation]** | Le type de référent est « IA dédiée à la conversation ». |
| **[!UICONTROL Le référent n’est pas l’IA dédiée à la conversation]** | Le type de référent n’est pas « IA dédiée à la conversation ». |

**Attributs d’accès** vous permet de spécifier une dimension, un opérateur correspondant et une valeur à rechercher.

| Condition d’attribut d’accès | Description |
|---|---|
| **[!UICONTROL Page]** | Dimension [Page](/help/components/dimensions/page.md). |
| **[!UICONTROL Domaine de page]** | Domaine de l’URL. Par exemple : `products.example.com`. |
| **[!UICONTROL Domaine Et Chemin D’Accès De La Page]** | Domaine et chemin de l’URL. Par exemple : `products.example.com/mens/pants/overview.html`. |
| **[!UICONTROL Domaine racine de la page]** | Domaine racine de l’URL. Par exemple : `example.co.uk`. |
| **[!UICONTROL URL de la page]** | URL de la page entière. |
| **[!UICONTROL Paramètre de chaîne de requête]** | Paramètre de chaîne de requête individuel dans l’URL de la page. Utilisez un paramètre de chaîne de requête par condition de règle. Si vous souhaitez inclure plusieurs paramètres de chaîne de requête dans une règle, utilisez plusieurs conditions de règle. |
| **[!UICONTROL Référent]** | La dimension [Référent](/help/components/dimensions/referrer.md). |
| **[!UICONTROL Domaine référent]** | La dimension [Domaine référent](/help/components/dimensions/referring-domain.md). |
| **[!UICONTROL Domaine Et Chemin De Référence]** | Une concaténation du domaine référent et du chemin d’URL du référent. Par exemple, `www.example.com/products/id/12345` ou `ad.example.com/foo`. |
| **[!UICONTROL Paramètre Référent]** | Paramètre de chaîne de requête dans le référent. |
| **[!UICONTROL Domaine racine de renvoi]** | Le domaine racine référent. |
| **[!UICONTROL Moteur de recherche]** | La dimension [&#x200B; Moteur de recherche &#x200B;](/help/components/dimensions/search-engine.md). |
| **[!UICONTROL Mot(s)-clé(s) de recherche]** | La dimension [Mot-clé de recherche](/help/components/dimensions/search-keyword.md). |
| **[!UICONTROL Moteur de recherche + mot(s)-clé(s) de recherche]** | Concaténation du moteur de recherche et du mot-clé de recherche. |
| **[!UICONTROL ID AMO]** | Code de suivi principal utilisé par les intégrations Adobe Advertising et Advertising Analytics. Lorsque l’une de ces intégrations est activée, le préfixe du code de suivi peut être utilisé pour identifier les canaux spécifiques à Advertising. Les valeurs commençant par « AL » sont pour Search et Social. Les valeurs commençant par « AC » sont pour Affichage. Lorsque l’ID AMO est utilisé dans les canaux marketing, les mesures de clic/coût/impression peuvent être attribuées au canal correct. |
| **[!UICONTROL ID EF AMO]** | Code de suivi secondaire utilisé par Adobe Advertising. Sert de clé pour renvoyer des données à Advertising. Il peut être utilisé pour identifier les clics publicitaires et les affichages publicitaires comme deux canaux marketing distincts. Pour ce faire, définissez la logique du canal marketing pour que « AMO EF ID » se termine par `:d` pour les clics d’affichage ou « AMO EF ID » se termine par `:i` pour les clics d’affichage. Si vous ne souhaitez pas diviser l’affichage en deux canaux, utilisez plutôt la dimension ID AMO . |

Les **variables de conversion** vous permettent de spécifier un eVar personnalisé, un opérateur correspondant et une valeur à rechercher.

| Condition de variable de conversion | Description |
|---|---|
| **eVar 1-250** | La dimension [eVar](/help/components/dimensions/evar.md) associée. |
