---
title: Mise en œuvre avec des Instant Articles de Facebook
description: Mettez en œuvre Adobe Analytics sur les pages Instant Article de Facebook.
translation-type: ht
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Mise en œuvre avec des Instant Articles de Facebook

Les Instant Articles de Facebook permettent aux éditeurs de créer rapidement des articles interactifs sur Facebook. Ils peuvent charger le contenu jusqu’à dix fois plus rapidement que le Web mobile.

Vous pouvez incorporer Adobe Analytics aux Instant Articles de Facebook pour suivre le comportement des visiteurs. Puisque le contenu de l’éditeur se trouve dans l’application Facebook et non sur les sites web de l’éditeur, la méthode du balisage diffère légèrement de celle d’une mise en œuvre Analytics standard.

## Processus

Le processus global de mise en œuvre d’Adobe Analytics est le suivant :

1. Créez une page `stats.html`. Codez cette page pour extraire les paramètres de chaîne de requête de l’URL et affecter chaque paramètre à une variable Analytics.
1. Hébergez la page `stats.html` sur votre serveur web.
1. Mettez en œuvre Analytics sur l’article Instant Facebook en référençant le fichier `stats.html` dans un iframe.
1. Incluez les paramètres de chaîne de requête dans l’attribut `src` d’iframe.

### Étape 1 : créez une page `stats.html`

L’exemple de code HTML ci-dessous peut servir à capturer les statistiques depuis les articles instantanés. Ce fichier est généralement hébergé sur l’un des serveurs web de votre entreprise. Chaque fois qu’un Instant Article est chargé, il charge le fichier dans un iframe, ce qui déclenche l’envoi de données à Adobe.

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;

      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### Étape 2 : hébergez la page `stats.html` sur votre serveur web

Adobe conseille d’héberger votre page `stats.html` avec la dernière version de `AppMeasurement.js` et `VisitorAPI.js`. Contactez les équipes d’ingénieurs appropriées de votre entreprise pour héberger ce fichier au bon endroit.

### Étape 3 : référencez `stats.html` sur chaque page Instant Article de Facebook

Lorsque vous créez votre contenu Instant Article de Facebook, incorporez le contenu HTML d’analyse dans une iFrame. Par exemple :

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Étape 4 : définissez le suivi personnalisé des variables et événements

Vous pouvez effectuer le suivi des variables et des événements personnalisés dans votre code HTML Analytics avec deux méthodes différentes :

* Inclure directement les valeurs et les événements de variable dans la page `stats.html`. Les variables définies ici sont meilleures pour les valeurs qui sont généralement les mêmes pour tous les Instant Articles de Facebook.
* Inclure des valeurs de variable dans une chaîne de requête référençant l’iframe. Cette méthode vous permet d’envoyer des valeurs de variable de l’Instant Article de Facebook à l’iframe qui héberge le code Analytics.

L’exemple suivant illustre plusieurs variables personnalisées incluses dans une chaîne de requête. Le code JavaScript à l’intérieur de `stats.html` vérifie ensuite la chaîne de requête à l’aide de `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

> [!NOTE] La dimension Référent n’est pas automatiquement suivie en raison de la nature des iframes. Veillez à inclure cette dimension dans votre chaîne de requête si vous souhaitez en effectuer le suivi.

## Instant Articles et confidentialité de Facebook

Tant que la page HTML Analytics est hébergée sur votre serveur web, Adobe peut prendre en charge votre politique de confidentialité existante pour tous les Instant Articles de Facebook. Si un utilisateur choisit de ne pas effectuer de suivi sur votre site principal, il choisit également de ne pas effectuer de suivi sur tous vos Instant Articles de Facebook. La page utilitaire prend également en charge Adobe Experience Cloud Identity Service afin que vous puissiez intégrer les données Instant Article de Facebook au reste d’Experience Cloud.
