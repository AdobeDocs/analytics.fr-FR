---
title: Référents
description: Affiche l’URL de l’accès précédent, si cet accès se trouvait en dehors de votre site.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# Référents

La dimension &quot;&quot; indique l’URL d’où sont venus vos avant qu’ils n’arrivent sur votre site. Si, par exemple, un clique sur un lien `example.com/example-page.html` et arrive sur votre site, `example.com/example-page.html` est le s’il n’est pas défini comme faisant partie de votre domaine.

Cette dimension requiert que vous configuriez la URL [interne de votre suite de rapports](/help/admin/admin/internal-url-filter-admin.md). Si vous ne configurez pas de  d’URL internes, Adobe Analytics considère tous les domaines comme internes à votre site.

## Propriétés de dimension

* Cette dimension utilise l’attribution la plus récente par défaut.
* Cette dimension expire par défaut après la visite.
* Cette dimension est soumise à la limite unique de 500 000 avant de regrouper les valeurs de dimension sous (Faible trafic). L&#39;entrepôt de données n&#39;a pas de limite unique.
* S’il n’existe aucune valeur  pour une mesure, elle est regroupée sous `Typed/Bookmarked`.
* Cette dimension est généralement définie sur le premier accès de la visite, mais elle peut être définie en milieu de visite.

## Résolution des problèmes

**Q : Pourquoi est-ce que je vois`googleusercontent.com`comme une valeur de dimension ?**

A : [Google](https://about.google/) utilise le domaine `googleusercontent.com` pour le contenu hébergé. Le contenu hébergé comprend :

* **Pages** mises en cache : Les araignées de Google analysent constamment le Web et enregistrent les pages Web au cas où elles seraient mises hors ligne ou indisponibles. Ces pages mises en cache sont disponibles en regard de tous les résultats de recherche en cliquant sur le lien &quot;Mise en cache&quot; de l&#39;une des pages de résultats de recherche de Google. Lorsqu’un utilisateur clique sur ce lien, puis examine le contenu d’origine sur votre site, `googleusercontent.com` est répertorié comme leur domaine référent. Ces pages ont le sous-domaine `webcache.googleusercontent.com`.
* **Pages** traduites : Google  un service de traduction robuste et pratique. Lorsque vous consultez un site à l’aide de ce service, il provient de `googleusercontent.com`. La dimension  du affiche les URL de ce domaine si l’utilisateur clique sur un lien pour revenir au contenu d’origine. Ces pages ont le sous-domaine `translate.googleusercontent.com`.
