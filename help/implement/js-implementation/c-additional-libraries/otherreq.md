---
description: D’autres exigences et configurations s’appliquent dans le cas de l’implémentation d’Analytics sans JavaScript.
keywords: Analytics Implementation;case sensitive;encode query parameters;invalid characters;secure image requests;maximum variable length;referring;url;caching;namespace
title: Mise en œuvre sans instructions JavaScript
topic: Developer and implementation
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mise en œuvre sans instructions JavaScript

D’autres exigences et configurations s’appliquent dans le cas de l’implémentation d’Analytics sans JavaScript.

Vous pouvez examiner un échantillon de code afin de mieux comprendre l’implémentation. Les informations suivantes décrivent les exigences et configurations supplémentaires :

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Respect de la casse**

Les noms de paramètres (`pageName`, `purchaseID`, etc.) sont sensibles à la casse. Ils n’enregistrent correctement les données que s’ils apparaissent tels qu’ils sont désignés dans le tableau affiché dans la section [Paramètres de requête](/help/implement/js-implementation/data-collection/query-parameters.md).

**Codage des paramètres de requête**

Les valeurs de chacun des paramètres de chaîne de requête doivent être codées au format URL. Ce codage convertit les caractères qui sont normalement incorrects lorsqu’ils apparaissent dans une chaîne de requête (c’est le cas d’un espace, par exemple) en caractères codés, précédés du signe `%`. Ainsi, un espace est converti en `%20`.

La version JavaScript de cette fonction est appelée Escape (pour le décodage, la fonction est Unescape). Microsoft IIS version 5.0 comprend également une fonction Escape / Unescape pour le codage de chaînes de requête. D’autres langages de script de serveurs Web fournissent également des utilitaires de codage/décodage.

**Longueur maximale de la variable**

Une longueur maximale est associée à chaque variable. Celle-ci est spécifiée dans la section [Variables Analytics](/help/implement/js-implementation/c-variables/sc-variables.md). En cas de dépassement de cette longueur maximale, la valeur de la variable est tronquée en vue d’être stockée et affichée dans Analytics.

**Caractères non valides**

Les caractères dont les codes sont supérieurs à la valeur décimale 128 ne sont pas valides, au même titre que les codes de caractères non imprimables inférieurs à 128. Le formatage HTML ("&lt;h1&gt;") est également incorrect, tout comme les symboles de marque commerciale, de marque déposée ou de copyright.

**Demandes d’images sécurisées (&lt;https:&gt;) et non sécurisées (&lt;http:&gt;)**

Sur les pages accessibles via le protocole sécurisé HTTPS (protocole sécurisé), la partie URL de la demande d’image varie en fonction de l’ensemble de serveurs de collecte de données.

Les informations ci-dessous illustrent les différentes URL utilisées pour les demandes d’image sécurisées et non sécurisées.

* Le `*` dans l’URL ci-dessus indique une URL spécifique au centre de données qui vous a été fournie par votre consultant Adobe. Adobe utilise plusieurs centres de données ; il est donc nécessaire d’implémenter l’URL correcte qui a été attribuée à votre société. Le centre de données correct est fourni automatiquement pour tout code téléchargé en dehors d’Admin Console dans le compte de votre société. En ce qui concerne le code provenant de sources externes, une correction peut s’avérer nécessaire pour le faire pointer vers le centre de données correct.
* Dans le cas des clients qui utilisent plusieurs suites de rapports, celles-ci doivent être répertoriées uniquement dans la section « répertoire », et non dans la section « domaine » de l’URL, comme illustré ci-dessous.
* Le `*` dans l’URL ci-dessus indique une URL spécifique au centre de données qui vous a été fournie par votre consultant Adobe. Adobe utilise plusieurs centres de données ; il est donc nécessaire d’implémenter l’URL correcte qui a été attribuée à votre société.

**URL et URL de référence**

L’URL et l’URL de référence peuvent être renseignées à partir du serveur dans les variables `g=` et `r=`. Utilisez Request ServerVariables (`HTTP\_REFERRER`) ou Request ServerVariables (`(URL) (IIS/ASP)`), ou la variable appropriée à votre technologie de script/serveur. L’URL de référence `( r=)` revêt une importance capitale pour effectuer le suivi des URL de ce type, des domaines, des moteurs de recherche, ainsi que des termes de recherche.

Si la variable pageName n’est pas utilisée, il est impératif que le champ URL active soit renseigné de manière unique. Si les variables pageName et URL active `(g=)` ne sont pas renseignées, l’enregistrement est incorrect et n’est pas traité. Le champ URL doit obligatoirement être renseigné pour que l’enregistrement soit traité.

**Effets de la mise en cache**

Des pages HTML et d’autres pages Web peuvent être mises en cache par des navigateurs ou serveurs situés entre le visiteur et le site Web qui diffuse le contenu. La mise en cache empêche un décompte précis des pages vues et des autres événements, sauf s’il est fait usage d’une technique de contournement de la mémoire cache.

Le langage JavaScript standard d’Adobe offre une méthode dynamique de modification de la demande d’image afin d’éviter la mise en cache des images et des pages, ce qui permet un décompte précis des pages vues.

Cependant, cette organisation aléatoire ne se produit pas lors de la création d’une demande d’image côté serveur. Les rechargements de pages et les pages mises en cache (que ce soit dans la mémoire cache du navigateur ou dans un serveur proxy) ne sont pas comptabilisés lors de l’utilisation de telles demandes.

Par définition, les pages SSL (`https:`) ne sont jamais mises en cache ; dès lors, cette mise en garde ne s’applique qu’aux pages non sécurisées (`http:`). Cette remarque concerne également les pages qui contiennent des paramètres (`https://www.samplesite.com/page.asp?parameter=1`) ou présentent certaines extensions de fichier (`.asp`, `.jsp`, etc.). ne sont pas non plus mises en cache.

Les exemples ci-dessous illustrent une solution JavaScript minimaliste qui assemble principalement la demande d’image côté serveur et, après coup, ajoute un nombre aléatoire dans le navigateur. Cette méthode permet de contourner la problématique de la mise en cache qui, autrement, se poserait sur des pages HTML statiques auxquelles l’utilisateur accède via le protocole https:.

**Variable nameSpace**

Le paramètre de chaîne de requête nameSpace est obligatoire pour les implémentations qui n’utilisent pas JavaScript.

Par exemple : ns=nameSpace

Contactez votre responsable de compte ou consultant Adobe pour obtenir la valeur nameSpace de votre société.
