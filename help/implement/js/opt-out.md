---
title: Liens d’exclusion
description: Découvrez comment créer et mettre en œuvre des liens d’exclusion pour les visiteurs de votre site.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 70%

---

# Mise en œuvre des liens d’exclusion

>[!IMPORTANT]
>
> **Cette page d’aide permet aux clients Adobe Analytics de fournir à leurs utilisateurs des liens d’exclusion. Si vous n’êtes pas client Adobe Analytics, reportez-vous à la section [Adobe des choix en matière de confidentialité](https://www.adobe.com/privacy/opt-out.html) pour contrôler la manière dont Adobe utilise vos informations.**

Certains visiteurs de votre site web préfèrent ne pas inclure leurs informations de navigation dans votre jeu de données. Adobe offre la possibilité de fournir aux visiteurs de votre site web un moyen de se désabonner de leurs informations en cours d’analyse.

Les liens d’exclusion permettent aux visiteurs de votre site web d’omettre leurs données des rapports Analytics. Ces liens sont limités aux mises en oeuvre d’AppMeasurement. Adobe recommande d’utiliser la variable [Service Adobe Experience Cloud Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr) au lieu de . Le service Opt-in est plus robuste et fonctionne sur plusieurs produits Adobe Experience Cloud, y compris Adobe Analytics et AppMeasurement.

Lorsqu’un visiteur atteint une URL d’exclusion, il est invité à installer un cookie d’exclusion. Si un utilisateur choisit de ne pas faire l’objet d’un suivi et qu’un cookie d’exclusion est défini, AppMeasurement continue d’envoyer des données à Adobe. Toutefois, ces données ne sont pas traitées ni incluses dans les rapports.

>[!TIP]
>
>Adobe propose également des paramètres de confidentialité par suite de rapports. Voir [Paramètres de confidentialité](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md) dans le guide d’utilisation destiné à l’administrateur.

## URL d’exclusion

La page d’exclusion de votre organisation dépend de la valeur de variable [`trackingServer`](../vars/config-vars/trackingserver.md) dans votre mise en œuvre.

* Dans l’extension Analytics :
   1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
   1. Cliquez sur la propriété de balise de votre choix.
   1. Cliquez sur l’onglet [!UICONTROL Extensions], puis sur [!UICONTROL Configurer] sous Adobe Analytics.
   1. Cliquez sur l’accordéon [!UICONTROL Général], puis notez la valeur [!UICONTROL Serveur de suivi].

* Dans une mise en œuvre JavaScript :
   1. Sur votre serveur web, ouvrez le fichier AppMeasurement.js utilisé sur votre site dans un éditeur de code ou de texte.
   1. Notez la valeur de la variable `trackingServer`.

* Installez [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html) :
   1. Accédez à votre site à l’aide du navigateur Chrome.
   1. Ouvrez Experience Cloud Debugger, puis accédez à l’[!UICONTROL onglet Réseau].
   1. Notez la valeur [!UICONTROL Request URL - Hostname].

Une fois que vous avez trouvé le domaine `trackingServer` de votre mise en œuvre, ajoutez le chemin `/optout.html` à la fin. Par exemple :

* Cookies tiers : `https://example.data.adobedc.net/optout.html`
* Cookies propriétaires : `https://stats.example.com/optout.html`

## Paramètres de chaîne de requête d’exclusion

Il existe des paramètres que vous pouvez charger automatiquement sur cette page à l’aide de chaînes de requête.

### Paramètres régionaux

Changer automatiquement la langue de la page d’exclusion en incluant le paramètre de chaîne de requête `locale`. Attribuez ce paramètre de chaîne de requête à l’une des valeurs suivantes :

* `en_US` (anglais, valeur par défaut)
* `bg_BG` (Bulgare)
* `zh_CN` (Chinois simplifié)
* `zh_TW` (Chinois traditionnel)
* `cs_CZ` (tchèque)
* `da_NK` (danois)
* `nl_NL` (néerlandais)
* `et_EE` (Estonien)
* `fi_FI` (finnois)
* `fr_FR` (Français)
* `de_DE` (Allemand)
* `el_GR` (Grec)
* `it_IT` (italien)
* `jp_JP` (japonais)
* `ko_KR` (coréen)
* `lv_LV` (letton)
* `lt_LT` (lituanien)
* `nb_NO` (norvégien)
* `pl_PL` (polonais)
* `pt_BR` (portugais)
* `sk_SK` (slovaque)
* `es_ES` (Espagnol)

Par exemple, `https://example.data.adobedc.net/optout.html?locale=ko_KR` charge la page d’exclusion en coréen.

### Fenêtre contextuelle

Ajoute un bouton Fermer la fenêtre à la page, ce qui permet de faire de la page d’exclusion une fenêtre contextuelle. Utilisez le paramètre de chaîne de requête `popup` et donnez-lui la valeur `1`.

Par exemple, `https://example.data.adobedc.net/optout.html?popup=1` charge la page d’exclusion avec un bouton Fermer la fenêtre.

>[!NOTE]
>
>Historiquement, ce paramètre de chaîne de requête forçait une fenêtre contextuelle. Cependant, la plupart des navigateurs modernes permettent à l’utilisateur final de contrôler les fenêtres contextuelles.

### Exclusion par clic unique

Permet à l’utilisateur de se désinscrire immédiatement du suivi. Ajoutez les deux paramètres de chaîne de requête `opt_out` et `confirm_change`, en attribuant à chacun une valeur de `1`.

Par exemple, `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` installe immédiatement le cookie d’exclusion sur la page du visiteur.

### Inclusion par clic unique

Permet à l’utilisateur de se reconnecter immédiatement au suivi en supprimant le cookie d’exclusion. Ajoutez les deux paramètres de chaîne de requête `opt_in` et `confirm_change`, en attribuant à chacun une valeur de `1`.

Par exemple, `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` supprime immédiatement le cookie d’exclusion du visiteur.
