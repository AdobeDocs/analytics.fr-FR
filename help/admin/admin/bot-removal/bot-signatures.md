---
title: Signatures de robots courantes
description: Reconnaissez les identifiants communs des robots.
translation-type: tm+mt
source-git-commit: 2f4c54ec57eeddc03f0b0d12a0a7f391e36ab0fc
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---


# Signatures de robots courantes

Bien que l’identification des robots dans un jeu de données soit différente selon l’environnement, voici quelques façons courantes d’identifier les robots.

## Nombre élevé de vues de page par visite

Vous pouvez extraire un rapport de Data Warehouse avec l’adresse IP, les vues de page et les visiteurs uniques. Créez ensuite un &#x200B; de calcul &#x200B; dans Excel pour les vues de page par visite et triez les pages du plus haut au plus bas. Les robots ont généralement un très grand nombre de vues de page par visite (plusieurs centaines à milliers). Vous constaterez une forte baisse du trafic réel.

## Aucun parrain

En règle générale, les robots n’ont pas d’URL de référence. Dans la segmentation, il est possible de filtrer cette variable sous la forme `Referring Domain equals Typed/Bookmarked`.

## Agents utilisateur étranges

Les robots utilisent souvent des agents utilisateur personnalisés qui ne sont pas classés dans la dimension Navigateurs ou qui s’affichent sous la forme d’une version `unknown` d’un navigateur standard. Safari inconnu et Opera inconnu ont une très grande probabilité d&#39;être des bots.

## Systèmes d’exploitation Linux ou &quot;Non spécifié&quot;

Nous ne voulons pas discréditer le grand système d&#39;exploitation open-source Linux, mais apparemment les bots aiment le définir comme leur système d&#39;exploitation. Cependant, veillez à exclure le trafic légitime des utilisateurs Linux. Les robots aiment également ne pas définir de système d&#39;exploitation, qui peut être segmenté en tant que `Operating System &#x200B;equals Not Specified`.

## Vues de page = Visites = Visiteurs uniques

Ceci s’applique particulièrement au rapport de l’agent utilisateur. Comme vous pouvez le voir sur la capture d’écran ci-dessous, la &quot;version inconnue&quot; de ces navigateurs a presque le même nombre de visiteurs que les visiteurs uniques (et presque le même nombre de vues de page). Il peut être isolé dans la segmentation en créant un conteneur [!UICONTROL Inclure] pour `Single Page Visits equals Enabled` ou `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Nombre de visites 1

Les robots obtiennent généralement un nouvel ID de visiteur chaque fois qu’ils s’exécutent, n’entraînant ainsi qu’une seule visite et tout leur trafic sera constitué d’un nombre de visites de 1.

## Résolution d&#39;écran inférieure

Les utilisateurs modernes ont des moniteurs à résolution beaucoup plus élevée que par le passé. Les accès avec les résolutions suivantes semblent être très populaires pour les robots :

* 1024 x 768&#x200B;&#x200B;
* 1 366 x 768
* 1 600 x 864
* 800 x 600
* 1 600 x 1 200
* Non spécifié
* 1 024 x 667

## Pays + Fuseau horaire non compatible

Vous remarquerez une incohérence entre le pays d’origine et le fuseau horaire. Par exemple, l&#39;emplacement peut être les États-Unis mais le fuseau horaire peut être GMT.

![](assets/bots-country-time-zone.png)

## Non connecté

L’utilisateur ne se connecte à aucun moment de sa visite et ses eVars d’identification d’utilisateur ne persistent pas lors de ses précédentes visites. Bien que certains robots puissent être configurés pour s&#39;authentifier, la majorité ne sont pas si malins.

## Aucun IPC en visite

En règle générale, les robots n&#39;ajoutent pas de produits à un panier ou ne procèdent pas à l&#39;extraction. La plupart du temps, ils n’envoient pas de formulaire de piste ou d’autres événements de réussite, mais certains robots envoient des formulaires HTML simples. &#x200B;

## Chaîne de requête spécifique présente

Parfois, les robots tentent de détruire le cache ou de briser des sites en heurtant des URL ou des URL mal formées qui n&#39;existent pas (comme des pages d&#39;administration LAMP ou Wordpress standard) ou en ajoutant des chaînes de requête spécifiques.

## Adresses IP provenant de plateformes informatiques distribuées

Les services d&#39;hébergement Web tels que Amazon Web Services ou Google Cloud peuvent être utilisés à mauvais escient comme des fermes de robots. Ces adresses IP risquent fort d&#39;être des robots :
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/) : DÉBUTS d’adresse IP avec  `&#x200B;35.199` ou  `35.194&#x200B;`
