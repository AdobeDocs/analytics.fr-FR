---
title: Mise en œuvre avec des demandes d’image codées en dur
description: Mise en œuvre d’Adobe Analytics à l’aide d’une balise d’image HTML (demande d’image codée en dur)
feature: Implementation Basics
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 100%

---

# Mise en œuvre avec des demandes d’image codées en dur

Les bibliothèques AppMeasurement fournies par Adobe compilent les variables présentes sur la page, puis les envoient en tant que demande d’image à Adobe. Vous pouvez ignorer les bibliothèques AppMeasurement et envoyer manuellement une demande d’image à Adobe. Cette méthode nécessite de formuler manuellement la demande d’image et la chaîne de requête.

Cette méthode de mise en œuvre peut être utilisée sur n’importe quelle plateforme qui affiche des images provenant de sources externes. Elle ne dépend pas du tout de JavaScript.

>[!NOTE]
>
>Bien que les demandes d’image codées en dur soient faciles à configurer, il est difficile de les déboguer, de les gérer et de les mettre à l’échelle dans des projets de grande envergure. Assurez-vous que les demandes d’image codées en dur sont la meilleure option pour vous avant de continuer.

## Syntaxe de la demande d’image

Voici un exemple de demande d’image codée en dur à l’aide de code HTML :

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1/s234234238479?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` désigne le protocole. Faites correspondre le protocole utilisé dans la demande d’image avec le protocole utilisé par le reste de votre site.
* `example.data.adobedc.net` est la valeur contenue dans la variable [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md).
* `/b/ss/` est inclus dans toutes les demandes d’image. Il fait partie de la structure de fichiers des images stockées sur les serveurs de collecte de données Adobe.
* `examplersid` correspond à l’identifiant de la suite de rapports à laquelle vous souhaitez envoyer des données. Pour plusieurs suites de rapports, séparez les identifiants par des virgules, sans espaces (par exemple `examplersid1,examplersid2`, etc.).
* `/1/` est la source de l’accès. Voir `hit_source` dans la section [Référence des colonnes de données](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) du guide d’utilisation Exportation. Contrôle l’ordre que les cookies et les autres méthodes suivent pour identifier les visiteurs.
* `/s234234238479` (`"s"` + un nombre aléatoire) empêche le navigateur de mettre en cache la demande d’image.
* Tout ce qui suit le délimiteur de chaîne de requête (`?`) fait partie des données que vous souhaitez inclure dans les rapports. Voir [Paramètres de requête de collecte de données](../validate/query-parameters.md) pour obtenir la liste complète des paramètres que vous pouvez inclure dans une demande d’image.

## Demandes d’image codées en dur dans Microsoft Outlook

Comme la plupart des courriers électroniques sont au format HTML, il est possible de suivre les courriers électroniques ouverts et d’envoyer ces données à Adobe Analytics. Si votre entreprise choisit d’utiliser cette méthode, tenez compte des points suivants :

* Chaque expéditeur de courrier électronique peut incrémenter un appel au serveur facturable.
* Seuls les clients de messagerie compatible avec HTML et autorisant les images sont suivis. Certains clients de messagerie, tels que Microsoft Outlook, bloquent les images externes par défaut. Ces messageries ne sont pas suivies tant que le destinataire n’a pas choisi de télécharger des images externes.

Pour rédiger un courrier électronique Outlook contenant une demande d’image :

1. Ouvrez un éditeur HTML. Si aucun éditeur HTML n’est disponible, vous pouvez également utiliser un éditeur de texte brut.
2. Dans un nouveau fichier HTML, insérez une balise `<img>` de demande d’image codée en dur enveloppée dans une balise `<body>`.
3. Enregistrez le fichier HTML.
4. Ouvrez Microsoft Outlook et rédigez un courrier électronique.
5. Accédez à l’onglet Insertion et cliquez sur **Joindre un fichier**. Sélectionnez votre fichier HTML de demande d’image.
6. Cliquez sur le menu pop-up en regard de l’onglet Insertion, puis sélectionnez **Insérer comme texte**. Si vous cliquez sur le bouton Insérer sans le menu pop-up, le fichier HTML devient une pièce jointe et cela ne fonctionne pas.

L’apparence du courrier électronique ne change pas, car la demande d’image est un pixel transparent de 1x1. Si vous souhaitez afficher la demande d’image à des fins de test, modifiez le fichier HTML pour y inclure une bordure, du texte supplémentaire ou tout autre contenu.

## FAQ

Découvrez les questions courantes à l’aide de demandes d’image codées en dur.

### Les paramètres de chaîne de requête sont-ils sensibles à la casse ?

Oui. Assurez-vous que les paramètres de chaîne de requête correspondent exactement, sinon ils ne sont pas enregistrés. Par exemple, `pagename` n’est pas un paramètre de chaîne de requête valide, alors que `pageName` en est un.

### Puis-je inclure des espaces dans la chaîne de requête ?

Les valeurs de chacun des paramètres de chaîne de requête sont codées au format URL. Le codage d’URL convertit les caractères normalement interdits dans les URL en caractères autorisés. Ainsi, un espace est converti en `%20`. Assurez-vous que tout caractère non alphanumérique est codé en URL. Adobe URL décode automatiquement les valeurs lorsque les demandes d’image atteignent les serveurs de collecte de données.

Pour plus d’informations sur le fonctionnement du codage des URL, voir [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) (Référence sur le codage des URL HTML) sur W3Schools.

### Quel est le nombre maximal de caractères qu’une seule valeur peut contenir ?

Une longueur maximale différente est associée à chaque variable. La plupart des variables de trafic peuvent contenir jusqu’à 100 octets, tandis que la plupart des variables de conversion peuvent contenir jusqu’à 255 octets. Lorsqu’une demande d’image atteint les serveurs de collecte de données, Adobe tronque automatiquement ces valeurs à leur longueur maximale.
