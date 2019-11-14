---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---



# s.linkInternalFilters

La variable est utilisée pour déterminer les liens de votre site qui sont des liens de sortie.

Il s’agit d’une liste, séparée par des virgules, de filtres représentant les liens qui font partie du site.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Chemins &gt; Entrées et sorties &gt; Liens de sortie |  |

> [!NOTE] Nous suggérions auparavant de définir linkInternalFilters sur javascript:. Toutefois, il en résultait que tous les domaines étaient considérés comme externes, y compris le domaine actuel dans lequel réside la balise. Si vous voulez que plusieurs domaines soient considérés comme internes, vous pouvez les ajouter, tel qu’illustré dans les exemples ci-dessous.

La variable *`linkInternalFilters`* est utilisée pour déterminer si un lien est un lien de sortie, à savoir un lien qui permet à un visiteur de quitter votre site. Le lien apparaît dans le rapport des liens de sortie, que la fenêtre cible soit une fenêtre contextuelle ou qu’il s’agisse de la fenêtre existante. Le suivi des liens de sortie est effectué uniquement si *`trackExternalLinks`* est définie sur `"true"`. (Voir [Suivi des liens](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) dans la documentation relative à Dynamic Tag Management pour plus d’informations sur la façon dont Dynamic Tag Management gère les liens de sortie.) Les filtres de *`linkInternalFilters`* ne sont pas sensibles à la casse.

La liste des filtres de *`linkInternalFilters`* s’applique par défaut au domaine et au chemin d’accès de tous les liens. Si la variable *`linkLeaveQueryString`* est définie sur `"true"`, les filtres s’appliquent à l’intégralité de l’URL (domaine, chemin et chaîne de requête). Les filtres sont toujours appliqués au chemin absolu de l’URL, même si un chemin relatif est utilisé comme valeur href.

Sachez que tous les domaines de votre site (ainsi que tout partenaire qui utilise votre fichier JavaScript) sont inclus dans *`linkInternalFilters`*. Si tous les domaines ne sont pas inclus dans la liste, tous les liens qui y sont associés sont considérés comme des liens de sortie, ce qui a pour effet d’augmenter le nombre d’appels au serveur envoyés. Si vous souhaitez que plusieurs domaines ou entreprises utilisent un seul fichier [!DNL AppMeasurement] pour JavaScript, vous pouvez envisager de renseigner *`linkInternalFilters`* la page, en remplaçant la valeur spécifiée dans le fichier JavaScript. S’il existe des domaines mineurs qui redirigent immédiatement vers votre domaine principal, ils ne doivent pas nécessairement être inclus dans la liste.

L’exemple suivant illustre l’utilisation de cette variable. Dans cet exemple, l’URL de la page est `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## Syntaxe et valeurs possibles

La variable *`linkInternalFilters`* est une liste de caractères ASCII séparés par des virgules. Aucun espace n’est autorisé.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Exemples

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Insérez, dans la liste des filtres, tous les domaines sous lesquels le fichier [!DNL AppMeasurement] pour JavaScript peut être diffusé.
* Vérifiez régulièrement le rapport [!UICONTROL Chemins] &gt; [!UICONTROL Entrées et sorties] &gt; [!UICONTROL Liens de sortie] pour vous assurer que toutes les entrées qu’il contient sont correctes.

* Consultez régulièrement les contrats conclus avec les partenaires afin de déterminer s’ils contiennent des restrictions en termes de suivi des liens. Par exemple, vous pouvez ne pas être autorisé à effectuer le suivi des liens qui apparaissent dans des publicités de partenaires. Filtrez les liens des partenaires en ajoutant leur domaine à la variable *`linkInternalFilters`*

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## Suivi automatique des liens de sortie et des téléchargements de fichiers

Il est possible de configurer le fichier JavaScript pour un suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres qui définissent les types des fichiers téléchargés et les liens de sortie.

Les paramètres de contrôle du suivi automatique sont les suivants :

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

Les paramètres `trackDownloadLinks` and `trackExternalLinks` determine if automatic file download and exit link tracking are enabled. Lorsqu’il est activé, tout lien dont le type de fichier correspond à l’une des valeurs dans `linkDownloadFileTypes` est automatiquement suivi en tant que téléchargement de fichier. Tout lien dont l’URL ne contient aucune des valeurs dans `linkInternalFilters` est automatiquement suivi comme lien de sortie.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

### Exemple 1

Les types de fichiers `.jpg` et `.aspx` ne sont pas inclus dans `linkDownloadFileTypes` ci-dessus. Par conséquent, aucun clic sur ces types n’est automatiquement suivi et rapporté comme des téléchargements de fichiers.

The parameter `linkLeaveQueryString` modifies the logic used to determine exit links. When `linkLeaveQueryString`=false, exit links are determined using only the domain, path, and file portion of the link URL. When `linkLeaveQueryString`=true, the query string portion of the link URL is also used to determine an exit link.

### Exemple 2

Avec les paramètres suivants, l’exemple ci-dessous sera compté comme un lien de sortie :

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### Exemple 3

Avec les paramètres suivants, le lien ci-dessous n’est pas comptabilisé comme un lien de sortie :

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*Remarque : Un lien unique peut uniquement être suivi comme téléchargement de fichier ou lien de sortie, et le téléchargement de fichier a la priorité. Si un lien est à la fois un lien de sortie et un téléchargement de fichier en fonction des paramètres`linkDownloadFileTypes`et`linkInternalFilters`, il est suivi et signalé comme un téléchargement de fichier et non comme un lien de sortie.*
