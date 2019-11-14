---
title: Trafic interne
description: Le module Trafic interne identifie dynamiquement les visiteurs provenant d’un réseau interne.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Trafic interne

Le module Trafic interne identifie dynamiquement les visiteurs provenant d’un réseau interne.

L’identification du trafic interne et externe permet d’obtenir une plus grande précision dans tous les types de rapports, en fournissant un mécanisme qui filtre et segmente les données collectées. S’il est mis en œuvre correctement, il peut également éliminer la nécessité d’une règle VISTA ou d’une règle de traitement, qui sont des approches classiques pour identifier ce trafic.

## Comment fonctionne le module Trafic interne ?

Le module externe tente de charger un fichier qui ne serait disponible que dans votre réseau interne/intranet, c’est-à-dire un pixel transparent 1x1. S’il est correctement chargé, le trafic de ce visiteur est considéré comme interne. Toute autre chose serait alors considérée comme du trafic externe.

## Considérations

* Le seul inconvénient de cette approche est qu’une erreur 404 s’affiche dans la console du navigateur pour les visiteurs externes sur la première page de leur visite. Cela n’affectera pas l’expérience client.
* Nous vous conseillons vivement d’obtenir l’approbation de votre équipe Network ou InfoSec avant d’essayer de charger un pixel hébergé en interne.
* Bien que le module externe ne déplace pas le trafic vers une autre suite de rapports ou ne l’exclue pas de la création de rapports (comme cela peut être le cas avec une règle VISTA), la logique personnalisée peut être incluse avec son implémentation, de sorte que cette fonctionnalité puisse avoir lieu côté client.

## Mise en œuvre

1. Ajouter votre pixel intranet : vous pouvez ajouter sur votre intranet n’importe quel type de fichier auquel le module externe tenterait d’accéder. Un pixel transparent 1x1 est recommandé. Il doit être placé dans un emplacement de votre Intranet qui est facilement accessible depuis votre ou vos réseaux internes.
1. Configurer une eVar : une eVar doit être ajoutée dans votre suite de rapports de destination. Elle doit avoir une expiration de "Visite" et une attribution de "Valeur originale (première)".
1. Définir l’URL interne : dans les variables de configuration AppMeasurement et avant l’instanciation de doPlugins, définissez la variable d’URL interne (s.intURL) du pixel ou d’un autre fichier pouvant être utilisée pour la vérification du trafic. Par exemple : `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to "internal" or "external".
1. Ajouter le code source du module externe : ajoutez le code du module externe sous la section doPlugins de votre fichier AppMeasurement.

## Code source du module externe

Ajoutez ce code sous la section doPlugins de votre bibliothèque AppMeasurement.

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## Autres notes

* Les installations de module externe doivent toujours faire l’objet de tests afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Votre mise en œuvre peut utiliser un nom d’objet différent de celui de l’objet « s » par défaut d’Adobe Analytics. Si tel est le cas, veuillez mettre à jour le nom de l’objet en conséquence.
* Si vous utilisez un système de gestion des balises, procédez comme suit pour mettre à jour doPlugins et les autres modules externes personnalisés.
