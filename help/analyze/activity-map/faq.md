---
title: Questions fréquentes sur Activity Map
description: Questions fréquentes relatives à l’Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 15%

---

# Questions fréquentes sur Activity Map

Questions fréquentes relatives à l’Activity Map.

+++Comment accorder des autorisations à l’Activity Map ?

Les autorisations d’utilisation d’Activity Map et de ses dimensions associées sont gérées dans le [Adobe Admin Console](/help/admin/admin-console/home.md).

Les [éléments d’autorisation](/help/admin/admin-console/permissions/product-profile.md) requis pour l’Activity Map sont les suivants :

* **[!UICONTROL Outils Analytics]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Outils Analytics]** > **[!UICONTROL Publication de segments]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Portée de défilement Activity Map]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Lien Activity Map Par Région]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Région Activity Map]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Lien Activity Map]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Page Activity Map]**

Voir [Autorisations de profil de produit pour les outils Analytics](/help/admin/admin-console/permissions/analytics-tools.md) pour plus d’informations.

+++

+++Tous les clients Analytics ont-ils accès à Activity Map ?

Les entreprises ayant souscrit un contrat pour Adobe Analytics Standard, Premium et Ultimate ont accès à Activity Map. Ces types de contrats représentent la majorité de la clientèle d’Adobe Analytics.

+++

+++Comment Activity Map prend-il en charge les applications d’une seule page (SPA) ?

Toutes les quelques secondes, l’Activity Map analyse la page web à la recherche de modifications. L’Activity Map trouve du nouveau contenu sur la page sans avoir à recharger, mais ce nouveau contenu est toujours attribué à la première valeur de dimension de page.

* Activity Map vérifie si la visibilité des liens qu’il connaît a changé. Si une modification de visibilité est trouvée, alors les liens de la page dans la colonne Présent du tableau sont mis à jour avec pour valeur [!UICONTROL Affiché] ou [!UICONTROL Masqué].

* Lorsqu’une interaction d’un utilisateur crée du contenu, tous les nouveaux éléments que l’AppMeasurement détermine comme un lien sont ajoutés au tableau [!UICONTROL Liens sur la page]. Activity Map envoie une nouvelle requête de données qui inclut ces nouveaux liens. Les nouveaux liens apparaissent dans le tableau [!UICONTROL Liens sur la page] lorsque la requête de données est renvoyée.

+++

+++L’Activity Map fournit-il des données sur les liens affichés mais non cliqués ?

Non, l’Adobe ne suit pas automatiquement les liens qui n’ont été consultés que.

+++

+++Quels navigateurs et versions Activity Map prend-il en charge ?

Activity Map prend en charge la dernière version de la plupart des navigateurs modernes.

+++

+++L’Activity Map augmente-t-il les appels au serveur ?

Activity Map nʼenvoie pas dʼappels au serveur par lui-même. Au lieu de cela, les variables de données contextuelles Activity Map sont incluses dans les appels de page vue Analytics sur la page suivante. Cependant, certaines versions précédentes d’Activity Map sur le SDK Web envoient un appel séparé pour les données Activity Map. Si vous utilisez la dernière version de Web SDK, les données Activity Map sont fusionnées avec l’événement suivant.

+++

+++Pourquoi certains numéros de classement sont-ils manquants dans le recouvrement ?

Certains liens, tels que ceux contenus dans les menus, sont masqués de la page. Par conséquent, les recouvrements de liens correspondants ne s’affichent pas. Le classement est calculé pour tous les liens de la page, y compris les liens masqués.

+++

+++Comment le classement des liens est-il déterminé dans le rapport Tous les liens ?

* **En mode dégradé et bulle** : la colonne de mesures détermine le classement. Pour les liens avec la même valeur de mesure, le classement est déterminé en fonction de l’ordre alphabétique des ID de lien.
* **En mode gagnant et perdant** : la colonne de pourcentage gagné détermine le classement. Pour les liens disposant du même gain, le classement est déterminé selon lʼordre alphabétique des ID de lien.

+++

+++Comment Activity Map fonctionne-t-il avec les pages qui utilisent plusieurs suites de rapports ?

Par défaut, l’Activity Map utilise la suite de rapports associée à la première balise de la page. Vous pouvez sélectionner une autre suite de rapports via l’onglet **[!UICONTROL Paramètres de l’Activity Map]** > **[!UICONTROL Autres]**.

+++

+++Combien de temps l’Activity Map recherche-t-il Adobe Analytics sur la page ?

Activity Map recherche la présence dʼAdobe Analytics pendant 20 secondes au maximum après un événement de fin de page.

+++

+++Comment Activity Map gère-t-il le contenu dynamique ?

Activity Map vérifie toutes les 2 secondes si des changements ont été apportés à lʼétat de la page web, par exemple :

* le contenu HTML devenu visible ;
* le contenu HTML masqué ;
* le nouveau contenu HTML injecté.

Si le contenu est masqué ou affiché, l’extension modifie automatiquement l’état des liens affectés (et donc des superpositions) de masqué à affiché ou de visible à masqué. Si un nouveau contenu est injecté, l’application récupère les liens associés, extrait les données d’analyse pour ces liens et ajoute des recouvrements pour ces liens.

+++

+++Sur quelle mesure se base le rapport Flux de page ?

Toutes les données affichées se basent sur les pages vues.

+++

+++Puis-je exporter des données Activity Map par le biais de flux de données ?

Oui. Les [colonnes de flux de données](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) utilisées par l’Activity Map sont les suivantes :

* Lien Activity Map : `clickmaplink`
* Page Activity Map : `clickmappage`
* Région Activity Map : `clickmapregion`
* Lien Activity Map par région : `clickmaplinkbyregion`

+++

+++Les segments fonctionnent-ils en mode réel ?

Non, les segments ne fonctionnent pas en mode réel.

+++

+++L’Activity Map est-il compatible avec les suites de rapports virtuelles ?

Oui. Cependant, en raison des limitations des suites de rapports virtuelles, le mode réel de l’Activity Map n’est pas compatible avec celles-ci.

+++

+++Comment désactiver Activity Map ?

La méthode de désactivation de l’Activity Map dépend de votre type d’implémentation :

* **Extension Web SDK** : dans les paramètres de configuration de l’extension, décochez les cases **[!UICONTROL Collecter les clics sur les liens internes]**, **[!UICONTROL Collecter les clics sur les liens externes]** et **[!UICONTROL Collecter les clics sur les liens de téléchargement]**.
* **Bibliothèque JavaScript Web SDK** : définissez [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) sur `false`.
* **Extension Analytics** : dans les paramètres de configuration de l’extension, décochez la case intitulée **[!UICONTROL Utiliser l’Activity Map]**.
* **AppMeasurement**: supprimez ou mettez en commentaire le module Activity Map dans `AppMeasurement.js`, ou remplacez l&#39;appel de fonction de module par un corps vide :

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++Quelle est la configuration requise pour utiliser le recouvrement de l’Activity Map ?

Vous pouvez utiliser la dernière version de Chrome, Edge ou Firefox avec l’extension Activity Map.

+++

+++Que dois-je prendre en compte lorsque j’utilise Activity Map pour des informations d’identification personnelle ?

Tenez compte des scénarios suivants dans lesquels des données d’identification personnelle peuvent être collectées à l’aide d’Activity Map :

* **Liens d’e-mail** : s’il est possible de cliquer sur une adresse e-mail pour ouvrir le client de messagerie de l’utilisateur, l’Activity Map peut collecter l’adresse e-mail sur laquelle l’utilisateur a cliqué.
* **Liens d’ID utilisateur** : une fois qu’un visiteur s’est connecté, l’Activity Map peut enregistrer tous les liens contenant son ID utilisateur.
* **Liens d’informations sensibles** : pour les institutions financières, il est possible de suivre les informations sensibles telles que le numéro de compte s’il s’agit d’un lien sur lequel les visiteurs cliquent.
* **Liens contenant des informations personnelles** : pour les sites Web de soins de santé, les liens peuvent contenir des informations personnelles. Si un visiteur clique sur ces liens, l’Activity Map collecte ce texte de lien.

+++

+++Quelles données l’Activity Map suit-il par défaut ?

Le suivi Activity Map effectue le suivi des éléments suivants :

* Une balise `<a>` ou `<area>` avec une propriété `href`. Les liens des balises d’ancrage (`#`) ne sont pas suivis par défaut.
* Attribut `onclick` qui définit une variable `s_objectID`
* Une balise `<input>` ou un bouton de `submit` avec une valeur ou un texte enfant
* Une balise `<input>` de type `image` et une propriété `src`
* Balise `<button>` sans `type="button"` d’attribut. Si vous souhaitez effectuer le suivi des balises `<button>`, pensez à utiliser des attributs tels que `role="button"` ou `submit="button"` à la place.

+++

+++Quels sont les exemples de liens suivis automatiquement par l’Activity Map ?

Vous trouverez ci-dessous quelques exemples dans lesquels l’Activity Map dispose de toutes les informations requises pour effectuer le suivi d’un lien.

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++Quels sont quelques exemples de liens que l’Activity Map ne suit PAS automatiquement ?

* La balise d’ancrage n’a pas de `href` valide.
* Aucune méthode [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md) ou [`tl()`](/help/implement/vars/functions/tl-method.md) présente
* Propriété `src` manquante sur un élément d’entrée de formulaire

Voici quelques exemples dans lesquels l’Activity Map ne suit pas les clics :

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
