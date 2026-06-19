---
title: Liens d’exclusion
description: Découvrez comment créer et mettre en œuvre des liens d’exclusion pour les visiteurs de votre site.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
role: Developer
TQID: https://experienceleague.adobe.com/3X3RsfI3J96Ml4Q2UvnaaPLfBihSPvD-bfE8-yZujzU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 68%

---

# Mise en œuvre des liens d’exclusion

>[!IMPORTANT]
>
> Cet article fournit aux **clients d’Adobe Analytics qui (prévoient de) mettre en œuvre Adobe Analytics** sur leur site web des instructions sur la manière de fournir aux utilisateurs du site web des liens de désinscription. <p><p>> Si vous **visitez un site web qui a implémenté Adobe Analytics** et que vous souhaitez vous désinscrire, **<span style="color:red">cet article ne vous est PAS destiné</span>**. Consultez [Choix de confidentialité d’](https://www.adobe.com/privacy/opt-out.html) pour contrôler comment Adobe utilise vos informations.

Certains visiteurs de votre site web préfèrent ne pas inclure leurs informations de navigation dans votre jeu de données. Adobe permet de fournir aux visiteurs et visiteuses de votre site web un moyen de se désabonner de leurs informations en cours d’analyse.

Les liens d’exclusion sont un moyen de permettre aux visiteurs de votre site web d’omettre leurs données des rapports Analytics. Ces liens se limitent aux implémentations d’AppMeasurement ; Adobe recommande d’utiliser plutôt le service d’accord préalable à l’entreprise Adobe CX [&#128279;](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr). Le service Opt-in est plus robuste et fonctionne sur plusieurs produits Adobe CX Enterprise, y compris Adobe Analytics et AppMeasurement.

Lorsqu’un visiteur atteint une URL d’exclusion, il est invité à installer un cookie d’exclusion. Si un utilisateur choisit de ne pas faire l’objet d’un tracking et qu’un cookie d’exclusion est défini, AppMeasurement continue à envoyer des données à Adobe. Toutefois, ces données ne sont pas traitées ni incluses dans les rapports.

>[!TIP]
>
>Adobe propose également des paramètres de confidentialité par suite de rapports. Voir [Paramètres de confidentialité](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md) dans le guide d’utilisation destiné à l’administrateur.

## URL d’exclusion

La page d’exclusion de votre organisation dépend de la valeur de variable [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) dans votre mise en œuvre.

* Dans l’extension Analytics :
   1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
   1. Cliquez sur la propriété de balise de votre choix.
   1. Cliquez sur l’onglet [!UICONTROL Extensions], puis sur [!UICONTROL Configurer] sous Adobe Analytics.
   1. Cliquez sur l’accordéon [!UICONTROL Général], puis notez la valeur [!UICONTROL Serveur de suivi].

* Dans une mise en œuvre JavaScript :
   1. Sur votre serveur web, ouvrez le fichier AppMeasurement.js utilisé sur votre site dans un éditeur de code ou de texte.
   1. Notez la valeur de la variable `trackingServer`.

* À l’aide du débogueur d’entreprise Adobe CX [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html) :
   1. Accédez à votre site à l’aide du navigateur Chrome.
   1. Ouvrez CX Enterprise Debugger, puis accédez à l’onglet [!UICONTROL Network].
   1. Notez la valeur [!UICONTROL Request URL - Hostname].

Une fois que vous avez trouvé le domaine `trackingServer` de votre mise en œuvre, ajoutez le chemin `/optout.html` à la fin. Par exemple :

* Cookies tiers : `https://example.data.adobedc.net/optout.html`
* Cookies propriétaires : `https://stats.example.com/optout.html`

## Paramètres de chaîne de requête d’exclusion

Il existe des paramètres que vous pouvez charger automatiquement sur cette page à l’aide de chaînes de requête.

### Paramètres régionaux

Changer automatiquement la langue de la page d’exclusion en incluant le paramètre de chaîne de requête `locale`. Attribuez ce paramètre de chaîne de requête à l’une des valeurs suivantes :

* `en_US` (anglais, par défaut)
* `bg_BG` (bulgare)
* `zh_CN` (chinois simplifié)
* `zh_TW` (chinois traditionnel)
* `cs_CZ` (tchèque)
* `da_NK` (Danois)
* `nl_NL` (néerlandais)
* `et_EE` (Estonien)
* `fi_FI` (finlandais)
* `fr_FR` (Français)
* `de_DE` (allemand)
* `el_GR` (Grec)
* `it_IT` (italien)
* `jp_JP` (japonais)
* `ko_KR` (coréen)
* `lv_LV` (Letton)
* `lt_LT` (lituanien)
* `nb_NO` (norvégien)
* `pl_PL` (polonais)
* `pt_BR` (portugais)
* `sk_SK` (slovaque)
* `es_ES` (espagnol)

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
