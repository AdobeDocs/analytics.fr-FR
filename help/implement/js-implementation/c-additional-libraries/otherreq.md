---
description: D’autres exigences et configurations s’appliquent dans le cas de l’implémentation d’Analytics sans JavaScript.
keywords: Implémentation d'Analytics ; sensible à la casse ; encoder les paramètres de requête ; caractères non valides ; demandes d'image sécurisées ; longueur de variable maximale ; référence ; url ; mise en cache ; namespace
seo-description: D’autres exigences et configurations s’appliquent dans le cas de l’implémentation d’Analytics sans JavaScript.
seo-title: Implémentation sans instructions JavaScript
solution: Analytics
title: Implémentation sans instructions JavaScript
topic: Développeur et mise en œuvre
uuid: c 672 dd 63-1 c 74-4 f 66-8992-9257 c 5 a 75 e 36
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implémentation sans instructions JavaScript

D’autres exigences et configurations s’appliquent dans le cas de l’implémentation d’Analytics sans JavaScript.

Vous pouvez examiner un échantillon de code afin de mieux comprendre l’implémentation. Les informations suivantes décrivent les exigences et configurations supplémentaires :

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Respect de la casse**

The parameter names (`pageName`, `purchaseID`, and so forth) are case-sensitive and will not properly record data unless they appear as designated in the table displayed in [Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md).

**Codage des paramètres de requête**

Les valeurs de chacun des paramètres de chaîne de requête doivent être codées au format URL. URL encoding converts characters that are normally illegal when appearing in a query string, such as a space character, into an encoded character beginning with `%`. Ainsi, un espace est converti en `%20`.

La version JavaScript de cette fonction est appelée Escape (pour le décodage, la fonction est Unescape). Microsoft IIS version 5.0 comprend également une fonction Escape / Unescape pour le codage de chaînes de requête. D’autres langages de script de serveurs Web fournissent également des utilitaires de codage/décodage.

**Longueur maximale de la variable**

Une longueur maximale est associée à chaque variable. Celle-ci est spécifiée dans la section [Variables Analytics](../../../implement/js-implementation/c-variables/sc-variables.md). En cas de dépassement de cette longueur maximale, la valeur de la variable est tronquée en vue d’être stockée et affichée dans Analytics.

**Caractères non valides**

Les caractères dont les codes sont supérieurs à la valeur décimale 128 ne sont pas valides, au même titre que les codes de caractères non imprimables inférieurs à 128. Le formatage HTML ("&lt;h1&gt;") est également incorrect, tout comme les symboles de marque commerciale, de marque déposée ou de copyright.

**Secure (&lt; https : &gt; vs. Non sécurisée (&lt; http : &gt;) Demandes d'image**

Sur les pages accessibles via le protocole sécurisé HTTPS (protocole sécurisé), la partie URL de la demande d’image varie en fonction de l’ensemble de serveurs de collecte de données.

Les informations suivantes illustrent les différentes URL utilisées pour les demandes d'image sécurisées et non sécurisées.

* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe utilise plusieurs centres de données ; il est donc nécessaire d’implémenter l’URL correcte qui a été attribuée à votre société. Le centre de données correct est fourni automatiquement pour tout code téléchargé en dehors d’Admin Console dans le compte de votre société. En ce qui concerne le code provenant de sources externes, une correction peut s’avérer nécessaire pour le faire pointer vers le centre de données correct.
* Dans le cas des clients qui utilisent plusieurs suites de rapports, celles-ci doivent être répertoriées uniquement dans la section « répertoire », et non dans la section « domaine » de l’URL, comme illustré ci-dessous.
* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe utilise plusieurs centres de données ; il est donc nécessaire d’implémenter l’URL correcte qui a été attribuée à votre société.

**URL et URL de référence**

The URL and Referring URL may be populated from the server in the `g=` and `r=` variables. Use the Request ServerVariables (`HTTP\_REFERRER`) or Request ServerVariables `(URL) (IIS/ASP)`, or the appropriate variable for your server/scripting technology. The referring URL `( r=)` is extremely important for tracking referring URLs, domains, search engines, and search terms.

Si pagename n'est pas utilisé, il est impératif que le champ URL active soit renseigné de manière unique. If neither pageName nor Current URL `(g=)` is populated, the record is invalid and is not processed. Le champ URL doit obligatoirement être renseigné pour que l’enregistrement soit traité.

**Effets de la mise en cache**

Des pages HTML et d’autres pages Web peuvent être mises en cache par des navigateurs ou serveurs situés entre le visiteur et le site Web qui diffuse le contenu. La mise en cache empêche un décompte précis des pages vues et d'autres événements, sauf si une technique de « cache » est utilisée.

Le langage JavaScript standard d’Adobe offre une méthode dynamique de modification de la demande d’image afin d’éviter la mise en cache des images et des pages, ce qui permet un décompte précis des pages vues.

Cependant, cette organisation aléatoire ne se produit pas lors de la création d’une demande d’image côté serveur. Les rechargements de pages et les pages mises en cache (que ce soit dans la mémoire cache du navigateur ou dans un serveur proxy) ne sont pas comptabilisés lors de l’utilisation de telles demandes.

SSL (`https:`) pages are not, by definition, ever cached so this warning applies only to non-secure (`http:`) pages. Additionally, pages with parameters (`https://www.samplesite.com/page.asp?parameter=1`) or certain file extensions (`.asp`, `.jsp`, etc.) ne sont pas non plus mis en cache.

Les exemples ci-dessous illustrent une solution JavaScript minimaliste qui assemble principalement la demande d’image côté serveur et, après coup, ajoute un nombre aléatoire dans le navigateur. Cette méthode contourne la mise en cache qui autrement serait rencontrée sur les pages HTML statiques consultées via les https : .

**Variable nameSpace**

Le paramètre de chaîne de requête nameSpace est obligatoire pour les implémentations qui n’utilisent pas JavaScript.

Par exemple : ns=nameSpace

Contactez votre responsable de compte ou consultant Adobe pour obtenir la valeur nameSpace de votre société.
