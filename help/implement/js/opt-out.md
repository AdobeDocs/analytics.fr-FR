---
title: Liens d’exclusion
description: Découvrez comment créer et mettre en œuvre des liens d’exclusion pour les visiteurs de votre site.
translation-type: ht
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Mise en œuvre des liens d’exclusion

> [!IMPORTANT] Adobe recommande d’utiliser le service d’inclusion, en particulier pour les organisations concernées par la réglementation du RGPD. Voir [Aperçu du service d’inclusion](https://docs.adobe.com/content/help/fr-FR/id-service/using/implementation/opt-in-service/optin-overview.html) dans le guide d’utilisation d’Experience Cloud Identity Service.

Certains visiteurs de votre site web préfèrent ne pas inclure leurs informations de navigation dans votre jeu de données. Adobe offre la possibilité de fournir aux visiteurs le moyen d’exclure leurs informations de la collecte effectuée. Tous les types de mise en œuvre sont pris en charge ; votre organisation est responsable de votre propre politique de protection de la vie privée et du respect des conditions que vous avez signées.

Lorsqu’un visiteur atteint une URL d’exclusion, il est invité à installer un cookie d’exclusion. Si un utilisateur choisit de ne pas faire l’objet d’un suivi et qu’un cookie d’exclusion est défini, votre fichier JavaScript continue d’envoyer des données aux serveurs Adobe. Toutefois, ces données ne sont pas traitées ni incluses dans les rapports.

> [!TIP] Adobe propose également des paramètres de confidentialité par suite de rapports. Voir [Paramètres de confidentialité](../../admin/admin/privacy-settings.md) dans le guide d’utilisation Administrateur.

## URL d’exclusion

La page d’exclusion de votre organisation dépend de la valeur de variable [`trackingServer`](../vars/config-vars/trackingserver.md) dans votre mise en œuvre.

* Dans Adobe Experience Platform Launch :
   1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) et cliquez sur une propriété.
   2. Cliquez sur l’onglet [!UICONTROL Extensions], puis sur [!UICONTROL Configurer] sous Adobe Analytics.
   3. Cliquez sur l’accordéon [!UICONTROL Général], puis notez la valeur [!UICONTROL Serveur de suivi].

* Dans une mise en œuvre JavaScript :
   1. Sur votre serveur web, ouvrez le fichier AppMeasurement.js utilisé sur votre site dans un éditeur de code ou de texte.
   2. Notez la valeur de la variable `trackingServer`.

* Installez [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/fr-FR/debugger/using/experience-cloud-debugger.html) :
   1. Accédez à votre site à l’aide du navigateur Chrome.
   2. Ouvrez Experience Cloud Debugger, puis accédez à l’[!UICONTROL onglet Réseau].
   3. Notez la valeur [!UICONTROL Request URL - Hostname].

Une fois que vous avez trouvé le domaine `trackingServer` de votre mise en œuvre, ajoutez le chemin `/optout.html` à la fin. Par exemple :

* Cookies tiers : `https://example.sc.omtrdc.net/optout.html`
* Cookies propriétaires : `https://stats.example.com/optout.html`

## Paramètres de chaîne de requête d’exclusion

Il existe des paramètres que vous pouvez charger automatiquement sur cette page à l’aide de chaînes de requête.

### Paramètres régionaux

Changer automatiquement la langue de la page d’exclusion en incluant le paramètre de chaîne de requête `locale`. Attribuez ce paramètre de chaîne de requête à l’une des valeurs suivantes :

* en_US (anglais, par défaut)
* bg_BG (bulgare)
* zh_CN (chinois simplifié)
* zh_TW (chinois traditionnel)
* cs_CZ (tchèque)
* da_NK (danois)
* nl_NL (néerlandais)
* et_EE (estonien)
* fi_FI (finnois)
* fr_FR (français)
* de_DE (allemand)
* el_GR (grec)
* it_IT (italien)
* jp_JP (japonais)
* ko_KR (coréen)
* lv_LV (letton)
* lt_LT (lituanien)
* nb_NO (norvégien)
* pl_PL (polonais)
* pt_BR (portugais)
* sk_SK (slovaque)
* es_ES (espagnol)

Par exemple, `https://example.sc.omtrdc.net/optout.html?locale=ko_KR` charge la page d’exclusion en coréen.

> [!TIP] La valeur de la chaîne de requête `en_US` n’est pas obligatoire, car la page se charge en anglais par défaut.

### Fenêtre contextuelle

Ajoute un bouton Fermer la fenêtre à la page, ce qui permet de faire de la page d’exclusion une fenêtre contextuelle. Utilisez le paramètre de chaîne de requête `popup` et donnez-lui la valeur `1`.

Par exemple, `https://example.sc.omtrdc.net/optout.html?popup=1` charge la page d’exclusion avec un bouton Fermer la fenêtre.

> [!NOTE] Historiquement, ce paramètre de chaîne de requête forçait une fenêtre contextuelle. Cependant, la plupart des navigateurs modernes permettent à l’utilisateur final de contrôler les fenêtres contextuelles.

### Exclusion par clic unique

Permet à l’utilisateur de se désinscrire immédiatement du suivi. Ajoutez les deux paramètres de chaîne de requête `opt_out` et `confirm_change`, en attribuant à chacun une valeur de `1`.

Par exemple, `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` installe immédiatement le cookie d’exclusion sur la page du visiteur.

### Inclusion par clic unique

Permet à l’utilisateur de se reconnecter immédiatement au suivi en supprimant le cookie d’exclusion. Ajoutez les deux paramètres de chaîne de requête `opt_in` et `confirm_change`, en attribuant à chacun une valeur de `1`.

Par exemple, `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` supprime immédiatement le cookie d’exclusion du visiteur.
