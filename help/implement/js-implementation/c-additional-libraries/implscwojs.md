---
description: Mise en œuvre d’Analytics à l’aide d’une balise d’image HTML (demande d’image codée en dur).
keywords: Analytics Implementation;html image tag;hardcoded image request
title: Mise en œuvre d’Analytics à l’aide de balises d’image HTML
topic: Developer and implementation
uuid: 0c098a57-7c71-4362-812c-36e37848a5ae
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mise en œuvre d’Analytics à l’aide de balises d’image HTML

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
* Cette stratégie peut également être utilisée pour renseigner complètement la demande d’image dans la <noscript> balise pour le suivi des utilisateurs sans JavaScript ou avec JavaScript désactivé.

> [!NOTE] S’agissant de l’utilisation de balises d’image générées par le serveur, l’implémentation nécessite davantage de temps. Elle se révèle, en outre, plus difficile à déboguer, à déployer et à gérer. Adobe conseille vivement à ses clients d’utiliser la collecte de données JavaScript sur chaque page lorsque cela s’avère possible. Notez cependant que cette méthode d’implémentation ne permet pas la collecte ou la prise en charge de certains rapports ou fonctionnalités, dont la mise en correspondance des clics des visiteurs, les liens de téléchargement, les liens de sortie et les variables de navigateur (largeur/hauteur du navigateur, etc.).

