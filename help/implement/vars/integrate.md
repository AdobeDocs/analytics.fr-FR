---
title: Intégration de module
description: Le module Integrate permet aux partenaires Adobe d’intégrer leurs efforts de collecte de données à votre organisation.
translation-type: tm+mt
source-git-commit: e8f22d3e9efd57de0134a3c4ff55d0ad148f3df1

---


# Intégration de module

Le module Integrate permet aux partenaires Adobe d’intégrer leurs efforts de collecte de données à votre organisation. Cette intégration donne la possibilité d’établir une connexion de données bidirectionnelle. En règle générale, l’utilisation du module Integrate est gérée par un partenaire Adobe.

> [!NOTE] La demande de données de partenaire dans votre implémentation peut augmenter les délais entre le chargement de pages et l’envoi de données aux serveurs de collecte de données Adobe. Si un visiteur charge une nouvelle page avant l’envoi des données, cette page n’est pas enregistrée.

## Processus du module Integrate

1. Un visiteur de votre site charge une page qui initie une demande `get` en faveur de données de partenaire.
2. Le partenaire Adobe reçoit la demande `get` et regroupe les variables appropriées dans un objet JSON. L’objet JSON est renvoyé.
3. Votre site reçoit l’objet JSON et appelle `setVars` pour affecter les informations contenues dans l’objet JSON aux variables Adobe Analytics.
4. Une demande d’image est envoyée aux serveurs de collecte de données Adobe.

## Implémentation du module Integrate

Une organisation travaillant avec un partenaire Adobe peut suivre cette procédure pour commencer à utiliser le module Integrate.

### Obtention du code de module Integrate

L’obtention du code de module requiert un utilisateur disposant de l’accès Administrateur de produit ou appartenant à un profil de produit ayant accès au gestionnaire de code. La méthode d’obtention du code de module est la même pour toutes les méthodes d’implémentation, y compris Adobe Experience Platform Launch.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
1. Dans le volet de navigation supérieur, cliquez sur [!UICONTROL Administration] > [!UICONTROL Gestionnaire de code].
1. Téléchargez la bibliothèque AppMeasurement pour JavaScript la plus récente.
1. Une fois le fichier téléchargé, décompressez-le et recherchez `AppMeasurement_Module_Integrate.js`.

### Placez le module Integrate dans votre implémentation

La mise en œuvre du module Integrate sur votre site nécessite l’accès à Adobe Experience Platform Launch. Si vous utilisez une implémentation JavaScript héritée, vous devez accéder au code source du site web de votre entreprise.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété Launch que vous souhaitez modifier.
3. Cliquez sur l’onglet Extensions, puis sur Configurer sous Adobe Analytics.
4. Ouvrez l’accordéon « Configurer l’outil de suivi à l’aide du code personnalisé », puis cliquez sur « &lt;/> Ouvrir l’éditeur ».
5. Collez le code du module Integrate dans la fenêtre modale du code. Lorsque vous avez terminé, cliquez sur Enregistrer.

## Méthodes du module Integrate

Une fois le module Integrate mis en œuvre, utilisez ces méthodes pour le configurer afin qu’il envoie et reçoive des données du partenaire Adobe souhaité.

### add

La méthode `add` instancie un objet partenaire, qui sert de boutique intermédiaire de données variables lors du partage de données entre les systèmes partenaires et votre implémentation. Cette méthode est requise pour toutes les intégrations. Un objet partenaire distinct doit être utilisé pour chaque partenaire unique si plusieurs partenaires sont utilisés dans une seule implémentation.

```JavaScript
s.Integrate.add("<partner_name>");
```

En règle générale, votre organisation travaille avec un partenaire Adobe pour déterminer la valeur du nom du partenaire.

### beacon

La méthode `beacon` crée une demande d’image et la dirige vers l’URL spécifiée. Ces demandes d’image sont différentes des demandes d’image standard. La méthode de balise envoie généralement des données au partenaire Adobe plutôt qu’à des serveurs de collecte de données Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

En règle générale, votre organisation travaille avec le partenaire Adobe pour déterminer la valeur du nom du partenaire. Les chaînes de requête incluses dans l’URL sont facultatives et dépendent du partenaire. Le module Integrate inclut automatiquement une chaîne de requête contenant un nombre aléatoire afin d’empêcher la mise en cache du navigateur.

### delay

Adobe travaille avec des équipes en interne pour que cette méthode soit documentée.

### get

La méthode `get` permet à un client d’importer des variables de partenaire et de les stocker dans l’objet partenaire. Une fois que les données se trouvent dans l’objet partenaire, elles peuvent être affectées aux variables Analytics et envoyées dans une demande d’image. Cette méthode appelle une URL dirigée vers un objet JSON contenant les données souhaitées.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nom du partenaire :** en règle générale, votre organisation travaille avec le partenaire Adobe pour déterminer la valeur du nom du partenaire.
* **URL vers l’objet JSON :** URL permettant d’accéder à objet JSON qui contient les variables de partenaire à intégrer dans une demande d’image.
* **Paramètre(s) de chaîne de requête :** informations sur le compte du partenaire qui identifient votre organisation dans le système du partenaire. Le partenaire Adobe utilise ces informations pour identifier votre jeu de données.

Le module Integrate ajoute automatiquement d’autres chaînes de requête à l’URL. Une chaîne de requête var spécifie le nom de l’objet JSON attendu par le module de la part du partenaire. Un nombre aléatoire est également ajouté pour empêcher la mise en cache du navigateur.

### ready

Adobe travaille avec des équipes en interne pour que cette méthode soit documentée.

### useVars

La méthode `useVars` permet au client de partager des valeurs de variable avec un partenaire Adobe.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

En règle générale, votre organisation travaille avec un partenaire Adobe pour déterminer les valeurs du nom du partenaire et celles utilisées par le partenaire.

### setVars

La méthode `setVars` permet au client de renseigner les variables Analytics à l’aide des données de partenaire récupérées. Les données du partenaire peuvent être obtenues à partir d’une méthode `get`, d’une affectation statique ou de tout autre mécanisme qui renseigne l’objet partenaire à l’aide de données.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

En règle générale, votre organisation travaille avec un partenaire Adobe pour déterminer les valeurs du nom du partenaire et celles utilisées par le partenaire.

### script

La méthode `script` permet à un partenaire Adobe d’appeler du code JavaScript supplémentaire à partir du site du partenaire si certaines conditions sont remplies (par exemple, si la variable de campagne est définie).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

En règle générale, votre organisation travaille avec le partenaire Adobe pour déterminer la valeur du nom du partenaire. Les chaînes de requête incluses dans l’URL sont facultatives et dépendent du partenaire. Le module Integrate inclut automatiquement une chaîne de requête contenant un nombre aléatoire afin d’empêcher la mise en cache du navigateur.
