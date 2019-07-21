---
title: Module Integrate
seo-title: Module Integrate pour Adobe Analytics
description: Le module Integrate permet aux partenaires Adobe d'intégrer leurs efforts de collecte de données à votre organisation.
seo-description: Le module Integrate permet aux partenaires Adobe d'intégrer leurs efforts de collecte de données à votre organisation.
translation-type: tm+mt
source-git-commit: dae73042ace20eded9d0caf690a14203827f903a

---


# Module Integrate

Le module Integrate permet aux partenaires Adobe d'intégrer leurs efforts de collecte de données à votre organisation. Cette intégration permet d'établir une connexion bidirectionnelle aux données. En règle générale, l'utilisation du module Integrate est gérée par un partenaire Adobe.

> [!NOTE] La demande de données partenaires dans votre implémentation peut accroître les délais entre le chargement de la page et les données envoyées aux serveurs de collecte de données Adobe. Si un visiteur charge une nouvelle page avant l'envoi des données, cette page n'est pas enregistrée.

## Flux de travaux du module Integrate

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. L'objet JSON est renvoyé.
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. Une demande d’image est envoyée aux serveurs de collecte de données Adobe.

## Implémentation du module Integrate

Une organisation travaillant avec un partenaire Adobe peut utiliser ces étapes pour commencer à utiliser le module Integrate.

### Obtention du code Integrate Module

L'obtention du code du module requiert un utilisateur disposant d'un accès Administrateur de produit ou appartenant à un profil de produit avec accès au Gestionnaire de code. La méthode d'obtention du code du module est la même pour toutes les méthodes d'implémentation, y compris le lancement d'Adobe Experience Platform.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Cliquez sur l'icône 9 carrée dans l'angle supérieur droit, puis cliquez sur le logo Analytics coloré.
1. In the top navigation, click [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. Téléchargez la dernière bibliothèque appmeasurement pour JavaScript.
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### Placer le module Integrate dans votre implémentation

La mise en œuvre du module Integrate sur votre site nécessite l'accès au lancement d'Adobe Experience Platform. Si vous utilisez une implémentation JavaScript héritée, l'accès au code source du site Web de votre organisation est requis.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Cliquez sur la propriété de lancement que vous avez l'intention de modifier.
3. Cliquez sur l'onglet Extensions, puis sur Configurer sous Adobe Analytics.
4. Ouvrez l'accordéon « Configure tracker using custom code », puis cliquez sur &lt;/&gt; Ouvrir l'éditeur '.
5. Collez le code du module Integrate dans la fenêtre modale du code. Cliquez sur Enregistrer une fois terminé.

## Méthodes du module Integrate

Une fois le module Integrate implémenté, utilisez ces méthodes pour le configurer pour envoyer et recevoir des données du partenaire Adobe souhaité.

### ajouter

The `add` method instantiates a partner object, which serves as an intermediate store of variable data when sharing data between partner systems and your implementation. Cette méthode est requise pour toutes les intégrations. Un objet partenaire distinct doit être utilisé pour chaque partenaire unique si plusieurs partenaires sont utilisés dans une implémentation unique.

```JavaScript
s.Integrate.add("<partner_name>");
```

Votre organisation travaille généralement avec un partenaire Adobe pour déterminer la valeur du nom du partenaire.

### balise

`beacon` La méthode crée une demande d'image et la pointe vers l'URL spécifiée. Ces demandes d'image sont différentes des demandes d'image standard. La méthode de balise envoie généralement des données au partenaire Adobe au lieu des serveurs de collecte de données Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

Votre organisation travaille généralement avec le partenaire Adobe pour déterminer la valeur du nom du partenaire. Les chaînes de requête incluses dans l'URL sont facultatives et dépendent du partenaire. Le module Integrate inclut automatiquement une chaîne de requête contenant un nombre aléatoire afin d'éviter la mise en cache du navigateur.

### delay

Adobe collabore avec les équipes en interne pour obtenir cette méthode.

### get

The `get` method lets a client import partner variables and store them in the partner object. Une fois les données dans l'objet partenaire, elles peuvent être affectées aux variables Analytics et envoyées dans une demande d'image. Cette méthode appelle une URL qui pointe vers un objet JSON contenant les données souhaitées.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nom du partenaire :** Votre organisation travaille généralement avec le partenaire Adobe pour déterminer la valeur du nom du partenaire.
* **URL de l'objet JSON :** URL d'un objet JSON qui contient les variables partenaires à incorporer dans une demande d'image.
* **Paramètre (s) de chaîne de requête :** Informations de compte partenaire qui identifient votre organisation dans le système du partenaire. Le partenaire Adobe utilise ces informations pour identifier votre jeu de données.

Le module Integrate ajoute automatiquement d'autres chaînes de requête à l'URL. Une chaîne de requête var spécifie le nom de l'objet JSON que le module attend de la part du partenaire. Un nombre aléatoire est également ajouté pour empêcher la mise en cache du navigateur.

### ready

Adobe collabore avec les équipes en interne pour obtenir cette méthode.

### Usevars

The `useVars` method lets the client share variable values with an Adobe partner.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

Votre organisation travaille généralement avec un partenaire Adobe pour déterminer les valeurs du nom du partenaire et les variables utilisées par le partenaire.

### Setvars

The `setVars` method lets the client populate Analytics variables using partner data retrieved. Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

Votre organisation travaille généralement avec un partenaire Adobe pour déterminer les valeurs du nom du partenaire et les variables utilisées par le partenaire.

### script

The `script` method lets an Adobe partner to call additional JavaScript from the partner site if certain conditions are met (for example, if the campaign variable is set).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

Votre organisation travaille généralement avec le partenaire Adobe pour déterminer la valeur du nom du partenaire. Les chaînes de requête incluses dans l'URL sont facultatives et dépendent du partenaire. Le module Integrate inclut automatiquement une chaîne de requête contenant un nombre aléatoire afin d'éviter la mise en cache du navigateur.
