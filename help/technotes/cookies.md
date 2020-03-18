---
title: Adobe Analytics et les cookies de navigateur
description: Découvrez comment Adobe Analytics gère les cookies d’un navigateur.
translation-type: ht
source-git-commit: 3566960f546d847ed4f6ca8ecbb9c759460f4fb0

---


# Adobe Analytics et les cookies de navigateur

Afin de prendre en charge l’identification persistante des utilisateurs dans les propriétés et les solutions, Adobe Analytics réagit aux modifications apportées à la gestion des cookies par les navigateurs. La FAQ suivante présente des informations sur la manière dont l’identification persistante des visiteurs est préservée grâce aux modifications apportées aux cookies des navigateurs.

## Comment les navigateurs changent-ils leur façon de gérer les cookies ?

En général, la plupart des navigateurs sont de plus en plus restrictifs quant à la manière dont ils conservent les cookies tiers. Cela peut affecter le suivi si le cookie est supprimé ou refusé par le navigateur. Le navigateur Safari définit également des limites pour certains cookies propriétaires.

La liste suivante répertorie quelques modifications récentes en fonction des navigateurs :

* Chrome : à partir de Chrome 80, l’attribut `SameSite` est utilisé différemment pour gérer les cookies tiers ou les requêtes intersites. À terme, les développeurs Chrome cherchent des moyens d’[abandonner complètement les cookies tiers](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1).

* Firefox et Edge : les annonces de produits indiquent que les versions successives de leurs navigateurs doivent suivre les mêmes modifications que celles effectuées dans Chrome 80.

* Safari : avec [Safari 12.1](https://webkit.org/blog/category/privacy/), les cookies propriétaires persistants définis via l’API document.cookie, souvent appelés cookies « côté client », voient leur expiration plafonnée à sept jours.

## Quelle est la différence entre les cookies tiers et les cookies propriétaires ?

### Cookies propriétaires

Les cookies propriétaires sont créés par les sites web clients (propres à un domaine) et stockés dans les navigateurs clients lorsque les utilisateurs visitent les sites web clients. En général, tous les navigateurs acceptent les cookies propriétaires. Dans une implémentation Analytics de cookies propriétaires, le cookie d’identifiant visiteur est créé sur un nœud Adobe lorsque le nom d’hôte est rapproché du domaine à l’aide d’un [CNAME](https://docs.adobe.com/content/help/fr-FR/id-service/using/reference/analytics-reference/cname.html). Le cookie est ensuite accepté par le navigateur dans un contexte propriétaire. Pour plus d’informations, voir [À propos des cookies propriétaires](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-first-party.html).

### Cookies tiers

Les cookies tiers ne sont pas créés lorsque des utilisateurs visitent un site web. Bien que les navigateurs traitent actuellement tous les cookies tiers de la même manière et les stockent en conséquence, les cookies tiers eux-mêmes peuvent se comporter de différentes façons. Avec une implémentation Analytics de cookies tiers par un client, le client effectue des appels uniquement vers Adobe, et non vers des domaines tiers inconnus ou suspects. Il s’agit de la méthode actuelle d’implémentation d’Analytics pour un suivi sécurisé (HTTPS) et fiable avec des identifiants persistants. Cette méthode est implémentée en configurant le fichier AppMeasurement.js. Pour plus d’informations, voir [Cookies et Experience Cloud Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/intro/cookies.html).

![Comparaison des cookies](assets/cookies2.png)

## Comment les navigateurs stockent-ils et gèrent-ils actuellement les cookies Analytics ?

En fonction de l’implémentation, les cookies Analytics sont stockés comme suit :

### Implémentations de cookies tiers

Les navigateurs stockent actuellement l’ID Adobe [demdex.net](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/reference/demdex-calls.html) en tant que cookie tiers. Ce cookie fournit des identifiants persistants sur plusieurs domaines et permet d’obtenir du contenu sécurisé (https).

### Implémentations de cookies propriétaires

En configurant un CNAME, votre utilisateur peut recevoir des cookies Adobe dans un contexte de cookies propriétaires pour ses navigateurs. Il peut s’agir d’une option viable si l’implémentation d’un cookie tiers n’est pas optimale pour vos utilisateurs.

## Qu’est-ce que l’attribut de cookie SameSite et comment affecte-t-il Analytics ?

Avec la sortie du navigateur Chrome 80 (et les versions successives des navigateurs Firefox et Edge), l’attribut de cookie SameSite applique la spécification de trois valeurs différentes pour contrôler le comportement des demandes intersites, comme suit :

* `None` : ce paramètre permet l’accès intersite et la transmission de cookies dans un contexte tiers. Pour spécifier cet attribut, vous devez également spécifier `Secure` et toutes les requêtes de navigateur doivent suivre le protocole HTTPS. Par exemple, lorsque vous définissez le cookie, vous associez les valeurs de l’attribut comme suit : `Set-Cookie: example_session=test12; SameSite=None; Secure`. S’ils ne sont pas correctement étiquetés, les cookies sont inutilisables pour les navigateurs les plus récents et seront rejetés.

* `Lax` : permet d’envoyer des requêtes intersites avec les cookies d’un même site, uniquement pour les navigations de niveau supérieur avec des méthodes HTTP *sécurisées* (lecture seule, par exemple `GET`).

* `Strict` : le cookie du même site n’est envoyé pour aucune requête de site web tiers. Le cookie n’est envoyé que si le site du cookie correspond au site dans la barre d’URL.

Le comportement par défaut dans ces versions de navigateur consiste à traiter les cookies qui n’ont pas d’attribut `SameSite`spécifié comme `SameSite=Lax`.

## Comment Adobe Analytics réagit-il à ces modifications ?

Toutes les mises à jour des cookies Adobe sont gérées via les serveurs Adobe, et Adobe a mis à jour leurs serveurs Edge afin de définir les attributs de cookies appropriés. Adobe a publié des mises à jour côté serveur pour définir leurs cookies tiers avec les attributs appropriés. Aucune mise à jour JavaScript n’est requise pour vos sites.

Cette mise à niveau effectuée par les serveurs Adobe Edge se fera automatiquement lorsque les utilisateurs visitent un site web sur lequel le cookie est utilisé. Pour la plupart des produits Adobe, les cookies seront marqués comme appropriés à la publication de Chrome 80. L’exception concerne les implémentations d’Adobe Analytics qui utilisent la collecte de données tierces et qui n’utilisent pas Adobe Experience Cloud Identity Service (ECID). Il se peut que ces clients connaissent une légère augmentation temporaire du nombre de nouveaux visiteurs qui auraient été autrement balisés comme visiteurs récurrents.

Dans le cas des navigateurs que Google a identifiés comme ne gérant pas correctement les cookies lorsque `SameSite` est défini sur `None`, `SameSite` ne sera pas défini.

Le tableau suivant récapitule les cookies Analytics :

![Tableau des cookies](assets/cookies1.png)

## Quel est le meilleur moyen de préparer mon site aux modifications Chrome, Firefox et Edge ?

Les clients Analytics doivent confirmer que leur configuration JavaScript utilise HTTPS pour leurs appels aux services Adobe. ECID redirige les appels HTTP tiers vers son point de terminaison HTTPS, ce qui peut faire accroître la latence, mais vous ne devez pas obligatoirement modifier votre configuration.

Adobe vous conseille de vous assurer que toutes les pages de votre site sont diffusées avec HTTPS.

### Un CNAME pour plusieurs domaines

Si vous avez une implémentation CNAME définie dans le même domaine que votre site web, il s’agit alors d’un contexte de cookie propriétaire et vous n’avez pas besoin d’apporter de modifications.

Cependant, si vous possédez plusieurs domaines et utilisez le même CNAME pour la collecte de données sur tous vos domaines, il est traité comme un cookie tiers sur ces autres domaines. Avec Chrome 80, il ne sera plus visible sur ces autres domaines. Pour rendre le comportement plus similaire sur tous les navigateurs, Analytics définit explicitement la valeur `SameSite` de ce cookie sur `Lax`. Si vous utilisez ce cookie dans un contexte tiers convivial, vous devez définir le cookie avec la valeur `SameSite=None`, ce qui signifie également que vous devez toujours utiliser HTTPS. Contactez l’assistance clientèle Adobe pour que la valeur SameSite soit modifiée pour vos CNAME sécurisés. Remarque : cette action n’est PAS requise pour les clients Analytics qui utilisent l’ECID.

## Quel est l’impact des modifications de Safari (ITP 2.1) pour Analytics ?

Malgré les modifications apportées dans Safari 12.1, les ensembles de données des cookies Adobe Experience Cloud sont toujours en cours de collecte. Bien que les cookies soient plafonnés à sept jours, les visiteurs qui reviennent sur votre propriété dans le délai imparti renouvellent le cookie et évitent son expiration pendant sept jours supplémentaires. Les périodes d’analyse et le nombre de visiteurs récurrents peuvent être réduits pour le trafic Safari jusqu’à ce qu’une mise à jour Adobe soit disponible.

En raison de la durée d’expiration raccourcie de sept jours, les clients peuvent constater une augmentation du nombre de visiteurs uniques. Le nombre de visites et de pages vues ne devrait pas être affecté. Si votre propriété a un trafic saisonnier, tel que les services fiscaux ou les ventes durant la période des fêtes, vous pouvez constater un impact plus important, car ce visiteur ne sera pas connecté entre les saisons.

Si vous utilisez un CNAME, le service d’identification des visiteurs enregistre l’ECID dans un cookie propriétaire côté serveur. Cela permet au cookie de persister pendant toute sa durée.

**Remarque : ITP 2.1 ne s’applique pas aux navigateurs intégrés dans les applications mobiles.**

### Cookies propriétaires concernés

Les cookies propriétaires créés par le biais de `document.cookie` sont affectés. Si vous définissez l’un de ces cookies avec une réponse HTTP (côté serveur) ou en utilisant la certification CNAME, vous n’êtes pas affecté par les modifications apportées dans ITP 2.1. Les cookies propriétaires suivants et les bibliothèques JavaScript Adobe associées sont affectés :

* Les cookies AMCV définis par la bibliothèque du service ECID (Experience Cloud ID)
* Le cookie de secours hérité Analytics `s_fid`

Le cookie `s_vi` hérité Analytics en tant que cookie tiers, y compris les cibles de collecte de 2o7.net ou omtrdc.net, continue d’être bloqué en fonction des versions antérieures d’ITP.

Pour résumer :

* Si vous disposez d’un CNAME et que vous utilisez le service d’identification des visiteurs, votre implémentation ne sera pas affectée.

* Si vous utilisez un CNAME propriétaire dans le contexte propriétaire et n’utilisez pas le service d’identification des visiteurs, votre implémentation ne sera pas affectée.

* Si vous utilisez un domaine de cookies propriétaires dans le contexte tiers ou avec les noms de domaine tiers standard (par exemple 2o7.net, omtrdc.net, etc.), Safari continuera à le bloquer tel quel.

* Si vous utilisez un identifiant visiteur personnalisé, cela dépend de la manière dont vous stockez votre identifiant visiteur. Si vous stockez votre identifiant dans un cookie propriétaire « côté client », l’expiration après sept jours s’applique. Si vous utilisez d’autres moyens pour stocker votre identifiant personnalisé, vous devrez évaluer si vous êtes affecté.

### Ensembles de données les moins affectés

Les ensembles de données avec des visiteurs actifs qui reviennent fréquemment sont les moins affectés par les modifications. Si le contenu de votre site est tel que les clients reviennent tous les jours ou au moins deux fois par semaine, les cookies de ces utilisateurs actifs seront renouvelés avant expiration. Les réseaux sociaux, les sites d’actualités et les autres sites de médias sont plus susceptibles d’avoir de grandes communautés d’utilisateurs qui reviennent fréquemment.

Les clients qui utilisent `s_vi` comme identifiant visiteur principal et sont configurés avec la collecte de données propriétaires à l’aide d’un CNAME ne seront pas affectés par ITP 2.1. Notez que dans les cas où il est impossible de définir `s_vi`, le cookie de secours, `s_fid` peut être utilisé et aura un délai d’expiration de sept jours.

En outre, les ensembles de données qui utilisent le service d’identification des visiteurs et possèdent un domaine propriétaire sont les moins affectés.

## Les modifications de Safari affecteront-elles mon entreprise ?

Adobe recommande aux clients de mesurer d’abord l’impact au sein de leur propre entreprise avant d’apporter des modifications à la collecte de données. Pour ce faire, vous pouvez utiliser les méthodes décrites ci-après.

Pour mesurer l’impact sur les rapports et les tests, il est important de connaître le type de suivi des visiteurs et des cookies que vous avez mis en place et le volume de trafic généré par les utilisateurs utilisant Safari. Tenez compte des points suivants pour mesurer l’impact sur votre entreprise :

* Vérifiez les types de cookies définis par vos bibliothèques Adobe.

* Ouvrez votre console de développement dans votre navigateur Safari le plus récent. Si l’un des cookies répertoriés ci-dessus est défini dans votre domaine propriétaire, ces modifications peuvent vous affecter.

* Si un cookie `s_vi` s’affiche, mais pas un cookie `AMCV` défini dans le contexte d’un CNAME, c’est que vous utilisez un CNAME pour l’identification des visiteurs et votre utilisation d’Analytics n’est pas affectée par ces modifications. Si vous voyez à la fois un cookie `s_vi` et un cookie `AMCV` définis dans le contexte d’un CNAME, c’est que vous avez récemment utilisé la période de grâce ou que vous l’utilisez actuellement ; il se peut qu’une partie du trafic Analytics soit affectée.

* Mesurez le pourcentage de visiteurs qui ne reviennent pas dans les sept jours avec Analytics. Si vos visiteurs reviennent plusieurs fois dans les sept jours, votre trafic peut ne pas être affecté de manière significative. Pour plus d’informations sur l’utilisation d’Analytics pour mesurer cela, voir [Impact d’ITP 2.1 sur les clients d’Adobe Experience Cloud et Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac) (en anglais).

* Mesurez le pourcentage de trafic provenant des navigateurs Safari pour déterminer si des modifications sont suffisamment justifiées. Pour obtenir des instructions sur l’utilisation d’Analytics afin de connaître le pourcentage du trafic Safari sur vos sites, voir [Impact d’ITP 2.1 sur les clients d’Adobe Experience Cloud et Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac) (en anglais).

## Quels sont les navigateurs que les visiteurs utilisent le plus ?

Si vous souhaitez en savoir plus sur les navigateurs utilisés par vos visiteurs, vous pouvez utiliser la [dimension Navigateur](https://docs.adobe.com/content/help/fr-FR/analytics/components/variables/dimensions-reports/reports-browsers.html) d’Analytics pour déterminer les navigateurs les plus utilisés pour vos sites. Vous pouvez également utiliser les dimensions Analytics pour identifier les navigateurs les plus utilisés selon les régions géographiques. Pour plus d’informations, voir [Géosegmentation](https://docs.adobe.com/content/help/fr-FR/analytics/components/variables/dimensions-reports/reports-geosegmentation.html).

Selon [statcounter](https://gs.statcounter.com/browser-market-share/all), à la fin de 2019, la part de marché mondiale pour chaque navigateur était la suivante :

* Chrome : ~ 64 %
* Safari : ~ 17 %
* Firefox : ~ 4 %
* Edge : ~ 2 %

À mesure que la part de marché évolue, vous pouvez consulter ces [statistiques](https://gs.statcounter.com/browser-market-share/all) pour examiner votre stratégie de mise en œuvre.

## Comment puis-je travailler au mieux avec les modifications ITP 2.1 dans Safari à court terme ?

Le CNAME et le programme de certificat géré Adobe sont utilisés pour gérer les modifications ITP. Le programme de certificat géré Adobe permet de mettre en œuvre un nouveau certificat propriétaire pour les cookies propriétaires, sans frais supplémentaires. Aujourd’hui, Adobe propose plusieurs services CNAME par solution et cherche à tirer parti du programme de certification Analytics à court terme.

Tout client Analytics actuel avec une configuration CNAME qui utilise également les services d’identification des visiteurs Experience Cloud ID pourra tirer parti d’une prochaine mise à jour de la bibliothèque ECID. Ce changement permettra aux serveurs de suivi certifiés CNAME de gérer l’ECID et d’être utilisés comme référence pour l’identification des visiteurs. D’autres informations sont disponibles dans les versions successives de la bibliothèque ECID.

Adobe sait que tous les clients de la bibliothèque ECID n’utilisent pas CNAME ou Analytics. Tous les clients ECID se verront proposer une configuration CNAME afin d’utiliser la même fonctionnalité.

Si vous n’utilisez pas actuellement CNAME pour votre implémentation, vous pouvez démarrer le processus en contactant l’assistance clientèle.

## Quels sont les futurs plans d’Adobe pour l’identification persistante des visiteurs ?

Les nouvelles fonctionnalités et implémentations incluent :

* des options de certification CNAME en libre-service dans toutes les solutions Adobe ;

* des méthodes flexibles de collecte d’identifiants visiteurs, le BYOI (Bring your own Identity) et la collecte des données API-first ;

* des graphiques des identités d’Adobe Experience Platform ;

* une approche unifiée de la collecte de données Adobe.

Adobe s’engage à personnaliser plus précisément les contenus pour les clients qui souhaitent une expérience personnalisée. Adobe s’efforce d’offrir à ses clients une fonctionnalité d’identité en ligne qui les aide à s’aligner sur les choix de confidentialité de leurs propres clients.

## Plus d’informations

Pour plus d’informations, voir :

* [Adobe Experience Cloud : Mises à jour des cookies pour Google Chrome](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598) (en anglais)

* [Impact d’ITP 2.1 sur les clients d’Adobe Experience Cloud et Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac) (en anglais)
