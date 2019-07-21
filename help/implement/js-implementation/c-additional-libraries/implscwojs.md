---
description: Mise en œuvre d’Analytics à l’aide d’une balise d’image HTML (demande d’image codée en dur).
keywords: Implémentation d'Analytics ; html image tag ; demande d'image codée en dur
seo-description: Mise en œuvre d’Analytics à l’aide d’une balise d’image HTML (demande d’image codée en dur).
seo-title: Mise en œuvre d'Analytics à l'aide de balises d'image HTML
solution: Analytics
title: Mise en œuvre d'Analytics à l'aide de balises d'image HTML
topic: Développeur et mise en œuvre
uuid: 0 c 098 a 57-7 c 71-4362-812 c -36 e 37848 a 5 ae
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mise en œuvre d'Analytics à l'aide de balises d'image HTML

Mise en œuvre d’Analytics à l’aide d’une balise d’image HTML (demande d’image codée en dur).

Le navigateur demande ensuite l’image. Les données se déplacent avec cette demande d’image via des variables dans la chaîne de requête de la demande. JavaScript combine les variables au niveau du navigateur avec des variables au niveau de la page pour offrir une solution de collecte de données complète. Dans certains cas, une balise d’image entièrement créée par le serveur se révèle appropriée. La liste ci-dessous répertorie les éléments standard d’une implémentation JavaScript :

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> Code HTML </td> 
   <td> Cette partie comprend le code JavaScript placé dans des images (ou modèles) HTML qui définissent la valeur des variables JavaScript. </td> 
  </tr> 
  <tr> 
   <td> Bibliothèque JavaScript </td> 
   <td> <p>Ce fichier contient du code courant qui effectue les opérations suivantes : </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">Interrogation du navigateur pour connaître diverses propriétés, telles que la version de JavaScript, la version du système d’exploitation, la taille et la résolution du moniteur utilisé, ainsi que d’autres variables. </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">Codage et concaténation de toutes les variables dans une demande d’image (&lt;img&gt;) qui les transporte vers les serveurs de collecte de données. Il fait ensuite référence à un fichier de bibliothèque JavaScript qui est chargé et exécuté. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Balise &lt;noscript&gt; </td> 
   <td> Une version simplifiée de la demande d’image est placée dans une balise &lt;noscript&gt; qui s’exécute si l’utilisateur a désactivé JavaScript ou ne dispose pas de fonctionnalités JavaScript. Cette partie de l’implémentation est facultative et s’applique généralement à environ 2 % des internautes. </td> 
  </tr> 
 </tbody> 
</table>

JavaScript peut détecter les paramètres du navigateur qui ne sont pas accessibles au serveur, comme par exemple la hauteur/largeur de fenêtre, la résolution du moniteur et les modules externes Netscape. L’utilisation d’une méthode côté serveur pour créer une balise d’image empêche la capture de ces variables. Le code JavaScript définit un nombre aléatoire dans la demande d’image afin de surmonter la mise en cache du serveur proxy et du navigateur. Cela permet un suivi précis de toutes les pages vues. Dans certains cas, les avantages du code côté serveur surpassent ceux du code JavaScript. En voici un aperçu :

* JavaScript est particulièrement précis (de 98 à 100 %). Il arrive qu’un niveau de précision extrême soit souhaité, même dans le cas où un utilisateur clique rapidement vers une autre page avant l’exécution du code JavaScript. La création de la balise d’image côté serveur augmente le degré de précision de plusieurs points de pourcentage.
* Suivi des événements de conversion, tels que les achats, où la précision revêt une importance capitale.
* Cette stratégie peut également être utilisée pour renseigner complètement la demande d'image dans la variable <noscript> pour le suivi des utilisateurs sans JavaScript ou avec JavaScript désactivé.

>[!NOTE]
>
>L'utilisation de balises d'image générées par le serveur nécessite une durée de mise en œuvre supplémentaire et est plus difficile à déboguer, déployer et gérer. Adobe conseille vivement à ses clients d’utiliser la collecte de données JavaScript sur chaque page lorsque cela s’avère possible. Notez cependant que cette méthode d’implémentation ne permet pas la collecte ou la prise en charge de certains rapports ou fonctionnalités, dont la mise en correspondance des clics des visiteurs, les liens de téléchargement, les liens de sortie et les variables de navigateur (largeur/hauteur du navigateur, etc.).

