---
title: Trafic interne
description: Le module externe Trafic interne identifie dynamiquement les visiteurs provenant d'un réseau interne.
seo-description: Internal Traffic Plugin
seo-title: Internal Traffic Plugin
translation-type: tm+mt
source-git-commit: 8c2b28ee1ca2e9448b9dec99a0505d0fae525e94

---


# Trafic interne

Le module externe Trafic interne identifie dynamiquement les visiteurs provenant d'un réseau interne.

L'identification du trafic interne et externe favorise la précision de tous les types de rapport en fournissant un mécanisme qui filtre et segmente les données collectées. Implémenté correctement, cela élimine également la nécessité d'une règle VISTA ou de règles de traitement qui sont des approches classiques pour identifier ce trafic.

## Comment le module externe Trafic interne fonctionne-t-il ?

Le module externe tente de charger un fichier qui ne serait disponible que dans votre réseau interne/intranet, c'est-à-dire un pixel transparent 1 x 1. S'il est chargé correctement, le trafic pour ce visiteur est identifié comme interne. Tout autre élément serait un trafic externe.

## Considérations

* Le seul inconvénient de cette approche est qu'une erreur 404 est affichée dans la console du navigateur pour les visiteurs externes sur la première page de leur visite. Cela n'a aucune incidence sur l'expérience de l'utilisateur.
* Nous suggérons vivement que vous obteniez une approbation auprès de votre équipe réseau ou infosec avant de tenter de charger un pixel hébergé en interne.
* Bien que le module externe ne déplacera pas le trafic vers une autre suite de rapports ou l'exclut des rapports (comme il peut s'effectuer avec une règle VISTA), la logique personnalisée peut être incluse avec son implémentation, de sorte que cette fonctionnalité puisse avoir lieu côté client.

## Mise en œuvre

1. Ajoutez votre pixel Intranet : Vous pouvez ajouter n'importe quel type de fichier sur votre intranet que le module externe tente d'accéder. Il est recommandé d'utiliser un pixel transparent 1 x 1. Elle doit être placée à un emplacement de votre Intranet accessible à partir de vos réseaux internes.
1. Configuration d'une evar : Une evar doit être ajoutée au sein de votre suite de rapports de destination. Il doit avoir une expiration de « Visite » et une attribution de « Valeur d'origine (première) ».
1. Définissez l'URL interne : Dans les variables de configuration appmeasurement et avant l'instanciation de doplugins, définissez la variable URL interne (s. inturl) pour le pixel ou l'autre fichier peut être utilisée pour la vérification du trafic. Par exemple : `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modifiez doplugins et définissez l'evar : Le module externe peut alors être initialisé en incluant cette ligne de code dans la section doplugins du code de la bibliothèque appmeasurement, en utilisant l'evar définie à l'étape 1 : `s.eVarXX = s.intCheck();`
La valeur de la variable est définie sur « interne » ou « externe ».
1. Ajoutez le code source du module externe : Incluez le code du module externe sous la section doplugins de votre fichier appmeasurement.

## Code source du module externe

Ajoutez ce code sous la section doplugins de votre bibliothèque appmeasurement.

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## Autres remarques

* Testez toujours les installations de plug-in pour vous assurer que la collecte de données se produit comme prévu avant de les déployer dans un environnement de production.
* Votre implémentation peut utiliser un autre nom d'objet que l'objet Adobe Analytics par défaut. Si tel est le cas, veuillez mettre à jour le nom de l’objet en conséquence.
* Si vous utilisez un système de gestion des balises, procédez comme suit pour mettre à jour doplugins et les autres modules externes personnalisés.
