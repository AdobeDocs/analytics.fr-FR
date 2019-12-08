---
description: Comment mettre en œuvre Analytics dans les Instant Articles de Facebook ?
keywords: Analytics Implementation;embed;custom variable;custom event;visitor tracking;tracking;limitations
title: Instant Articles de Facebook
topic: Developer and implementation
uuid: 04b6366b-7c52-4dae-b2dd-bb6b78fd409c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Instant Articles de Facebook

Comment mettre en œuvre Analytics dans les Instant Articles de Facebook ?

Les Instant Articles de Facebook constituent un nouveau moyen pour les éditeurs de créer des articles interactifs instantanés sur Facebook. Ils peuvent charger le contenu jusqu’à dix fois plus rapidement que le web mobile.

Adobe Analytics peut être incorporé dans les Instant Articles Facebook afin d’effectuer le suivi du comportement des visiteurs qui interagissent avec le contenu. Puisque le contenu de l’éditeur se trouve dans l’application Facebook et non sur les sites web de l’éditeur, la méthode du balisage diffère légèrement de celle d’une mise en œuvre Analytics standard.

## Étape 1. Incorporation d’une page HTML Analytics {#section_0DF847F8BA624CF8A239C10003A39E59}

Lorsque vous créez votre contenu Instant Article de Facebook, vous pouvez incorporer le contenu HTML d’analyse dans une iFrame. Par exemple :

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## Étape 2 : Modification du code HTML Analytics {#section_76707B51D63A47FF833C2D3FFF8412B4}

L’exemple de code HTML ci-dessous peut servir à capturer les statistiques depuis les articles instantanés. Ce fichier est généralement hébergé sur l’un des serveurs web de votre entreprise. À chaque chargement d’un Instant Article, le fichier est chargé dans un iframe comme décrit dans la première étape, ce qui déclenche l’envoi des données d’analyse vers Adobe.

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**Modification de cet exemple de code HTML en fonction de votre mise en œuvre spécifique**

1. Il est recommandé d’héberger les dernières copies des versions non modifiées des fichiers VisitorAPI.js et AppMeasurement.js dans un répertoire commun sur les serveurs web de votre entreprise.

   Il est possible de télécharger ces fichiers depuis le gestionnaire de code dans l’interface utilisateur d’Analytics, si nécessaire.

1. Incluez les variables de la configuration standard de votre mise en œuvre Analytics :

   1. L’identifiant d’entreprise Experience Cloud.
   1. L’identifiant de suite de rapports où sera capturé le trafic Instant Article de Facebook.
   1. Le domaine du serveur de suivi de votre entreprise.
   1. La variable de l’espace de noms du visiteur. **Remarque :** La plupart de ces valeurs se trouvent dans votre mise en œuvre Analytics standard. L’assistance clientèle ou le conseiller Adobe peut vous aider à savoir quelles sont les valeurs correctes, si nécessaire.

1. [Définition du suivi personnalisé des variables et événements](/help/implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B).
1. Incluez la syntaxe de la demande d’image de page vue `( s.t())`.

## Étape 3. Définition du suivi personnalisé des variables et événements {#section_932C41BD21154C25B99389299BDF3E0B}

Vous pouvez effectuer le suivi des variables et des événements personnalisés dans votre code HTML Analytics selon différentes méthodes. La première méthode consiste à inclure la logique JavaScript dans votre configuration personnalisée, comme vous le feriez avec une mise en œuvre Analytics standard. Par exemple, pour définir la valeur d’une prop, il vous suffit d’utiliser la même syntaxe que celle que vous utiliseriez dans une mise en œuvre régulière :

```
s.prop10 = "Facebook Instant Article";
```

Vous pouvez également envoyer dynamiquement les variables à l’iframe en reprenant les paramètres de la chaîne de requête dans l’attribut `src` de l’iframe. Par exemple :

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

Ces paramètres de chaîne de requête peuvent être définis consécutivement dans la section des variables personnalisées du code HTML JavaScript Analytics en insérant la fonction `Util.getQueryParam`[!DNL AppMeasurement] dans la bibliothèque par défaut, comme suit :

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## Suivi des visiteurs {#section_60F0C77659534949831E85B5FD9AE81E}

Tant que la page HTML Analytics est hébergée sur votre serveur web, Adobe peut prendre en charge votre politique de confidentialité existante pour tous les Instant Articles de Facebook. Ainsi, si un utilisateur s’est désabonné du suivi sur votre site principal, il est également désabonné du suivi sur tous les Instant Articles de Facebook, sans aucune autre intervention de votre part. L’utilisation de cette page utilitaire signifie également que le service d’identité (identifiant visiteur) est pris en charge, de sorte que vous pouvez intégrer les mesures et les variables saisies dans vos Instant Articles de Facebook avec le reste d’Experience Cloud. (Par exemple pour les publicités ciblées à l’aide d’[!DNL Adobe Audience Manager]).

## Limitations du suivi {#section_1EE1BB069A3148DB9446371AFE196567}

Cette méthode présente quelques problèmes dont il convient de tenir compte. Les valeurs DOM, généralement accessibles uniquement par le biais de JavaScript sur un Instant Article de Facebook (tel un référent) ne pourront pas être récupérées dans l’iframe pour le suivi. Toutefois, les rapports des technologies standard (navigateur, appareil, taille d’écran ou résolution, notamment) devraient fonctionner normalement. Par ailleurs, la valeur pageURL peut être obtenue en référençant [!DNL document.referrer] depuis votre page utilitaire.

## Et après ? {#section_A170A10E2A3642A784DF720195DA8B38}

[!DNL Adobe Analytics] est ravie de collaborer avec Facebook et nos éditeurs afin de proposer aux éditeurs des capacités d’analyse de pointe sur le web mobile, dans un environnement utilisateur étonnamment rapide. Nous nous efforçons de créer une excellente solution à long terme qui répondra aux besoins d’analyses en constante évolution de nos clients.

Le projet Facebook Instant Article évolue rapidement et constamment. Pensez à consulter régulièrement les mises à jour. Il y aura certainement des changements tandis que nous perfectionnons nos intégrations et que davantage d’éditeurs adoptent les Instant Articles de Facebook.

Si vous avez des questions ou des problèmes, consultez votre conseiller ou l’assistance clientèle Adobe.
