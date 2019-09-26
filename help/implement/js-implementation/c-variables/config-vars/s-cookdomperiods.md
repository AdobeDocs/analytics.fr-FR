---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Elle est également utilisée par certains modules externes pour déterminer le domaine correct afin de définir le cookie du module externe.

The default value for  is "2". *`cookieDomainPeriods`* This is the value that is used if *`cookieDomainPeriods`* is omitted. Par exemple, l’utilisation du domaine `www.mysite.com`, *`cookieDomainPeriods`* doit être 2. Car `www.mysite.co.jp`il *`cookieDomainPeriods`* doit être "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

Par exemple, si vous définissez *`cookieDomainPeriods`* la valeur 2 sur le domaine `www.mysite.co.jp`, les `s_cc` cookies et `s_sq` sont créés sur le domaine `co.jp`. Comme `co.jp` est un domaine incorrect, la plupart des navigateurs rejette ces cookies. Cela entraîne la perte de données de mise en correspondance des clics des visiteurs, et le rapport [!UICONTROL Profil du visiteur] &gt; [!UICONTROL Technologie] &gt; [!UICONTROL Cookies] indique que pratiquement 100 % des visiteurs ont rejeté les cookies propriétaires.

Si la variable *`cookieDomainPeriods`* est définie sur « 3 » et que le domaine contient uniquement deux points, le fichier JavaScript définit les cookie sur le sous-domaine du site. Par exemple, si vous définissez *`cookieDomainPeriods`* la valeur "3" sur le domaine `www2.mysite.com`, les `s_cc` cookies et `s_sq` sont créés sur le domaine `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. Par exemple, `store.toys.mysite.com` aurait toujours *`cookieDomainPeriods`* défini sur "2". Cette définition de la variable définit correctement les cookies sur le domaine racine [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

Voir aussi [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | CDP | Affecte plusieurs rapports, dans la mesure où il contrôle le mode de stockage et de traitement de l’identifiant visiteur. | "2" |

>[!NOTE]
>
>Certains services de cloud computing sont considérés comme des domaines de niveau supérieur, qui ne permettent pas l’écriture de cookies. (Par exemple, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, etc.) Si vous mettez ces services en œuvre, vous pourriez être affecté par le paramètre de vie privé d’Analytics qui retire les utilisateurs qui ont bloqué tous les cookies si vous n’avez pas configuré votre propre domaine (par exemple, si vous testez votre mise en œuvre). Dans ce cas, tout accès pour lequel le système a déterminé que les cookies étaient désactivés, non fonctionnels ou inaccessibles est exclu et n’apparaît donc pas dans les rapports.

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

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. Cela peut entraîner une perte de données, dans la mesure où des visiteurs basculent entre différents sous-domaines.
* La variable était utilisée dans les implémentations obsolètes avant *`cookieDomainPeriods`* *`trackingServer`* de définir le cookie Identifiant visiteur. Bien qu’elle ne soit présente que dans du code obsolète, l’échec de la définition correcte *`cookieDomainPeriods`* dans ce cas présente un risque de perte de données pour votre implémentation.