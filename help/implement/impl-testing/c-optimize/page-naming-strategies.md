---
description: La variable pageName doit être renseignée avec un identifiant de page lisible et intuitif.
keywords: Mise en œuvre d’Analytics
seo-description: La variable pageName doit être renseignée avec un identifiant de page lisible et intuitif.
seo-title: Stratégies de nommage de page
solution: Analytics
title: Stratégies de nommage de page
topic: Développeur et mise en œuvre
uuid: a 829 d 0 c 7-6 ebf -459 a-b 403-5 e 9 c 05161 e 5 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Stratégies de nommage de page

La variable pageName doit être renseignée avec un identifiant de page lisible et intuitif.

You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

While the *`pageName`* variable is central to identifying user behavior, Adobe recommends using multiple variables to indicate page information. Les meilleures stratégies de dénomination de page utilisent une variable différente pour chaque niveau de hiérarchie du site, comme illustré ci-dessous :

* La variable *`channel`* peut être utilisée pour indiquer la section du site.
* The *`pageName`* variable can be used to show content type.
* Une variable [!UICONTROL d’aperçu personnalisée] (prop1) peut être utilisée pour le contenu détaillé.

Les niveaux de détail varient selon la propriété, comme illustré ci-dessous :

| Variable | Niveau de détails | Exemple |
|---|---|---|
| Canal | Section générale | Electronique |
| Prop1 | Sous-section | Sports : Sports locaux |
| PageName | Description générale du contenu | Prêts : Prêt hypothécaire : Comparaison des taux |
| Prop2 | Description détaillée du contenu | Electronique : PC portable : Spécifications détaillées : IBM Thinkpad T20 |

Plus le site comporte de niveaux, plus vous devez utiliser de variables pour identifier le contenu de la page. Les entreprises peuvent également trouver intéressant de faire en sorte que les variables se chevauchent. Par exemple, une variable plus détaillée peut contenir des informations non seulement sur le produit affiché, mais aussi sur la section et la sous-section du site. Cela peut s’avérer particulièrement utile lorsqu’un produit ou un article apparaît dans plusieurs sections du site.

Les stratégies de dénomination de page suivantes expliquent comment renseigner la variable *`pageName`* . Bien qu’il soit tentant de choisir la stratégie de dénomination de page la plus facile à mettre en œuvre, cette stratégie détermine en grande partie la facilité d’utilisation de tous les rapports [!UICONTROL Chemin] et [!UICONTROL Page]. Faites preuve de bon sens lors du choix des noms de page.

## Nom unique pour chaque page {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

La méthode la plus intéressante consiste à attribuer à chaque page un identifiant unique, facile à comprendre par tous les utilisateurs [!DNL Analytics] de votre société. Parmi les exemples de noms de pages, citons notamment Page d’accueil, Page d’accueil du rayon Electronique et Sports : Sports locaux : Lycée.

La plupart des utilisateurs [!DNL Analytics] trouvent que les noms de page hiérarchiques sont utiles pour identifier à la fois l’emplacement de la page sur le site et son objectif. Le tableau suivant montre quelques exemples de noms de page pour divers secteurs d’activité :

| Conversion | Média | Finances |
|---|---|---|
| Page d’accueil | Page d’accueil | Page d’accueil |
| Electronique | Technologie | Prêts hypothécaires |
| Electronique : Ordinateurs portables | Technologie : Nouveaux gadgets | Prêts hypothécaires : Comparaison des taux |
| Electronique : Ordinateurs portables : Page des produits | Technologie : Nouveaux gadgets : Page de l’article | Prêts hypothécaires : Comparaison des taux : 10 ans à taux fixe |

## Chemin d’accès au fichier (et non l’URL complète) {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

Pour certains sites, le chemin d’accès au fichier est clair et facile à lire. Dans ce cas, un utilisateur peut lire l’URL et déterminer à quelle page le chemin fait référence. Si c’est le cas de votre site, vous pouvez utiliser une variable côté serveur pour renseigner la variable *`pageName`* avec le chemin d’accès au fichier, comme illustré ci-dessous :

```js
s.pageName="<%= file_path %>"
```

Adobe does not recommend leaving the *`pageName`* blank, (which results in using the full URL of the page) even though you may be tempted to do so. The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* Il se peut que le domaine et le chemin d’une page ne s’affichent pas toujours de manière identique. Par exemple, les quatre URL suivantes renvoient une page unique :

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports.

* Certaines pages (les formulaires, par exemple) publient vers elles-mêmes, effaçant par là même toute distinction entre le formulaire d’origine et le résultat.
* Lorsque la page est traduite dans une autre langue par des moteurs de recherche ou d’autres outils en ligne, l’URL de la page est celle du moteur de recherche (et non l’URL de votre site).

## Code HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. Certains navigateurs interprètent le titre HTML d’une façon différente que d’autres, ce qui peut entraîner la réception par [!DNL Analytics] de noms de page différents de différents navigateurs.

La bonne pratique d’utilisation du titre HTML consiste à copier les titres existants pour chaque page dans une variable distincte ou dans un élément de gestion du contenu. Lorsque vous décidez d’apporter des modifications au titre HTML pour l’optimisation du moteur de recherche ou à d’autres fins, le nom des pages dans [!DNL Analytics] n’est pas modifié. Si un nom de page change dans [!DNL Analytics], il devient une nouvelle page et il n’est pas lié à l’ancien nom, quelle que soit l’URL associée.
