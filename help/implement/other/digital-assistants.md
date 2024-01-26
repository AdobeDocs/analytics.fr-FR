---
title: Mise en œuvre d’Analytics pour les assistants numériques
description: Mettez en œuvre Adobe Analytics sur des assistants numériques, tels qu’Amazon Alexa ou Google Home.
feature: Implementation Basics
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '1258'
ht-degree: 98%

---

# Mise en œuvre d’Analytics pour les assistants numériques

Avec les récentes avancées dans le cloud computing, le machine learning et le traitement du langage naturel, les assistants numériques font désormais partie de la vie quotidienne. Les consommateurs commencent à parler à leurs appareils et s’attendent à ce qu’ils comprennent et réagissent de manière humaine. À mesure que ces plates-formes s’ancrent dans le marché, les marques peuvent présenter leurs services aux consommateurs avec le même réalisme. Par exemple, les clients peuvent poser les questions suivantes :

* « Alexa, demande à ma voiture quand il faut changer son huile. »
* « Cortana, quel est le solde de mon compte courant ? »
* « Siri, envoie 20 $ à John pour le dîner d’hier soir avec mon application bancaire. »

Cette page fournit une vue d’ensemble des meilleures façons d’utiliser Adobe Analytics afin de mesurer et d’optimiser ces types d’expériences.

## Vue d’ensemble de l’architecture de l’expérience digitale

![Processus de lʼassistant numérique](assets/Digital-Assitants.png)

À l’heure actuelle, la plupart des assistants numériques suivent la même architecture de niveau supérieur :

1. **Appareil** : il y a un appareil (tel qu’Amazon Echo ou un téléphone) équipé d’un micro qui permet à l’utilisateur de poser une question.
1. **Assistant numérique** : cet appareil interagit avec le service sur lequel repose l’assistant numérique. C’est là que la parole est convertie en intentions que la machine peut comprendre et que les détails de la demande sont analysés. Une fois que l’intention de l’utilisateur est comprise, l’assistant numérique la transmet avec les détails de la demande à l’application qui gère cette demande.
1. **Application** : il peut s’agir d’une application sur le téléphone ou d’une application vocale. L’application a la responsabilité de répondre à la demande. Elle répond à l’assistant numérique qui répond ensuite à l’utilisateur.

## Où mettre en œuvre Analytics

L’application est l’un des meilleurs emplacements où Analytics peut être mis en œuvre. L’application reçoit l’intention et les détails de l’assistant numérique, puis détermine le mode de réponse.

Il peut s’avérer utile d’envoyer des données à Adobe Analytics à deux étapes d’une demande.

1. Lorsque la demande est envoyée à l’application
1. Après que la demande est renvoyée par l’application

Si vous souhaitez uniquement enregistrer ce qui s’est passé avec le client à des fins d’optimisation future, envoyez une demande à Adobe Analytics une fois la réponse renvoyée. Vous disposez de l’ensemble du contexte incluant ce qu’était la demande et la façon dont le système a répondu.

## Nouvelles installations

Pour certains assistants numériques, vous recevez une notification lorsque quelqu’un installe la compétence, en particulier lorsque l’authentification est impliquée. Adobe recommande d’envoyer un événement Install en définissant la variable de données contextuelles `a.InstallEvent=1`. Cette fonctionnalité n’est pas disponible sur tous les assistants numériques, mais elle est utile pour observer la rétention. L’exemple de code suivant envoie les valeurs Install event, Install Date et AppID aux variables de données contextuelles.

```text
GET
/b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://example.data.adobedc.net">
  example.data.adobedc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Plusieurs assistants ou applications

Il est probable que votre entreprise souhaite des applications pour plusieurs plateformes. La bonne pratique consiste à inclure un identifiant d’application dans chaque demande. Cette variable peut être définie dans la variable de données contextuelles `a.AppID`. Suivez le format `[AppName] [BundleVersion]`, par exemple, BigMac pour Alexa 1.2.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Identification de l’utilisateur/du visiteur

Adobe Analytics utilise [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) pour lier les interactions au fil du temps à la même personne. La plupart des assistants numériques renvoient un `userID` que vous pouvez utiliser pour conserver l’activité pour différents utilisateurs. Dans la plupart des cas, cette valeur correspond à ce que vous pouvez transmettre en tant qu’identifiant unique. Certaines plateformes renvoient un identifiant qui dépasse les 100 caractères autorisés. Dans ce cas, Adobe recommande de hacher l’identifiant unique sur une valeur de longueur fixe à l’aide d’un algorithme de hachage standard, tel que MD5 ou Sha1.

L’utilisation du service d’ID offre le meilleur rapport qualité-prix lorsque vous mappez des ECID sur différents appareils (par exemple, web vers l’assistant numérique). Si votre application est une application mobile, utilisez les SDK de la plateforme d’expérience en l’état et envoyez l’identifiant utilisateur à l’aide de la méthode `setCustomerID`. Cependant, si votre application est un service, utilisez l’identifiant utilisateur fourni par le service comme l’ECID, et définissez-le dans `setCustomerID`.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Sessions

Les assistants numériques étant conversationnels, ils font souvent appel au concept de session. Par exemple :

**Consommateur :** « OK Google, appelle-moi un taxi. »

**Google :** « Bien sûr, pour quelle heure ? ».

**Consommateur :** « 20 h 30 »

**Google :** « Très bien. Le taxi sera là à 20 h 30. »

Les sessions sont importantes pour garder le contexte et pour aider à collecter plus de détails afin de rendre l’assistant numérique plus naturel. Lorsque vous mettez Analytics en œuvre sur une conversation, vous devriez effectuer deux actions au démarrage d’une nouvelle session :

1. **Contacter Audience Manager** : obtenir les segments pertinents dont fait partie l’utilisateur de façon à personnaliser la réponse. (Par exemple, cette personne a actuellement droit à la remise multi-canal.)
2. **Envoyer un nouvel événement de lancement ou de session** : quand vous envoyez la première réponse à Analytics, incluez un événement de lancement. Vous pouvez généralement l’envoyer en définissant les données contextuelles de `a.LaunchEvent=1`.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Intentions

Chacun des assistants numériques possède des algorithmes qui détectent les intentions et les transmettent ensuite à l’application afin qu’elle sache quoi faire. Ces intentions constituent une représentation succincte de la demande.

Par exemple, si un utilisateur dit &quot;Siri, envoie 20 $ à John pour le dîner d’hier soir à partir de mon application bancaire&quot;, l’intention peut ressembler à *sendMoney*.

En envoyant chacune de ces demandes sous la forme d’une eVar, vous pourrez exécuter des rapports de cheminement sur chaque intention pour les applications conversationnelles. Assurez-vous que votre application peut également traiter les requêtes sans intention. Adobe conseille de transmettre la variable « Aucun mode spécifié » à la variable de données contextuelles dʼintention, plutôt que de la supprimer.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.adobedc.net
Cache-Control: no-cache
```

ou

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Paramètres/emplacements/entités

Outre l’intention, les assistants numériques disposeront souvent d’un ensemble de paires valeur/clé détaillant l’intention. Il peut s’agir d’emplacements, d’entités ou de paramètres. Par exemple, « Siri, envoie 20 $ à John pour le dîner d’hier soir avec mon application bancaire » présenterait les paramètres suivants :

* Qui = John
* Montant = 20
* Pourquoi = dîner

Il existe généralement un nombre fini de ces valeurs dans votre application. Pour effectuer leur suivi dans Analytics, envoyez-les dans les variables de données contextuelles et mappez ensuite chacun des paramètres à une eVar.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## États d’erreur

Parfois, l’assistant numérique fournit à l’application des données qu’elle ne sait pas gérer. Par exemple, « Siri, envoie 20 sacs de charbon à John pour le dîner d’hier soir avec mon application bancaire ».

Dans ce cas, demandez à votre application de clarifier la situation. De plus, envoyez à Adobe des données indiquant que l’application a un état d’erreur, ainsi qu’une eVar indiquant le type d’erreur qui s’est produit. Veillez à inclure les erreurs où les données en entrée ne sont pas correctes ainsi que celles où l’application a rencontré un problème.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Fonctionnalités des appareils

Bien que la plupart des plateformes n’exposent pas l’appareil auquel l’utilisateur a parlé, elles exposent les fonctionnalités de l’appareil. Par exemple, Audio, Écran, Vidéo, etc. Ces informations sont utiles, car elles définissent le type de contenu qui peut être utilisé pour interagir avec vos utilisateurs. Lorsque vous mesurez les fonctionnalités des appareils, il est préférable de les concaténer (dans l’ordre alphabétique).

Exemple : `":Audio:Camera:Screen:Video:"`

Les deux-points de début et de fin aident à créer des segments. Par exemple, affichez tous les accès dotés de fonctionnalités `:Audio:`.

* [Fonctionnalités Amazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) avec Amazon Alexa
* [Fonctionnalités Google](https://developers.google.com/actions/assistant/surface-capabilities) utilisant des actions sur Google

## Exemples

| Personne | Réponse de l’appareil | Action/intention | Demande GET |
|---|---|---|---|
| Installe Spoofify | Pas de réponse | Install | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Jouer Spoofify | « OK, je joue Spoofify » | Play | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Change de chanson | « OK, quelle chanson voulez-vous ? » | ChangeSong | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Jouer « Baby Shark » | « OK, je joue &quot;Baby Shark&quot; de PinkFong » | ChangeSong | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Change de liste de lecture | « OK, quelle liste de lecture voulez-vous ? » | ChangePlaylist | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Lire ma liste de lecture de chansons préférées | « OK, je joue votre liste de lecture de chansons préférées » | ChangePlaylist | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Arrête la musique | Pas de réponse, la musique s’arrête | Off | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
