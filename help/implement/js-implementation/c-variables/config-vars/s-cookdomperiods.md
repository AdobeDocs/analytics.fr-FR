---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieDomainPeriods

La variable détermine le domaine sur lequel les cookies [!DNL Analytics] `s_cc`et `s_sq` sont définis en établissant le nombre de points contenus dans le domaine de l’URL de la page. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe.

La valeur par défaut de *`cookieDomainPeriods`* est « 2 ». Il s’agit de la valeur utilisée si la variable *`cookieDomainPeriods`* est omise. Par exemple, en utilisant le domaine `www.mysite.com`, *`cookieDomainPeriods`* doit être « 2 ». Pour `www.mysite.co.jp`, *`cookieDomainPeriods`* doit être « 3 ».

Si la valeur *`cookieDomainPeriods`* est définie sur « 2 », mais que le domaine contient trois points, le fichier JavaScript tente de définir les cookies sur le suffixe du domaine.

Par exemple, si vous définissez *`cookieDomainPeriods`* sur « 2 » sur le domaine `www.mysite.co.jp`, les cookies `s_cc` et `s_sq` sont créés sur le domaine `co.jp`. Comme `co.jp` est un domaine incorrect, la plupart des navigateurs rejette ces cookies. Cela entraîne la perte de données de mise en correspondance des clics des visiteurs, et le rapport [!UICONTROL Profil du visiteur] &gt; [!UICONTROL Technologie] &gt; [!UICONTROL Cookies] indique que pratiquement 100 % des visiteurs ont rejeté les cookies propriétaires.

Si la variable *`cookieDomainPeriods`* est définie sur « 3 » et que le domaine contient uniquement deux points, le fichier JavaScript définit les cookie sur le sous-domaine du site. Par exemple, si vous définissez *`cookieDomainPeriods`* sur « 3 » sur le domaine `www2.mysite.com`, les cookies `s_cc` et `s_sq` sont créés sur le domaine `www2.mysite.com`. Cependant, lorsqu’un visiteur se rend sur un autre sous-domaine du site (tel que `www4.mysite.com`), tous les cookies définis avec `www2.mysite.com` ne peuvent pas être lus.

> [!NOTE] N’incluez pas de sous-domaines supplémentaires dans *`cookieDomainPeriods`*. Par exemple, `store.toys.mysite.com` aurait toujours *`cookieDomainPeriods`* défini sur « 2 ». Cette définition de la variable définit correctement les cookies sur le domaine racine [!DNL mysite.com]. La définition de *`cookieDomainPeriods`* sur « 3 » dans cet exemple définit les cookies sur le domaine [!DNL toys.mysite.com], ce qui a les mêmes conséquences que l’exemple précédent.

Voir aussi [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | CDP | Affecte plusieurs rapports, dans la mesure où il contrôle le mode de stockage et de traitement de l’identifiant visiteur. | "2" |

> [!NOTE] Certains services de cloud computing sont considérés comme des domaines de niveau supérieur qui n’autorisent pas l’écriture de cookies. (Par exemple, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, etc.) Si vous mettez ces services en œuvre, vous pourriez être affecté par le paramètre de vie privé d’Analytics qui retire les utilisateurs qui ont bloqué tous les cookies si vous n’avez pas configuré votre propre domaine (par exemple, si vous testez votre mise en œuvre). Dans ce cas, tout accès pour lequel le système a déterminé que les cookies étaient désactivés, non fonctionnels ou inaccessibles est exclu et n’apparaît donc pas dans les rapports.

## Exemples

Définition manuelle de la variable

```js
s.cookieDomainPeriods = "3";
```

Voici plusieurs exemples pour définir de manière dynamique la variable si le fichier JavaScript héberge les deux types :

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## Pièges, questions et conseils

* Si vous constatez que les données de mise en correspondance des clics des visiteurs sont absentes ou que le rapport [!UICONTROL Trafic] &gt; [!UICONTROL Technologie] &gt; [!UICONTROL Cookies] affiche un pourcentage élevé de visiteurs qui rejettent les cookies, vérifiez que la valeur de *`cookieDomainPeriods`* est correcte.

* Si la valeur *`cookieDomainPeriods`* est supérieure au nombre de sections figurant dans le domaine, les cookies sont définis avec le domaine complet. Cela peut entraîner une perte de données, dans la mesure où des visiteurs basculent entre différents sous-domaines.
* La variable *`cookieDomainPeriods`* était utilisée dans les implémentations obsolètes avant *`trackingServer`* afin de définir le cookie d’identifiant visiteur. Bien qu’elle ne soit présente que dans du code obsolète, la non-définition correcte de *`cookieDomainPeriods`* dans cette situation présente un risque de perte de données pour votre mise en œuvre.