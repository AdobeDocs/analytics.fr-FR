---
description: valeur nulle
title: Advertising Analytics - Aperçu
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Advertising Analytics - Aperçu

Advertising Analytics permet d’afficher toutes vos données de référencement payant Google et Bing côte à côte dans Adobe Analytics. Auparavant, toutes les données Google AdWords/DFA ou Microsoft Bing Ads devaient être affichées dans Adobe Advertising Cloud (AMO) ou dans Google/Bing. Vous obtiendrez maintenant les données suivantes dans Adobe Analytics : Impressions, Clics, Coûts, Note de qualité et Position moyenne directement à partir des moteurs de recherche ainsi que les Instances AMO ID (cliquez sur Instances).

>[!NOTE] Yahoo Gemini a été absorbé par Microsoft Bing le 31 mars 2019. Par conséquent, l’option de compte publicitaire Yahoo Gemini n’est plus disponible.

En réunissant les données des moteurs de recherche dans Adobe Analytics, vous pouvez analyser les mêmes données en utilisant la puissance d’Analysis Workspace. Le nouveau modèle [Performance de référencement payant](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) dans Workspace facilite cette analyse.

![](assets/aa_aw.png)

Cette intégration est destinée aux   suivants :

* L’ **analyste** qui doit collecter des rapports de performances pour le spécialiste du marketing de recherche payante.
* Le spécialiste **du marketing** de recherche payante qui recherche des réponses à ces questions : Combien de trafic suis-je en train d’envoyer sur notre site et les clients sont-ils en train de se convertir ? Quelles sont les campagnes publicitaires les plus rentables ?

## Conditions préalables {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* Cette fonctionnalité est disponible pour les clients qui ne sont pas abonnés à Advertising Cloud et non-AMO.
* Vous devez être un administrateur Adobe Analytics pour avoir accès à Advertising Analytics. Par la suite, vous pouvez [accorder des autorisations](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) d’accès aux non-administrateurs.
* Toutes les suites de rapports Analytics dans lesquelles vous souhaitez afficher les données de recherche Google/Bing doivent être [mappées à votre organisation Experience Cloud](https://marketing.adobe.com/resources/help/fr_FR/mcloud/report-suite-mapping.html).
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* Vous devez disposer des informations de connexion d’un utilisateur disposant d’autorisations de modification pour le ou les comptes de recherche que vous souhaitez intégrer à Adobe Analytics, tels qu’un ID de compte Google et un mot de passe.
* Dans le cas des publicités Bing, vous avez également besoin de l’ID de client Bing.
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) for any of the three search engines. Utilisez plutôt d’autres navigateurs Web.

## Autorisations Advertising Analytics  {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics dispose de deux autorisations qui sont automatiquement accordées aux administrateurs d’Analytics. Les administrateurs peuvent alors choisir d’accorder ces autorisations aux non-administrateurs.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Autorisation </th> 
   <th colname="col2" class="entry"> Définition </th> 
   <th colname="col3" class="entry"> Octroi d’une autorisation dans Adobe Analytics </th> 
   <th colname="col4" class="entry"> Octroyez l’autorisation si vous êtes connecté à Adobe Experience Cloud. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gestion Advertising Analytics </p> </td> 
   <td colname="col2"> <p>Permet aux utilisateurs de configurer/modifier/des comptes de recherche publicitaire. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol">Gestion utilisateur</span> &gt; <span class="uicontrol">Groupes</span> &gt; <span class="uicontrol">Modifier l’accès à tous les rapports</span> &gt; <span class="uicontrol">Personnaliser les outils Analytics</span> &gt; <span class="uicontrol">Gestion Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Connectez-vous à adminconsole.adobe.com</span> &gt; <span class="uicontrol">Produits</span> &gt; <span class="uicontrol">Profil des produits</span> &gt; <span class="uicontrol">Onglet Autorisations</span> &gt; <span class="uicontrol">Outils Analytics</span> &gt; <span class="uicontrol">Gestion Advertising Analytics</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuration Advertising Analytics </p> </td> 
   <td colname="col2"> <p>Permet aux utilisateurs de configurer les suites de rapports à configurer pour les analyses de publicité. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol">Gestion utilisateur</span> &gt; <span class="uicontrol">Groupes</span> &gt; <span class="uicontrol">Modifier l’accès à tous les rapports</span> &gt; <span class="uicontrol">Personnaliser les outils de suites de rapports</span> &gt; <span class="uicontrol">Configuration Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Connectez-vous à adminconsole.adobe.com</span> &gt; <span class="uicontrol">Produits</span> &gt; <span class="uicontrol">Profil des produits</span> &gt; <span class="uicontrol">Onglet Autorisations</span> &gt; <span class="uicontrol">Outils de suites de rapports</span> &gt; <span class="uicontrol">Configuration Advertising Analytics</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Dimensions et mesures Advertising Analytics {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analytics ajoute les dimensions et les mesures suivantes à Analysis Workspace, à Reports &amp; Analytics, au Report Builder et à l’API de création de rapports.

**Dimensions**

>[!IMPORTANT]
>
>Cette intégration crée un ensemble de dimensions à travers les classifications de la variable AMO ID. Ces nouvelles dimensions n’affectent ni ne modifient vos dimensions de variable de suivi de campagne ou de marketing existantes. L’ID AMO est connecté à un  lorsqu’un arrive sur le site à partir d’une publicité de recherche payante. Les dimensions AMO peuvent donc être utilisées pour ventiler les mesures AMO fournies par cette intégration, ainsi que toutes les données capturées en aval par le (visites,,  de page, taux de rebonds, commandes, recettes,  personnalisé, etc.). Ils peuvent également être ventilés selon d’autres dimensions lorsqu’ils sont  sur d’autres mesures sur site.
>
>Les classifications de ces mesures sont mises à jour quotidiennement. Ainsi, si vous apportez des modifications aux métadonnées dans un moteur de recherche, il se peut que ces modifications ne soient pas répercutées avant le jour suivant où les classifications sont mises à jour.

| Nom de classification (dimension) | Définition |
|--- |--- |
| Type de correspondance de mot-clé (AMO ID) | Type de correspondance de mot-clé. En règle générale, les valeurs sont soit large, soit une expression, soit une valeur exacte ou aucune valeur si le type de publicité n’a pas de type de correspondance. |
| Plateforme publicitaire (ID AMO) | Nom du moteur de recherche. Les valeurs peuvent inclure Google AdWords ou Microsoft Bing Ads. |
| Compte (ID AMO) | Nom du compte de moteur de recherche qui est suivi. |
| Campaign (AMO ID) | Nom de la campagne dans votre compte de moteur de recherche. |
| Groupe publicitaire (ID AMO) | Nom du groupe publicitaire dans vos campagnes par moteur de recherche. |
| Publicité (ID AMO) | Titre et description de la publicité qui sont utilisés sur votre publicité. |
| Mot-clé (ID AMO) | La valeur de mot-clé de votre compte de moteur de recherche |
| Type de correspondance (AMO ID) | Le type de correspondance de mot-clé affecté à votre mot-clé. En général, les valeurs sont large, expression, exact ou aucune valeur si aucun type de correspondance n’est défini pour le type de publicité. |
| Type de publicité (ID AMO) | Le type de publicité diffusée, en général « Publicité textuelle ». |
| Titre de la publicité (ID AMO) | L’objet Titre utilisé dans votre publicité. |
| Description de la publicité (ID AMO) | L’objet Description de la publicité utilisé dans votre publicité. |
| URL d’affichage d’annonce (ID AMO) | L’objet URL d’affichage de la publicité utilisé dans votre publicité. |
| URL de destination de l’annonce (ID AMO) | L’URL de la page d’entrée ou l’URL finale affectée à votre publicité. |
| Réseau (AMO ID) | Réseau sur lequel la publicité est diffusée. Pour Advertising Analytics, cette valeur est toujours « Recherche ». |
| Emplacement (AMO ID) | Le site web de placements gérés (pour les réseaux de contenu). Seuls les placements gérés utilisent cette dimension. |
|  du de produits (ID AMO) | Nom de la cible du produit utilisé sur les publicités PLA (et non le produit acheté). |
| Optimisation (AMO ID) | Il n’est pas utilisé par les analyses de publicité. Il est utilisé uniquement par les clients de Advertising Cloud. |
| Périphérique (AMO ID) | Pas utilisé aujourd’hui. Espace réservé pour une éventuelle amélioration du produit afin d’indiquer le type d’appareil cible (p. ex. mobile ou de bureau) de la publicité (et non l’appareil du visiteur). |

**Mesures**

>[!IMPORTANT]
>
>Les mesures fournies par Advertising Analytics (répertoriées ci-dessous) sont des données synthétiques provenant des moteurs de recherche. Ils ne sont pas connectés au  du Analytics. Elles sont uniquement connectées à la variable d’identifiant AMO et à ses dimensions de classification associées. En tant que tels, ils ne doivent faire l’objet d’aucun rapport par des dimensions/segments autres que ceux basés sur les dimensions de l’ID AMO. Analytics affichera alors des zéros pour les données. Vous pouvez les inclure dans des mesures calculées avec d’autres mesures, mais ces mesures calculées doivent également être ventilées uniquement par dimensions d’ID d’OMA.
>
>Ces mesures sont des données provenant quotidiennement, de sorte qu’elles ne contiennent pas de données pour le jour en cours. Ils ne doivent pas non plus être signalés sur une granularité inférieure à la normale.
>
>Il existe une mesure Instances d’ID AMO qui est définie lorsque l’ID AMO est défini sur un  de (c.-à-d. un clic publicitaire). Cette mesure est capturée en temps réel avec l’accès au  du et est disponible pour les ventilations avec d’autres dimensions également définies sur le  du.

| Nom de la mesure | Définition |
|--- |--- |
| Impressions AMO | Nombre d&#39;impressions publicitaires signalées par le moteur de recherche. |
| Clics AMO | Nombre de clics sur les publicités tel que rapporté par le moteur de recherche. |
| Coût AMO | Coût payé pour chaque mot-clé/publicité tel que rapporté par le moteur de recherche. |
| Pos. moy. | Mesure calculée qui reflète la position moyenne des publicités telle que rapportée par le moteur de recherche. |
| La Durée note de qualité moyenne | Mesure calculée qui reflète le score de qualité moyen rapporté par le moteur de recherche. |
