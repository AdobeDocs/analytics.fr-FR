---
title: Règles de traitement des canaux marketing
description: Les règles de traitement des  marketing déterminent si un accès répond aux critères attribués à un . Les règles traitent chaque accès qu’un effectue sur votre site. Lorsqu’une règle ne répond pas aux critères d’un  de ou si les règles ne sont pas configurées correctement, le système affecte l’accès à Aucun  identifié.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Règles de traitement des canaux marketing

Les règles de traitement des  marketing déterminent si un accès répond aux critères attribués à un . Les règles traitent chaque accès qu’un effectue sur votre site. Lorsqu’une règle ne répond pas aux critères d’un  de ou si les règles ne sont pas configurées correctement, le système affecte l’accès à Aucun  identifié.

Voici quelques consignes importantes pour la création de règles :

* Triez les règles dans l’ordre dans lequel elles doivent être traitées.
* À la fin de votre , incluez une règle fourre-tout, telle que Autre. Cette règle identifie le trafic externe mais pas le trafic interne.

   Consultez la section [Aucun canal identifié.](/help/components/c-marketing-channels/c-faq.md)

>[!NOTE] Bien que ces règles n’affectent pas les rapports en dehors des canaux marketing, elles ont un impact sur la collecte de données des canaux marketing. Les données collectées à l’aide de ces règles sont permanentes. De plus, les règles modifiées après la collecte des données ne sont pas rétroactives. Il est vivement recommandé de vérifier et de prendre en compte toutes les circonstances avant de procéder [!UICONTROL Marketing Channel Processing Rules] à l’enregistrement afin d’atténuer les données collectées dans des  incorrectes.

## Conditions préalables

* Passez en revue les informations conceptuelles dans [Prise en main des](/help/components/c-marketing-channels/c-getting-started-mchannel.md)marketing.
* Créez un ou plusieurs canaux auxquels attribuer des règles. Reportez-vous à la section [Ajout de canaux marketing.](/help/components/c-marketing-channels/c-channels.md)

## Création de règles de traitement des canaux marketing

Créez des règles de traitement des canaux marketing qui déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal.

Cette procédure utilise une règle de courrier électronique comme exemple. L’exemple suppose que vous avez ajouté un de messagerie à votre de  desur la page Gestionnaire de marketing.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Sélectionnez une suite de rapports.

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Cliquez sur **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Résultat de l’étape](assets/marketing_channel_rules.png)

1. Dans le **[!UICONTROL Add New Rule Set]** menu, sélectionnez **[!UICONTROL Email]**.

   Dans le cas présent, vous ne sélectionnez pas le canal, mais le modèle qui renseigne quelques-uns des paramètres nécessaires de la règle.

   ![Résultat de l’étape](assets/example_email.png)

   Utilisez la logique booléenne (instructions if / then) pour configurer une règle. Par exemple, dans une règle de de messagerie, indiquez les paramètres ou les informations mis en évidence dans l’instruction de règle suivante :

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   Dans cet exemple, *`<value>`* est le paramètre de chaîne de requête utilisé pour votre campagne par courrier électronique, tel que *`eml`*,
1. Pour continuer à créer des règles, cliquez sur **[!UICONTROL Add Rule]**.
1. Pour classer les règles par priorité, faites-les glisser à l’emplacement souhaité.
1. Cliquez sur **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Questions fréquentes et exemples](/help/components/c-marketing-channels/c-faq.md)


## Critères de règle de marketing

Ce tableau de référence définit les champs, options et attributs de visite que vous pouvez sélectionner sur la page Règles de traitement des canaux marketing.

| Terme | Définition |
|--- |--- |
| Tous | N’active ce canal que lorsque toutes les règles de la règle numérotée sont vraies. |
| N&#39;importe quel(le) | Active cette  lorsque l’une des règles du jeu de règles est vraie. Cette option est disponible uniquement si plusieurs règles existent dans la règle numérotée. |
| ID AMO | Code de suivi principal utilisé par les intégrations Advertising Cloud et Advertising Analytics. Lorsque l’une de ces intégrations est activée, le préfixe du code de suivi peut être utilisé pour identifier les canaux spécifiques à Advertising Cloud. Utilisez « AMO ID » en commençant par « AL » pour Rechercher, « AC » pour Afficher ou « AO » pour Social. Lorsque l’AMO ID est utilisé dans les canaux marketing, les mesures de clic/coût/impression peuvent être attribuées au canal approprié (lorsqu’elles ne sont pas configurées, elles sont alors associées à Direct ou Aucun). |
| AMO ED ID | Code de suivi secondaire utilisé par Advertising Cloud. Le principal objectif de ce code de suivi est de servir de clé pour renvoyer les données vers Advertising Cloud. Il peut toutefois également être utilisé pour identifier les clics publicitaires par rapport aux affichages publicitaires si vous souhaitez les voir comme deux canaux marketing distincts. Pour ce faire, définissez la logique du canal marketing pour « AMO EF ID » se terminant par « :d » pour les clics publicitaires ou « AMO EF ID » se terminant par « :i » pour les affichages publicitaires. Si vous ne souhaitez pas diviser Affichage en deux canaux, utilisez plutôt la dimension AMO ID. |
| Variables de conversion | Se compose d’eVars activées pour cette suite de rapports et s’applique uniquement lorsque ces variables sont définies via le code Adobe de la page.  Consultez le Guide d’implémentation . |
| Existe | Plusieurs sélections sont disponibles, notamment :<ul><li>**N’existe pas** : indique que l’attribut de visite n’existe pas pour la demande. Dans un domaine référent par exemple, si l’utilisateur saisit une URL ou clique sur un signet, l’attribut de domaine référent n’existe pas.</li><li>**Est vide** : indique que l’attribut de visite existe, généralement sous la forme d’un paramètre de chaîne de requête ou eVar, mais qu’aucune valeur associée à l’attribut de visite n’est attribuée.</li><li>**Ne contient** pas : Vous permet, par exemple, de spécifier qu’un domaine référent ne contient pas de valeur spécifique (au lieu d’utiliser la sélection &quot;Contient&quot;).</li></ul> |
| Identifier le canal comme | Associe la règle à un canal marketing ajouté à la page Gestionnaire de canaux marketing.  Reportez-vous à la section Ajout de canaux marketing . |
| Fait correspondre les règles de détection des recherches payées | Une recherche payante détectée par Adobe. Lors des recherches payantes, les sociétés paient une somme au moteur de recherche pour répertorier leur site. Les recherches payantes apparaissent généralement en haut ou à droite des résultats de la recherche. |
| Fait correspondre les règles de détection des recherches naturelles | Une recherche non payante détectée par  Adobe. |
| Le référent correspond aux filtres d&#39;URL internes | Visite dont l’URL de page correspond à un filtre d’URL interne, tel que défini pour la suite de rapports dans les Outils d’administration. |
| Le référent ne correspond pas aux filtres d&#39;URL internes | L’URL de référence ne correspond pas à un filtre d’URL interne, tel que défini pour la suite de rapports dans les Outils d’administration. Vous pouvez utiliser ce paramètre avec  URL de la page  et  Existe  afin de configurer une règle fourre-tout, de telle sorte qu’aucune visite ne figure dans la section  Aucun canal identifié  du rapport. |
| Ignorer les accès correspondant au d’URL interne  | (Pour les ) Effectue uniquement le suivi des accès provenant de sites externes. En règle générale, laissez ce paramètre activé, sauf si vous souhaitez inclure le trafic interne. |
| Est la première page de la visite | Première page d’une visite détectée par le Adobe. |
| Page | Le nom d’une page web du site qui contient une balise web d’Adobe. Cette valeur équivaut à  s.pageName . Par exemple, `Home Page` et `About Us`. |
| Domaine de page | The domain of the page on which the visitor lands, such as `products.example.co.uk`. |
| Domaine et chemin de page | The domain and path, such as `products.example.co.uk/mens/pants/overview.html` . |
| Domaine racine de page (TLD+1) | Domaine racine de la page à laquelle accède le visiteur, tel que exemple.co.uk . |
| URL de la page | URL d’une page Web de votre site. |
| Domaine référent | Le domaine d’où proviennent les visiteurs avant de visiter votre site ; par exemple, les référents provenant de `abcsite.com` par rapport à `xyzsite.com`. |
| Paramètre de chaîne de requête | If a page URL on your site looks like `https://example.com/?page=12345&cat=1`, then page and cat are both query string parameters. (Reportez-vous à la section `https://en.wikipedia.org/wiki/Query_string`.)  Vous ne pouvez spécifier qu’un seul paramètre de chaîne de requête par ensemble de règles. To add additional query string parameters, use `ANY` as your operator, then add new query string parameters to the rule. |
| Referrer (Référent) | Emplacement de la page Web (URL complète) sur laquelle vos se trouvaient avant de venir sur votre site. Un  existe en dehors de votre domaine défini. |
| Domaine et chemin référents | Concaténation du domaine référent et du chemin d’accès à l’URL. Voici quelques exemples :    `www.example.com/products/id/12345` ou `ad.example.com/foo` |
| Paramètre de référent | Un paramètre de chaîne de requête sur l’URL de renvoi. For example, if your visitors come from `example.com/?page=12345&cat=1`, then page and cat are the referring parameters. |
| Domaine racine référent | Domaine racine du . Un  existe en dehors de votre domaine défini. |
| Moteur de recherche | Moteur de recherche, tel que Google ou Yahoo!, qui a amené les visiteurs sur votre site. |
| Mots-clés de recherche | Mot utilisé dans une recherche en utilisant un moteur de recherche. |
| Moteur de recherche + Mots-clés | Concaténation du mot-clé de recherche et du moteur de recherche pour identifier le moteur de recherche de manière unique. Par exemple, si vous recherchez le mot ordinateur, le moteur de recherche et le mot clé sont identifiés comme suit : `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Remarque :**n = naturelle; p = payé |
| Définir la valeur du canal comme | Outre le fait de savoir quel canal marketing dirige un visiteur sur le site, vous pouvez connaître la bannière publicitaire, le mot-clé ou la campagne par courrier électronique du canal qui reçoit le crédit de l’activité d’un visiteur sur le site. Cet ID est une valeur de  stockée avec le  de. Souvent, cette valeur est un identifiant de campagne incorporé dans le  de ou l’URL de référence ; dans d&#39;autres cas, c&#39;est la combinaison moteur de recherche et mot-clé de recherche, ou l&#39;URL de référence qui identifie le plus correctement le d&#39;un  particulier. |

## Canal interne (actualisation de session)

Le canal Interne (souvent renommé Actualisation de session) comprend les visites sur le site où l’URL de référence correspond aux filtres d’URL internes configurés dans Admin Console. Cela signifie que le visiteur a commencé sa visite depuis le site.

![](assets/int-channel1.png)

### Bonnes pratiques : le remplacement

Il est recommandé de désélectionner l’option de remplacement Dernière touche pour les canaux Directs et Internes, afin qu’ils ne puissent pas s’attribuer le crédit d’autres canaux Dernière touche persistants (ou les uns des autres).

>[!NOTE]Ce document part du principe que les paramètres de remplacement des canaux Directs et d’Actualisation de session sont désactivés.

![](assets/int-channel2.png)

### Période d’engagement

Les canaux Première touche et Dernière touche d’un visiteur sont réinitialisés après 30 jours d’inactivité sur ce navigateur.

>[!NOTE] 30 jours correspond à la valeur par défaut. Elle peut être modifiée selon les besoins via les paramètres d’administration.

Si le visiteur utilise fréquemment le site, la fenêtre d’engagement s’adaptera en fonction. Ils doivent être inactifs pendant 30 jours pour que la période arrive à expiration et que les canaux soient réinitialisés.
Exemple :

* Jour 1 : l’utilisateur accède au site par le biais de l’Affichage. Les canaux Première touche et Dernière touche seront définis sur Affichage.

* Jour 2 : l’utilisateur se rend sur le site par le biais d’une Recherche naturelle. La première touche reste sur Affichage et la dernière touche est définie sur Recherche naturelle.

* Jour 35 : l’utilisateur ne s’est pas rendu sur le site depuis 33 jours et y retourne en utilisant l’onglet qu’il a ouvert dans son navigateur. En supposant une fenêtre d’engagement de 30 jours, la fenêtre se serait fermée et les cookies Marketing Channel auraient expiré. Les canaux Première touche et Dernière touche seront réinitialisés et seront définis sur Actualisation de session puisque l’utilisateur provient d’une URL interne.

### Relation entre Première touche et Dernière touche

Pour comprendre l’interaction entre la première et la dernière touche et confirmer que les remplacements fonctionnent comme prévu, vous pouvez extraire un rapport du canal Première touche, sous-lié à un rapport du canal Dernière touche, en ajoutant votre mesure de succès clé (voir l’exemple ci-dessous). Cet exemple illustre l’interaction entre les canaux Première touche et Dernière touche.

![](assets/int-channel3.png)

L’intersection où la Première touche est égale à la Dernière touche est surlignée en orange. Les canaux Direct et Actualisation de session n’obtiennent le crédit Dernière touche que s’ils étaient également le canal Première touche, car ils ne peuvent pas obtenir de crédit d’autres canaux persistants (lignes surlignées en gris).

### Pourquoi l’Actualisation de session se produit-elle ?

Puisque nous savons que l’Actualisation de session pour la dernière touche ne peut avoir lieu que si elle était également la première touche, les scénarios ci-dessous expliquent comment l’Actualisation de session peut être un canal Première touche.

**Scénario 1 : délai d’expiration de la session**

Un visiteur se rend sur un site Web, puis laisse l’onglet ouvert dans son navigateur pour y retourner ultérieurement. La période d’engagement du visiteur expire (ou bien il supprime volontairement ses cookies) et il utilise l’onglet ouvert pour se rendre à nouveau sur le site Web. L’URL de référence étant un domaine interne, la visite est classée comme Actualisation de session.

**Scénario 2 : les pages d’un site ne sont pas toutes balisées**

Un visiteur arrive sur la page A qui n’est pas balisée, puis passe à la page B qui est balisée. La page A serait considérée comme le référent interne et la visite serait classée comme Actualisation de session.

**Scénario 3 : redirections**

Si une redirection n’est pas configurée pour transmettre les données du référent à la nouvelle page d’entrée, les données d’entrée réelle du référent sont perdues et la page de redirection (probablement une page interne) apparaît désormais comme domaine référent. La visite sera classée comme Actualisation de session.

**Scénario 4 : trafic inter-domaines**

Un visiteur passe d’un domaine qui se déclenche vers la suite A à un autre domaine qui se déclenche vers la suite B. Si, dans la suite B, les filtres d’URL internes incluent le premier domaine, la visite dans la suite B est enregistrée comme Interne, puisque les canaux marketing la considèrent comme une nouvelle visite dans la deuxième suite. La visite sera classée comme Actualisation de session.

**Scénario 5 : temps de chargement long de la page d’entrée**

Un visiteur accède à la page A, qui contient beaucoup de contenu, et le code Adobe Analytics se trouve au bas de la page. Avant que tout le contenu (y compris la demande d’images Adobe Analytics) puisse être chargé, le visiteur clique sur la page B. La page B déclenche sa demande d’images Adobe Analytics. Comme la demande d’images de la page A n’a jamais abouti, la deuxième page apparaît comme le premier accès de la visite dans Adobe Analytics, avec la page A comme référent. La visite est classée comme Actualisation de session.

**Scénario 6 : effacement des cookies durant la visite**

Un visiteur se rend sur le site et efface ses cookies durant la visite. Les canaux Première touche et Dernière touche seront réinitialisés et la visite sera classée comme Actualisation de session (car le référent est interne).
