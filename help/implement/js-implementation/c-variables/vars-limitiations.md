---
description: Aperçu détaillé des variables et de leurs restrictions.
keywords: Implémentation d'Analytics ; variable ; restrictions ; limites
seo-description: Aperçu détaillé des variables et de leurs restrictions.
seo-title: Variables et limites
solution: Analytics
subtopic: Variables
title: Variables et limites
topic: Développeur et mise en œuvre
uuid: 028677 a 7-2132-4 ee 7-9 cc 1-697 c 2 c 09 b 087
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variables et limites

Aperçu détaillé des variables et de leurs restrictions.

>[!NOTE]
>
>See [Configuration Variables](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) and [Page Variables](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) for an in-depth look at the most common Analytics variables.

Le tableau suivant fournit des informations en un coup d’œil des variables [!DNL Analytics] :

| Variable | Description |
|---|---|
| s_account | Détermine la suite de rapports dans laquelle les données sont stockées et rapportées. |
| browserHeight | Affiche la hauteur de la fenêtre du navigateur. |
| browserWidth | Affiche la largeur de la fenêtre du navigateur. |
| campaign | Identifie les campagnes marketing utilisées pour amener des visiteurs sur votre site. La valeur de la variable *`campaign`* provient généralement d’un paramètre de chaîne de requête. |
| channel | Identifie généralement une section de votre site Web. Par exemple, un site commercial peut présenter des sections telles que « Electronique », « Jouets » ou « Vêtements ». Un site de médias peut présenter des sections comme « Infos », « Sports » ou encore « Affaires ». |
| charSet | Convertit le jeu de caractères de la page Web au format UTF-8.  |
| colorDepth | Affiche le nombre de bits utilisés pour l’affichage de la couleur sur chaque pixel de l’écran. |
| connectionType | Indique (dans Microsoft Internet Explorer) si le navigateur est configuré sur une connexion LAN (réseau local) ou modem. |
| cookieDomainPeriods | Détermine le domaine sur lequel le cookie [!DNL Analytics]identifiant visiteur (s_vi) est défini en établissant le nombre de points contenus dans le domaine de l’URL de la page. For `www.mysite.com`, *`cookieDomainPeriods`* should be "2." For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3." |
| cookieLifetime | Utilisée par les serveurs [!DNL Analytics] et JavaScript pour déterminer la durée de vie d’un cookie. |
| cookiesEnabled | Indique si un cookie de session propriétaire a pu être défini par JavaScript. |
| currencyCode | Détermine le taux de conversion à appliquer aux recettes lors de leur entrée dans les bases de données d’[!DNL Analytics]. Les bases de données d’[!DNL Analytics] stockent toutes les valeurs monétaires dans la devise de votre choix. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied. |
| dc | Permet de définir le centre de données auquel vos données sont envoyées. |
| doPlugins | *`doPlugins`* est une référence à *`s_doPlugins`* la fonction. It allows the *`s_doPlugins`* function to be called at the appropriate location within the JavaScript file. |
| dynamicAccountList | Permet de sélectionner, de manière dynamique, la suite de rapports à laquelle sont envoyées les données. La variable *`dynamicAccountList`* contient les règles utilisées pour déterminer la suite de rapports de destination. |
| dynamicAccountMatch | Utilise l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles indiquées dans *`dynamicAccountList`*. This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' |
| dynamicAccountSelection | Permet de sélectionner dynamiquement la suite de rapports en fonction de l’URL de chaque page. |
| dynamicVariablePrefix | Permet au déploiement de marquer les variables qui doivent être renseignées de manière dynamique. Les cookies, en-têtes de requête et paramètres de chaîne de requête d’image peuvent être renseignés de cette manière. |
| eVarN | Utilisée pour créer des rapports personnalisés dans le [!DNL Analytics]module de conversion[!UICONTROL  d’]. Lorsqu’une eVar est définie sur une valeur pour un visiteur, [!DNL Analytics] la mémorise jusqu’à son expiration. Tout événement de succès auquel est associé un visiteur alors que la valeur eVar est active est comptabilisé dans cette dernière. |
| events | Enregistre des événements de succès courants du panier, ainsi que des événements de succès personnalisés |
| fpCookieDomainPeriods | Détermine le domaine sur lequel les cookies [!DNL Analytics] autres que l’[!UICONTROL identifiant visiteur] (s_vi) sont définis, en établissant le nombre de points contenus dans le domaine de la page. |
| hierN | Détermine l’emplacement d’une page dans la hiérarchie de votre site. Cette variable est particulièrement utile pour les sites dont la structure comprend plus de trois niveaux. |
| homepage | Indique (dans Internet Explorer) si la page active est définie comme page d’accueil de l’utilisateur. |
| javaEnabled | Indique si Java est activé dans le navigateur. |
| javascriptVersion | Affiche la version JavaScript prise en charge par le navigateur. |
| linkDownloadFileTypes | Liste d’extensions de fichiers séparées par des virgules. Si votre site contient des liens pointant vers des fichiers associés à l’une de ces extensions, les URL de ces liens s’affichent dans le rapport [!UICONTROL Téléchargements de fichiers]. |
| linkExternalFilters | Si votre site contient plusieurs liens vers des sites externes et que vous ne souhaitez pas suivre tous les liens de sortie, la variable *`linkExternalFilters`* peut être utilisée pour créer des rapports sur un sous-ensemble spécifique de liens de sortie. |
| linkInternalFilters | Détermine les liens de votre site qui sont des liens de sortie. Il s’agit d’une liste, séparée par des virgules, de filtres représentant les liens qui font partie du site. |
| linkLeaveQueryString | Détermine si la chaîne de requête doit être incluse ou non dans les rapports [!UICONTROL Liens de sortie] et [!UICONTROL Téléchargements de fichiers]. |
| linkName | Cette variable facultative, utilisée dans le [!UICONTROL suivi des liens], détermine le nom d’un lien personnalisé, de téléchargement ou de sortie. En règle générale, la variable *`linkName`* n'est pas nécessaire, car le troisième paramètre de *`tl()`* la fonction le remplace. |
| linkTrackEvents | Contient les événements qui doivent être envoyés avec des liens personnalisés, de téléchargement et de sortie. Cette variable n’est prise en compte que si *`linkTrackVars`* contient « events ». |
| linkTrackVars | Liste de variables séparées par des virgules qui seront envoyées avec les liens personnalisés, de téléchargement et de sortie. Si la variable *`linkTrackVars`* est définie sur "", toutes les variables qui comportent des valeurs sont envoyées avec des données de lien. |
| linkType | Variable facultative utilisée dans le cadre du suivi des liens. Elle détermine le rapport dans lequel un nom de lien ou une URL doit apparaître (liens personnalisés, de téléchargement ou de sortie). *`linkType`* n'est pas nécessaire, car le deuxième paramètre de *`tl()`* la fonction le remplace. |
| mediaLength | Définit la longueur totale du média en cours de lecture. |
| mediaName | Indique le nom de la vidéo ou de l’élément multimédia. Elle est uniquement disponible par le biais de l’[!UICONTROL API pour l’insertion des données] et de la [!UICONTROL source de données à traitement complet]. |
| mediaPlayer | Indique le lecteur utilisé pour exécuter une vidéo ou un élément multimédia. |
| mediaSession | Indique les segments lus d’une vidéo ou d’une ressource mutimédia. |
| Media.trackEvents | Identifie les événements qui doivent être envoyés avec un accès au média. Elle s’applique uniquement à JavaScript et [!UICONTROL ActionSource]. |
| Media.trackVars | Identifie les variables qui doivent être envoyées avec un accès au média. Elle s’applique uniquement à JavaScript et [!UICONTROL ActionSource]. |
| mobile | Contrôle l’ordre dans lequel les cookies et les identifiants d’abonnés sont utilisés pour identifier les visiteurs. |
| s_objectID | Variable globale qui doit être définie dans l’événement [!UICONTROL onClick] d’un lien. En créant un identifiant d’objet unique pour un lien ou emplacement de lien sur une page, vous pouvez améliorer le suivi de la mise en correspondance des clics des visiteurs ou utiliser la mise en correspondance des clics des visiteurs pour créer des rapports sur un emplacement ou un type de lien plutôt que sur l’URL du lien. |
| pageName | Contient le nom de chaque page de votre site. Si la variable *`pageName`* n’est pas renseignée, l’URL est utilisée pour représenter le nom de la page dans [!DNL Analytics]. |
| pageType | Utilisée uniquement pour désigner une page « Erreur 404 - Page introuvable ». Une seule valeur est possible pour cette variable, à savoir : « errorPage ». La variable *`pageName`* ne doit pas être renseignée sur une page « Erreur 404 ». |
| pageURL | Dans de rares cas, l’URL de la page diffère de celle que vous souhaiteriez voir consignée dans les rapports [!DNL Analytics]. To accommodate these situations, [!DNL Analytics] offers the *`pageURL`* variable, which overrides the actual URL of the page. |
| plugins | Dans les navigateurs Netscape et à architecture Mozilla, cette variable répertorie les modules externes (plug-ins) installés. |
| products | Utilisée pour effectuer le suivi des produits et des catégories de produits (ainsi que de la quantité achetée et du prix d’achat). La variable *`products`* doit toujours être définie conjointement avec un événement de succès. Optionally, the *`products`* variable can track custom numeric and currency events, as well as [!UICONTROL Merchandising] eVars. |
| propN | Utilisée pour créer des rapports personnalisés dans le [!DNL Analytics]module Trafic[!UICONTROL  d’]. Vous pouvez utiliser la variable [!UICONTROL props] comme compteur (pour comptabiliser le nombre d’envois d’une page vue), pour les rapports de cheminement ou dans des rapports de corrélation. |
| purchaseID | Cette variable permet d’éviter qu’une commande ne soit comptée plusieurs fois par [!DNL Analytics]. Whenever the purchase event is used on your site, you should use the *`purchaseID`* variable. |
| referrer | Restaure les informations perdues sur le référent. |
| resolution | Affiche la résolution du moniteur du visiteur de la page Web. |
| server | Affiche soit le domaine d’une page Web (pour indiquer les domaines sur lesquels arrivent les utilisateurs), soit le serveur d’où provient la page (pour une référence rapide de l’équilibrage de charge). |
| state | Capture l’état dans lequel réside un visiteur de votre site. |
| trackDownloadLinks | Définissez la variable *`trackDownloadLinks`* sur true si vous souhaitez effectuer le suivi de liens vers des fichiers téléchargeables de votre site. If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* determines which links are downloadable files. |
| trackExternalLinks | If *`trackExternalLinks`* is 'true,' *`linkInternalFilters`* and *`linkExternalFilters`* determines whether any link clicked is an exit link. |
| trackingServer | Utilisée dans le cadre de l’implémentation des cookies propriétaires, afin d’indiquer le domaine au niveau duquel sont écrits le cookie et la demande d’image. Elle est utilisée pour les pages non sécurisées.  |
| trackingServerSecure | Utilisée dans le cadre de l’implémentation des cookies propriétaires, afin d’indiquer le domaine au niveau duquel sont écrits le cookie et la demande d’image. Elle est utilisée pour les pages sécurisées.  |
| trackInlineStats | Détermine si les données de mise en correspondance des clics des visiteurs sont collectées. |
| transactionID | Relie les données hors ligne à une transaction en ligne (un prospect ou un achat généré en ligne, par exemple). Chaque variable *`transactionID`* unique envoyée à Adobe est enregistrée en vue d’un chargement de [!UICONTROL sources de données] d’informations hors ligne relatives à cette transaction. Reportez-vous au [Guide des sources de données](https://marketing.adobe.com/resources/help/en_US/sc/datasources/). |
| s_usePlugins | Si la fonction *`s_doPlugins`* est disponible et contient du code utile, [!UICONTROL la variable s_ useplugins] doit être définie sur « true ». When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request. |
| visitorID | Visitors may be identified by the *`visitorID`* tag, or by IP address/User Agent. The *`visitorID`* may be up to 100 alphanumeric characters and must not contain a hyphen. |
| visitorNamespace | If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. Elle identifie le domaine avec lequel les cookies sont définis. Si la variable *`visitorNamespace`* change, tous les visiteurs signalés dans [!DNL Analytics] peuvent devenir de nouveaux visiteurs. En résumé, ne modifiez pas cette variable sans l’accord d’un représentant Adobe. |
| zip | Capture le code postal du lieu de résidence d’un visiteur de votre site. |

