---
title: Questions fréquentes sur Activity Map
description: Questions fréquentes relatives à l’Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 64964972410911c2bea1460039def39b7c6dfa38
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 15%

---

# Questions fréquentes sur Activity Map

Questions fréquentes relatives à l’Activity Map.

+++Comment accorder des autorisations à Activity Map ?

Les autorisations d’utilisation d’Activity Map et de ses dimensions associées sont gérées dans le [Adobe Admin Console](/help/admin/admin-console/home.md).

Les [éléments d’autorisation](/help/admin/admin-console/permissions/product-profile.md) requis pour l’Activity Map sont les suivants :

* **[!UICONTROL Outils Analytics]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Outils Analytics]** > **[!UICONTROL Publication de segment]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Portée de défilement Activity Map]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Lien Activity Map par région]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Région Activity Map]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Lien Activity Map]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Page Activity Map]**

Pour plus d’informations, voir [Autorisations de profil de produit pour les outils Analytics](/help/admin/admin-console/permissions/analytics-tools.md) .

+++

+++Tous les clients Analytics ont-ils accès à l’Activity Map ?

Les organisations qui ont un contrat pour Adobe Analytics Standard, Premium et Ultimate ont accès à l’Activity Map. Ces types de contrats représentent la majorité des clients Adobe Analytics.

+++

+++Comment Activity Map prend-il en charge les applications d’une seule page (SPA) ?

Toutes les quelques secondes, Activity Map analyse la page web à la recherche de modifications. L’Activity Map trouve du nouveau contenu sur la page sans recharger, mais ce nouveau contenu est toujours attribué à la première valeur de dimension de page.

* Activity Map vérifie si la visibilité des liens qu’il connaît a changé. Si une modification de visibilité est trouvée, alors les liens de la page dans la colonne Présent du tableau sont mis à jour avec pour valeur [!UICONTROL Affiché] ou [!UICONTROL Masqué].

* Lorsque l’interaction de l’utilisateur crée du contenu, tous les nouveaux éléments qui sont AppMeasurement comme lien sont ajoutés à la table [!UICONTROL Liens sur la page]. Activity Map envoie une nouvelle requête de données qui inclut ces nouveaux liens. Les nouveaux liens apparaissent dans la table [!UICONTROL Liens sur la page] lorsque la requête de données est renvoyée.

+++

+++Activity Map fournit-il des données sur les liens qui sont affichés mais qui ne font pas l’objet d’un clic ?

Non, Adobe ne suit pas automatiquement les liens qui ont été uniquement affichés.

+++

+++Quels navigateurs et versions Activity Map prend-il en charge ?

Activity Map prend en charge la dernière version de la plupart des navigateurs modernes.

+++

+++Activity Map augmente-t-il les appels au serveur ?

Activity Map nʼenvoie pas dʼappels au serveur par lui-même. Au lieu de cela, les variables de données contextuelles Activity Map sont incluses dans les appels de page vue Analytics sur la page suivante. Cependant, certaines versions précédentes d’Activity Map sur le SDK Web envoient un appel distinct pour les données d’Activity Map. Si vous utilisez la dernière version du SDK Web, les données Activity Map sont fusionnées avec l’événement suivant.

+++

+++Pourquoi manque-t-il certains nombres de classement dans la superposition ?

Certains liens, tels que ceux contenus dans les menus, sont masqués sur la page. Par conséquent, les superpositions de lien correspondantes ne s’affichent pas. Le classement est calculé pour tous les liens de la page, y compris les liens masqués.

+++

+++Comment le classement des liens est-il déterminé dans le rapport Tous les liens ?

* **En mode dégradé et bulle** : la colonne de mesures détermine le rang. Pour les liens ayant la même valeur de mesure, le classement est déterminé selon l’ordre alphabétique des ID de lien.
* **En mode gagnant et perdant** : la colonne pourcentage gagné détermine le rang. Pour les liens disposant du même gain, le classement est déterminé selon lʼordre alphabétique des ID de lien.

+++

+++Comment Activity Map fonctionne-t-il avec les pages qui utilisent plusieurs suites de rapports ?

Par défaut, Activity Map utilise la suite de rapports associée à la première balise de la page. Vous pouvez sélectionner une autre suite de rapports par l’intermédiaire de l’onglet **[!UICONTROL Paramètres de l’Activity Map]** > **[!UICONTROL Autres]** .

+++

+++Combien de temps Activity Map analyse-t-il Adobe Analytics sur la page ?

Activity Map recherche la présence dʼAdobe Analytics pendant 20 secondes au maximum après un événement de fin de page.

+++

+++Comment Activity Map gère-t-il le contenu dynamique ?

Activity Map vérifie toutes les 2 secondes si des changements ont été apportés à lʼétat de la page web, par exemple :

* le contenu HTML devenu visible ;
* le contenu HTML masqué ;
* le nouveau contenu HTML injecté.

Si le contenu est masqué ou affiché, l’extension modifie automatiquement l’état des liens affectés (et donc des superpositions) de masqué à visible ou de visible à masqué. Si du nouveau contenu est injecté, l’application récupère les liens associés, extrait les données d’analyse à leur sujet et ajoute des superpositions pour ces liens.

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

+++Activity Map est-il compatible avec les suites de rapports virtuelles ?

Oui. Cependant, en raison des limitations des suites de rapports virtuelles, le mode de connexion de l’Activity Map n’est pas compatible avec les suites de rapports virtuelles.

+++

+++Comment désactiver l’Activity Map ?

La méthode de désactivation de l’Activity Map dépend du type de mise en oeuvre :

* **Extension SDK Web** : dans les paramètres de configuration de l’extension, décochez les cases **[!UICONTROL Collecter les clics sur les liens internes]**, **[!UICONTROL Collecter les clics sur les liens externes]** et **[!UICONTROL Collecter les clics sur les liens de téléchargement]**.
* **Bibliothèque JavaScript du SDK Web** : définissez [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) sur `false`.
* **Extension Analytics** : dans les paramètres de configuration de l’extension, décochez la case intitulée **[!UICONTROL Utiliser l’Activity Map]**.
* **AppMeasurement** : supprimez ou commentez le module Activity Map dans `AppMeasurement.js`, ou remplacez l’appel de fonction de module par un corps vide :

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++Quelle est la configuration système requise pour utiliser la superposition Activity Map ?

Vous pouvez utiliser la dernière version de Chrome, Edge ou Firefox avec l’extension Activity Map.

+++

+++Que dois-je prendre en compte lors de l’utilisation d’Activity Map pour des informations d’identification personnelle ?

Tenez compte des scénarios suivants où les données d’identification personnelle peuvent être collectées à l’aide d’Activity Map :

* **Liens d’e-mail** : si vous cliquez sur une adresse e-mail pour ouvrir le client de messagerie de l’utilisateur, l’Activity Map peut collecter l’adresse électronique sur laquelle l’utilisateur a cliqué.
* **Liens d’ID utilisateur** : une fois qu’un visiteur se connecte, l’Activity Map peut enregistrer tous les liens contenant l’ID utilisateur du visiteur.
* **Liens d’informations sensibles** : pour les institutions financières, les informations sensibles telles que le numéro de compte peuvent être suivies s’il s’agit d’un lien et que les visiteurs cliquent dessus.
* **Liens contenant des informations personnelles** : pour les sites web de santé, les liens peuvent contenir des informations personnelles. Si un visiteur clique sur ces liens, l’Activity Map collecte le texte du lien.

+++

+++Quelles sont les données suivies par l’Activity Map par défaut ?

Activity Map effectue le suivi des éléments suivants :

* Une balise `<a>` ou `<area>` avec une propriété `href`. Les liens de balise d’ancrage (`#`) ne sont pas suivis par défaut.
* Un attribut `onclick` qui définit une variable `s_objectID`
* Balise `<input>` ou bouton `submit` avec une valeur ou du texte enfant
* Une balise `<input>` de type `image` et une propriété `src`
* Une balise `<button>` sans l’attribut `type="button"`. Si vous souhaitez effectuer le suivi des balises `<button>`, envisagez d’utiliser des attributs tels que `role="button"` ou `submit="button"` à la place.

+++

+++Quels sont les exemples de liens suivis automatiquement par Activity Map ?

Vous trouverez ci-dessous quelques exemples dans lesquels Activity Map dispose de toutes les informations requises pour effectuer le suivi d’un lien.

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

+++Quels sont les exemples de liens que l’Activity Map ne suit PAS automatiquement ?

Voici quelques exemples dans lesquels Activity Map ne suit pas les clics.

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
