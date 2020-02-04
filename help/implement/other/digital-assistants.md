---
title: Mise en œuvre d’Analytics pour les assistants numériques
description: Mettez en oeuvre Adobe Analytics sur des assistants numériques, tels qu’Amazon Alexa ou Google Home.
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Mise en oeuvre d’Analytics pour les assistants numériques

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

Avec les récentes avancées dans l&#39;informatique en nuage, l&#39;apprentissage automatique et le traitement du langage naturel, les assistants numériques font désormais partie de la vie quotidienne. Les consommateurs commencent à parler à leurs appareils et s&#39;attendent à ce qu&#39;ils comprennent et réagissent de manière humaine. À mesure que ces plates-formes s’ancrent dans le marché, les marques peuvent présenter leurs services aux consommateurs avec le même réalisme. Par exemple, les clients peuvent poser les questions suivantes :

* « Alexa, demande à ma voiture quand il faut changer son huile. »
* « Cortana, quel est le solde de mon compte courant ? »
* « Siri, envoie 20 $ à John pour le dîner d’hier soir avec mon application bancaire. »

Cette page présente la meilleure façon d’utiliser Adobe Analytics pour mesurer et optimiser ces types d’expériences.

## Présentation de l’architecture de l’expérience numérique

![Fonctionnement de Digital Assistant](assets/Digital-Assitants.png)

À l’heure actuelle, la plupart des assistants numériques suivent la même architecture de niveau supérieur :

1. **Périphérique**: Il y a un appareil (comme un Echo Amazon ou un téléphone) avec un micro qui permet à l&#39;utilisateur de poser une question.
1. **Assistant** numérique : Cet appareil interagit avec le service qui alimente l&#39;assistant numérique. C’est là que la parole est convertie en intentions que la machine peut comprendre et que les détails de la demande sont analysés. Une fois que l’intention de l’utilisateur est comprise, l’assistant numérique la transmet avec les détails de la demande à l’application qui gère cette demande.
1. **&quot;App&quot;**: L’application peut être une application sur téléphone ou une application vocale. L’application a la responsabilité de répondre à la demande. Elle répond à l’assistant numérique qui répond ensuite à l’utilisateur.

## Où mettre en œuvre Analytics

L’application est l’un des meilleurs emplacements où Analytics peut être mis en œuvre. L’application reçoit l’intention et les détails de l’assistant numérique, puis détermine le mode de réponse.

Deux fois au cours d’une demande peuvent s’avérer utiles pour envoyer des données à Adobe Analytics.

1. Lorsque la demande est envoyée à votre application.
1. Après que la demande est renvoyée par l’application.

Si vous souhaitez uniquement enregistrer ce qui s’est passé avec le client à des fins d’optimisation future, envoyez une demande à Adobe Analytics une fois la réponse renvoyée. Vous aurez le contexte complet de la demande et de la réponse du système.

## Nouvelles installations

Pour certains assistants numériques, vous recevez une notification lorsque quelqu’un installe la compétence, en particulier lorsque l’authentification est impliquée. Adobe recommande d’envoyer un événement Install en définissant la variable de données contextuelles `a.InstallEvent=1`. Cette fonctionnalité n’est pas disponible sur tous les assistants numériques, mais elle est utile lorsqu’elle est présente pour étudier la fidélisation. L’exemple de code suivant envoie les valeurs Install event, Install Date et AppID aux variables de données contextuelles.

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Plusieurs assistants ou applications

Il est probable que votre entreprise souhaite des applications pour plusieurs plateformes. La bonne pratique consiste à inclure un ID d’application dans chaque demande. This variable can be set in the `a.AppID` context data variable. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2:

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Identification utilisateur/visiteur

Adobe Analytics utilise [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) pour lier les interactions au fil du temps à la même personne. La plupart des assistants numériques renvoient un `userID` message que vous pouvez utiliser pour conserver l’activité pour différents utilisateurs. Dans la plupart des cas, cette valeur est ce que vous pouvez transmettre en tant qu’identifiant unique. Certaines plateformes renvoient un identifiant qui dépasse les 100 caractères autorisés. Dans ce cas, Adobe recommande de hacher l’identifiant unique sur une valeur de longueur fixe à l’aide d’un algorithme de hachage standard, tel que MD5 ou Sha1.

L’utilisation du service d’ID offre le meilleur rapport qualité-prix lorsque vous mappez des ECID sur différents périphériques (par exemple, Web vers l’assistant numérique). Si votre application est une application mobile, utilisez les SDK de la plateforme d’expérience en l’état et envoyez l’ID utilisateur à l’aide de la `setCustomerID` méthode. However, if your app is a service, use the user ID provided by the service as the ECID, as well as setting it in `setCustomerID`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Sessions

Les assistants numériques étant conversationnels, ils font souvent appel au concept de session. Par exemple :

**Consommateur :** « OK Google, appelle-moi un taxi. »

**Google :** « Bien sûr, pour quelle heure ? ».

**Consommateur :** « 20 h 30 »

**** Google : &quot;Ça a l&#39;air bien, le chauffeur sera à 20h30&quot;

Les sessions sont importantes pour garder le contexte et pour aider à collecter plus de détails afin de rendre l’assistant numérique plus naturel. Lors de l’implémentation d’Analytics sur une conversation, deux opérations s’effectuent au démarrage d’une nouvelle session :

1. **Contactez Audience Manager**: Obtenez les segments appropriés auxquels un utilisateur fait partie afin de pouvoir personnaliser la réponse. (Par exemple, cette personne a actuellement droit à la remise multi-canal.)
2. **Envoyez une nouvelle session ou un nouvel événement** de lancement : Lorsque vous envoyez la première réponse à Analytics, incluez un événement de lancement. Vous pouvez généralement l’envoyer en définissant les données contextuelles de `a.LaunchEvent=1`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Intentions

Chacun des assistants numériques possède des algorithmes qui détectent les intentions et les transmettent ensuite à l’application afin qu’elle sache quoi faire. Ces intentions constituent une représentation succincte de la demande.

Par exemple, si un utilisateur dit « Siri, envoie 20 $ à John pour le dîner d’hier soir avec mon application bancaire. », l’intention serait du type *sendMoney*.

En envoyant chacune de ces requêtes sous la forme d’une eVar, vous pouvez exécuter des rapports de cheminement sur chacun des objectifs des applications de conversation. Assurez-vous que votre application peut également traiter les requêtes sans intention. Adobe conseille de transmettre la variable &quot;Aucun mode spécifié&quot; à la variable de données contextuelles d’intention, plutôt que de la supprimer.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

ou

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Paramètres/emplacements/entités

En plus de l’intention, les assistants numériques ont souvent un ensemble de paires clé/valeur qui fournissent des détails sur l’intention. On peut les appeler emplacements, entités ou paramètres. Par exemple, &quot;Siri, Envoyer à John 20 dollars pour le dîner hier soir à partir de mon application bancaire&quot; aurait les paramètres suivants :

* Qui = John
* Montant = 20
* Pourquoi = dîner

Votre application comporte généralement un nombre limité de ces valeurs. Pour suivre ces valeurs dans Analytics, envoyez-les dans des variables de données contextuelles, puis mappez chacun des paramètres à une eVar.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Etats d’erreur

Parfois, l’assistant numérique fournit à votre application des entrées qu’elle ne sait pas gérer. Par exemple, &quot;Siri, envoie à John 20 sacs de charbon pour dîner hier soir à partir de mon application bancaire&quot;

Dans ce cas, demandez à votre application de clarifier la situation. De plus, envoyez à Adobe des données indiquant que l’application a un état d’erreur, ainsi qu’une eVar indiquant le type d’erreur qui s’est produit. Veillez à inclure des erreurs lorsque les entrées ne sont pas correctes et des erreurs lorsque l’application a rencontré un problème.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Fonctionnalités du périphérique

Bien que la plupart des plateformes n’exposent pas le périphérique auquel l’utilisateur s’est entretenu, elles exposent les fonctionnalités du périphérique. Par exemple, Audio, Ecran, Vidéo, etc. Ces informations sont utiles car elles définissent les types de contenu qui peuvent être utilisés lors de l’interaction avec vos utilisateurs. Lors de la mesure des capacités des appareils, il est préférable de les concaténer (par ordre alphabétique).

Exemple : `":Audio:Camera:Screen:Video:"`

Les deux-points de début et de fin aident à créer des segments. Par exemple, affichez tous les accès dotés de `:Audio:` fonctionnalités.

* [Fonctionnalités](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) Amazon avec Amazon Alexa
* [Fonctionnalités](https://developers.google.com/actions/assistant/surface-capabilities) Google utilisant des actions sur Google

## Exemples

| Personne | Réponse du périphérique | Action/intention | Demande GET |
| --- | --- | --- | --- | ---|
| Installe Spoofify | Aucune réponse | Install | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Jouer Spoofify | &quot;Ok, jouer à Spoofify&quot; | Play | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Change de chanson | &quot;Ok, quelle chanson veux-tu ?&quot; | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Jouer &quot;Baby Shark&quot; | &quot;Ok, jouer &quot;Baby Shark&quot; par PinkFong&quot; | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Change de liste de lecture | &quot;Ok, quelle playlist veux-tu ?&quot; | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Lire ma liste de chansons préférées | &quot;Ok, jouer ta playlist de chansons préférées&quot; | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Arrête la musique | Pas de réponse, la musique s&#39;éteint | Off | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
