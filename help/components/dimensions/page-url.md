---
title: URL de la page
description: URL de la page.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# URL de la page

La dimension &quot;URL de page&quot; liste les URL de votre site.

>[!IMPORTANT]
>
>Cette dimension n’est disponible que dans le Data warehouse. Si vous souhaitez utiliser une dimension URL dans d’autres solutions Analytics, utilisez une [eVar](evar.md).

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`g` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Renseigner une eVar avec une URL

Adobe recommande de définir une eVar sur la chaîne concaténée `window.location.hostname + window.location.pathname`. Cette chaîne fonctionne généralement mieux que `window.location.href` parce qu’elle omet le protocole, les chaînes de requête et les balises d’ancrage.

Si vous souhaitez que l’eVar corresponde exactement à la dimension &quot;URL de page&quot; dans le Data warehouse, vous pouvez utiliser des variables [](/help/implement/vars/page-vars/dynamic-variables.md) dynamiques et définir l’eVar sur `D=g` chaque accès. Notez que cette méthode ne fonctionne pas pour les accès aux liens personnalisés, car l’URL de la page est supprimée pour tous les [`tl()`](/help/implement/vars/functions/tl-method.md) appels.

## Valeurs de dimension

Les valeurs de dimension incluent les URL des pages de votre site.
