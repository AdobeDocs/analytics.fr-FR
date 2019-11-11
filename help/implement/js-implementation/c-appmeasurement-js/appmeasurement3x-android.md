---
description: AppMeasurement 3.x pour Android
seo-description: Documentation héritée pour AppMeasurement 3.x pour Android
seo-title: AppMeasurement 3.x pour Android
solution: Analytics
subtopic: Signets
title: AppMeasurement 3.x pour Android
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 595efd52fe3b8edae32d8b3c2216ea066ec642be

---


# AppMeasurement 3.x pour Android

*Remarque : Ce document contient des informations héritées pour les versions précédentes d’AppMeasurement, en particulier pour les versions 3.x pour Android.
Pour plus d’informations sur la mise en oeuvre actuelle d’AppMeasurement, voir[A propos d’AppMeasurement pour JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).*

*Dernière mise à jour le 15/3/2018 AppMeasurement 3.x pour Android*

Adobe AppMeasurement pour Android vous permet de mesurer les applications Android natives dans Adobe Experience Cloud.

Ce guide est divisé en deux sections; une section pour l’analyste ayant une expérience d’Adobe Analytics et une autre pour le développeur Android ayant une expérience du développement d’applications mobiles.

**Versions** prises en charge : Android 2.0 ou version ultérieure.

**Téléchargez les instructions et les liens de** téléchargement de bibliothèque pour toutes les plateformes mobiles AppMeasurement à la page Mesures et optimisation des applications mobiles sur Developer Connection. Pour télécharger les bibliothèques, vous devez disposer d’un compte Developer Connection gratuit ou d’une connexion à SiteCatalyst. Les liens de téléchargement ne s’affichent que lorsque vous êtes connecté.

## Analystes : démarrage rapide

Cette section vous guide tout au long des étapes nécessaires pour mettre en œuvre la bibliothèque Android et ajouter le code requis pour une mise en œuvre standard. Elle comprend également des étapes vous montrant comment envoyer des événements personnalisés et d’autres données.

En tant qu’analyste, vous devez activer les rapports d’applications mobiles pour votre suite de rapports. Si vous devez capturer des mesures supplémentaires, vous devez fournir au développeur une description des variables de données contextuelles devant être envoyées par l’application. Par exemple, pour collecter un nom d'utilisateur après une connexion, vous pouvez demander au développeur de définir le nom d'utilisateur dans une variable de données contextuelles appelée `myco.username`.

### Activation des rapports d’applications mobiles dans SiteCatalyst

SiteCatalyst fournit une interface pour activer le suivi du cycle de vie des applications mobiles. Cette mise en correspondance permet à SiteCatalyst de générer automatiquement les rapports d’applications mobiles.

1. Ouvrez Console d’administration &gt; Report Suites &gt; Modifier les paramètres &gt; Gestion mobile &gt; Rapports d’applications mobiles.
1. Cliquez sur Activer le suivi du cycle de vie des applications mobiles.

Les mesures de cycle de vie sont à présent capturées. Les rapports d’applications mobiles apparaissent dans le menu Rapports de SiteCatalyst.

### Capture de mesures supplémentaires à l’aide des règles de traitement

Si votre mise en œuvre envoie des dimensions et des événements supplémentaires à l’aide de données contextuelles, vous devez configurer des règles de traitement pour capturer ces données.

Avant de créer des règles de traitement, une personne de votre organisation doit être certifiée. Pour obtenir des informations supplémentaires, reportez-vous à l’Aide sur les règles de traitement.

Une fois les règles de traitement activées, l’exemple Copie d’une variable de données contextuelles montre le processus requis pour mettre en correspondance des données contextuelles.

### (Facultatif) Activation du suivi hors ligne

Si vous planifiez de stocker les accès lorsque l’appareil est hors ligne, la suite de rapports doit être horodatée.

Une fois le suivi hors ligne activé, tous les accès doivent être horodatés (sinon, ils ne sont pas collectés). Si vous collectez actuellement des données AppMeasurement dans une suite de rapports qui collecte également des données de JavaScript, il est possible que vous deviez configurer une suite de rapports distincte pour les données mobiles afin d’éviter toute perte de données ou que vous deviez inclure un horodatage personnalisé pour les accès JavaScript à l’aide de la variable s.timestamp.

Si vous ne savez pas si votre suite de rapports est horodatée, contactez le service à la clientèle.

## Développeurs : démarrage rapide

Cette section vous guide tout au long des étapes nécessaires pour sélectionner et configurer les événements, eVars et props que vous utiliserez pour la collecte de données Android. Elle comprend également les étapes nécessaires à la création de règles de traitement pour copier les données contextuelles envoyées par les bibliothèques Android à ces variables.

Les étapes pour mettre en oeuvre la bibliothèque Android et commencer à envoyer des données de mesure sont les suivantes :

* Obtention de la bibliothèque
* Ajout de la bibliothèque à votre projet
* Ajout des autorisations des applications
* Remarque concernant TrackingHelper
* Mise en œuvre

### Obtention de la bibliothèque

Consultez la page Mesures et optimisation des applications mobiles sur Developer Connection pour télécharger la bibliothèque Android. Après avoir décompressé le fichier téléchargé, vous disposerez des composants logiciels suivants :

* admsAppLibrary.jar : bibliothèque conçue pour l’utilisation avec les appareils et simulateurs Android. Requiert Android 2.0 ou une version ultérieure.
* Examples\TrackingHelper.java : classe facultative, conçue pour séparer le code de suivi de la logique applicative.

### Ajout de la bibliothèque à votre projet

1. Dans Eclipse IDE, cliquez avec le bouton droit sur le nom du projet.
1. Sélectionnez Créer chemin &gt; Ajouter archives externes.
1. Select `admsAppLibrary.jar`.
1. Cliquez sur Ouvrir.
1. Cliquez de nouveau avec le bouton droit sur le projet, puis sélectionnez Build Path (Créer chemin) &gt; Configure Build Path (Configurer création chemin).
1. Cliquez sur l’onglet Order and Export (Classer et exporter).
1. Vérifiez que `admsAppLibrary.jar` est sélectionné.

Votre application peut importer les classes/interfaces de la bibliothèque admsAppLibrary.jar à l’aide de import com.adobe.ADMS.*;

### Ajout des autorisations d’application

La bibliothèque AppMeasurement nécessite les autorisations suivantes pour envoyer des données et enregistrer les appels de suivi hors ligne :

* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### Remarque concernant TrackingHelper

Le kit SDK comprend une autre classe facultative, appelée TrackingHelper. La classe TrackingHelper permet de séparer le code de mesure de la logique applicative.

Prenez l’exemple suivant : dans votre application, vous voulez envoyer un événement qui effectue le suivi de chaque connexion. Vous pouvez ajouter le code suivant juste après le code de connexion pour envoyer cet événement (ne vous souciez pas à ce stade des détails du code ; nous y reviendrons ultérieurement) :

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

Cette option est correcte, mais ne voulez-vous pas placer ce code à un autre endroit pour qu’il ne vous dérange pas lors du développement de l’application ? La classe TrackingHelper fait office d’autre endroit. Vous pouvez y placer le code dans une méthode appelée trackLogonEvent :

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

Dans le code de votre application, vous pouvez maintenant effectuer le suivi d’un événement de connexion à l’aide d’un simple appel à trackLogonEvent :

TrackingHelper.trackLogonEvent("nom d'utilisateur");

L’appel de mesure du code de votre application ne tient que sur une seule ligne. De plus, si la logique de mesure sous-jacente doit être modifiée, il vous suffit de mettre à jour uniquement la classe TrackingHelper. Si un autre développeur effectue des ajouts à votre code, il peut utiliser les méthodes simplifiées que vous avez définies sans suivre de cours intensif sur la bibliothèque AppMeasurement.

Nous pensons que vous préférerez utiliser la classe TrackingHelper pour les nouvelles mises en œuvre, même si la configuration prend une minute ou deux de plus. Le reste de ce guide vous décrit les étapes pour configurer la classe TrackingHelper et commencer à envoyer des données de mesure.

Copiez TrackingHelper.java dans un répertoire contenant les fichiers de classe pour votre application et remplacez le nom du package en haut de ce fichier pour qu’il corresponde à la structure du package (com.company.application). Si vous souhaitez effectuer une mise en œuvre sans TrackingHelper, vous trouverez plusieurs exemples dans TrackingHelper que vous pouvez copier dans votre application.

### Mise en œuvre

1. Ouvrez TrackingHelper.java et mettez à jour TRACKING_RSID et TRACKING_SERVER avec l’identifiant de la suite de rapports et le serveur de suivi. Par exemple :

   ```
   private static final String TRACKING_RSID = "rsid";
   private static final String TRACKING_SERVER = "server";
   ```

   Ces valeurs sont obligatoires et doivent être correctes. Sinon, la mesure ne fonctionne pas. Si vous n’êtes pas sûr de ces valeurs, contactez le spécialiste SiteCatalyst.

2. Recherchez la méthode configureAppMeasurement. C’est ici que vous activez SSL et le suivi hors ligne, et que vous apportez des modifications globales à votre configuration. Pour l’instant, supprimez le commentaire de la ligne pour activer debugLogging jusqu’à ce que tout fonctionne comme vous le souhaitez.

3. Ajoutez un appel à configureAppMeasurement à partir de l’activité racine dans votre application.

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

Il s’agit du code dont vous avez besoin pour commencer le suivi des mesures personnalisées. Avec quelques lignes de code supplémentaires, vous pouvez toutefois activer le suivi du cycle de vie pour envoyer automatiquement des mesures de cycle de vie, notamment les lancements, mises à niveau, blocages et utilisateurs quotidiens et mensuels.

La bibliothèque AppMeasurement fait la plus grande partie du travail ; vous devez juste ajouter deux appels de méthode à chaque classe d’activité de votre application.

### (Recommandé) Suivi des événements de cycle de vie

Lorsque le suivi du cycle de vie est activé, chaque fois que votre application est lancée, un seul accès est envoyé pour effectuer le suivi des installations, des mises à niveau, des jours d’activité et des autres mesures de cycle de vie.

Pour commencer à suivre les événements de cycle de vie, dans votre application, ajoutez des appels aux méthodes onResume() et onPause() dans chaque activité à l’intérieur de votre application, comme illustré dans l’exemple ci-dessous. Il est également recommandé de transmettre l’activité ou le service comme objet de contexte au lieu du contexte d’application globale.

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

Vous avez terminé ! Vous avez mis en œuvre un suivi de cycle de vie de base dans votre application Android. Lorsque l’analyste Web configure SiteCatalyst pour traiter les mesures AppMeasurement que vous signalez, la suite de rapports SiteCatalyst contient les mesures de cycle de vie par défaut.

Ce que vous pouvez faire à ce stade :

* (Facultatif) Suivi des événements personnalisés. Ajoutez des méthodes personnalisées à TrackingHelper pour effectuer le suivi de tous les événements à mesurer dans votre application. Vous pouvez ajouter des méthodes pour effectuer le suivi des connexions, des achats, etc.
* (Facultatif) Suivi des états d’application. Un état d’application est semblable à une page vue. Cette section montre comment ajouter une méthode personnalisée à TrackingHelper pour effectuer le suivi d’un état d’application.
* Mesures vidéo : démarrage rapide. Ajoutez le code pour effectuer le suivi des mesures vidéo, notamment affichages de vidéos, durée totale de lecture et vidéos les plus populaires.

### (Facultatif) Suivi des événements personnalisés

Les événements personnalisés sont des mesures de succès propres à votre application. Vous pouvez envoyer un événement personnalisé lorsqu’un utilisateur se connecte, effectue un achat ou clique sur un lien vers votre page Facebook. La classe TrackingHelper contient un exemple qui montre comment effectuer le suivi d’un événement personnalisé. Vous pouvez utiliser cette méthode comme modèle pour ajouter d’autres méthodes de suivi d’événements.

Dans TrackingHelper.java, définissez une méthode de suivi d’événement personnalisé :

```
public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

Dans tout votre code, vous pouvez appeler cette méthode pour effectuer le suivi d’un événement personnalisé :

`TrackingHelper.trackCustomEvents();`

Utilisez ce processus pour ajouter autant de méthodes de suivi d’événements que nécessaire. La section Remarque concernant TrackingHelper contient un exemple de méthode pour effectuer le suivi d’un événement de connexion.

### (Facultatif) Suivi des états d’application

La classe TrackingHelper contient également un exemple qui montre comment effectuer le suivi d’un état d’application. Le suivi d’un état personnalisé ressemble au suivi d’un événement. La seule différence réside dans le fait que vous utilisez la méthode trackAppState à la place de trackEvents.

```
measure.trackAppState("name", contextData);
```

D’un point de vue des rapports, trackAppState incrémente les pages vues, contrairement à trackEvents.

## Mesures vidéo : démarrage rapide

Les mesures vidéo sont décrites dans le guide intitulé Mesure des vidéos dans SiteCatalyst. Le processus général de mesure vidéo se ressemble dans toutes les plates-formes AppMeasurement. Cette section de démarrage rapide donne une vue d’ensemble des tâches du développeur et fournit des exemples de code.

La même bibliothèque admsAppLibrary.jar est utilisée pour le suivi des vidéos et de l’application. Pour maintenir la cohérence entre les plates-formes, la documentation fait référence à ces méthodes en tant que module média.

Vous devez configurer une instance de mesure avant d’utiliser le module média.

Pour mettre en œuvre le suivi vidéo sur Android, effectuez les tâches suivantes :

* Mise en correspondance des événements du lecteur avec les variables SiteCatalyst
* Configuration des jalons, des segments et de la fréquence des appels
* Suivi des événements du lecteur

### Mise en correspondance des événements du lecteur avec les variables SiteCatalyst

Pour configurer les mesures vidéo, vous devez mettre en correspondance les événements et eVar SiteCatalyst sélectionnés pour le suivi vidéo avec les variables de données contextuelles. Pour plus d’informations, voir la section Configuration des vidéos SiteCatalyst.

L’analyste Web doit vous fournir une feuille de mise en œuvre vidéo contenant la liste des variables SiteCatalyst qu’il a configurés pour recevoir les données vidéo :

* Nom de la vidéo (eVar) : eVar2
* Nom de la vidéo (prop) : prop2
* Segments (eVar) : eVar3
* Type de contenu (eVar) : eVar1
* Durée de la vidéo (événement) : event3
* Affichages de vidéos (événement) : event1
* La vidéo se termine (événement) : event7
* Affichages de segments de vidéo (événement) : event2

1. Ajoutez le code suivant après le code que vous avez ajouté dans la section Mise en œuvre, en remplaçant la variable SiteCatalyst que vous avez sélectionnée par l’exemple du code :

   ```
   ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
   Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
   contextDataMapping.put("a.media.name", "eVar2,prop2");
   contextDataMapping.put("a.media.segment", "eVar3");
   contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
   namespace
   contextDataMapping.put("a.media.timePlayed", "event3");
   contextDataMapping.put("a.media.view", "event1");
   contextDataMapping.put("a.media.segmentView", "event2");
   contextDataMapping.put("a.media.complete", "event7");
   mediaMeasure.ContextDataMapping = contextDataMapping;
   ```

2. Configuration des jalons, des segments et de la fréquence des appels.

3. Suivi des événements du lecteur.


### Configuration des jalons, des segments et de la fréquence des appels

Les jalons vous permettent d’envoyer un événement lorsqu’un point spécifique est atteint dans la vidéo. Les segments servent à diviser la vidéo en sections pour un suivi plus précis. La fréquence des appels permet d’envoyer des appels de mesure avec le temps passé à des intervalles spécifiques. Pour plus d’informations, voir la section Mesures vidéo.

### Mise en correspondance des jalons

Vous pouvez définir des jalons basés sur un pourcentage de la durée totale ou sur des secondes écoulées. Cet exemple définit des jalons en tant que pourcentage de la durée totale. Pour une vidéo de 2 minutes, le code ci-dessous envoie des événements de jalon à 30 secondes, 60 secondes et 90 secondes.

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### Mise en correspondance du décalage de jalons

Cet exemple définit les jalons par secondes écoulées depuis le début de la vidéo. Pour une vidéo de 2 minutes, le code ci-dessous envoie des événements de jalon à 20 secondes, 40 secondes et 60 secondes, indépendamment de la durée totale de la vidéo.

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### Exemples

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### Suivi des événements du lecteur

Pour mesurer des vidéos, vous devez ajouter du code qui indique au module média à quel moment les événements se produisent dans le lecteur (à l’aide des méthodes open, play, stop et close). Lorsqu’un utilisateur commence la lecture d’une vidéo, vous devez appeler la méthode play pour que le module média commence à comptabiliser les secondes affichées.

Si l’utilisateur interrompt la vidéo, vous devez appeler stop pour interrompre la comptabilisation. En règle générale, cela est effectué à l’aide de gestionnaires d’événements exposés par le lecteur.

Par exemple :

Chargement : appelez open et play

Pause : appelez stop. Par exemple, si un utilisateur met en pause une vidéo après 15 secondes, appelez stop("Video1",15)

Mémoire tampon : appelez stop pendant la mise en mémoire de la vidéo. Appelez play lorsque la lecture reprend.

Reprise : appelez play. Par exemple, quand un utilisateur reprend la lecture d’une vidéo après en avoir affiché initialement 15 secondes, appelez s.play("Video1",15).

Lecture à vitesse variable (réglette) : lorsque l’utilisateur fait glisser la réglette de la vidéo, appelez stop. Lorsque l’utilisateur relâche la réglette de la vidéo, appelez play.

Fin : appelez stop, puis close. Par exemple, à la fin d’une vidéo de 100 secondes, appelez stop("Video1",100), puis close("Video1").

Pour ce faire, vous pouvez définir quatre fonctions personnalisées que vous pouvez appeler à partir des gestionnaires d’événements du lecteur multimédia. Les différents paramètres transmis à open, play, stop et close proviennent du lecteur. Le pseudocode suivant montre comment c’est possible :

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## Mesures de cycle de vie

Cette feuille de calcul répertorie les mesures et les dimensions qui sont automatiquement mesurées lorsque le suivi du cycle de vie automatique est activé.

### Mesures de cycle de vie et de dimensions

Une fois configurées, les mesures de cycle de vie sont envoyées dans les paramètres de données contextuelles d’Analytics, les paramètres de Target avec chaque appel mbox, et en tant que signal pour la Gestion de l’audience. Analytics et Target utilisent le même format, tandis que la Gestion de l’audience utilise un préfixe différent pour chaque mesure.

Pour Analytics, les données contextuelles envoyées avec chaque appel de suivi de cycle de vie sont automatiquement capturées et consignées à l’aide de la mesure ou de la dimension répertoriée dans la première colonne, avec les exceptions spécifiées dans la colonne réservée à la description.

| Mesure | Contexte Analytics | Analytics Context Audience Manager Signal Description | Paramètre de données/cible |
|--- |--- |--- |--- |
| Premiers lancements | a.InstallEvent | c_a_InstallEvent | Déclenché à la première exécution après installation (ou nouvelle installation). |
| Mises à niveau | a.UpgradeEvent | c_a_UpgradeEvent | Déclenché à la première exécution après les mises à niveau (à chaque modification du numéro de version). |
| Utilisateurs actifs par jour | a.DailyEngUserEvent | c_a_DailyEngUserEvent | Déclenché lorsque l’application est utilisée un jour spécifique. |
| Utilisateurs actifs mensuels | Utilisateurs actifs par mois | a.MonthlyEngUserEvent | Déclenché lorsque l'application est utilisée un mois spécifique. |
| Lancements | a.LaunchEvent | c_a_LaunchEvent | Déclenché à chaque exécution, y compris les blocages et les installations. | Lancements Également déclenchés sur un CV en arrière-plan lorsque le délai d’expiration de la session de cycle de vie est dépassé. |
| Blocages | a.CrashEvent | c_a_CrashEvent | Déclenché lorsque l’application ne se ferme pas normalement. L’événement est envoyé au démarrage de l’application après son blocage (l’application est considérée comme bloquée si la sortie n’est pas appelée). |
| Durée de session précédente | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Total cumulé Durée de session précédente en secondes. |

*Remarque : Les utilisateurs actifs **quotidiens**et les utilisateurs **actifs**mensuels ne sont pas automatiquement stockés dans une mesure Analytics. Pour capturer ces mesures, vous devez créer une règle de traitement définissant un événement personnalisé.*

### Dimensions

| Mesure | Données contextuelles Analytics/Paramètre Target | Signal Analytics Context Audience Manager | Description |
|--- |--- |--- |--- |
| Date d’installation | a.InstallDate | c_a_InstallDate | Date du premier lancement après installation. MM/JJ/AAAA |
| Mises à niveau | a.UpgradeEvent | c_a_UpgradeEvent | Déclenché à la première exécution après les mises à niveau (à chaque modification du numéro de version). |
| ID de l’application | a.AppID | c_a_AppID | Stocke le nom et la version de l’application au format suivant : `[AppName] [BundleVersion]` Par exemple : monappli 1.1. |
| Nombre de jours depuis la première utilisation | a.DaysSinceFirstUse | c_a_DaysSinceFirstUse | Nombre de jours depuis la première exécution. |
| Utilisateurs actifs par mois | Utilisateurs actifs par mois | a.MonthlyEngUserEvent | Déclenché lorsque l'application est utilisée un mois spécifique. |
| Lancements | a.LaunchEvent | c_a_LaunchEvent | Déclenché à chaque exécution, y compris les blocages et les installations. | Lancements Également déclenchés sur un CV en arrière-plan lorsque le délai d’expiration de la session de cycle de vie est dépassé. |
| Blocages | a.CrashEvent | c_a_CrashEvent | Déclenché lorsque l’application ne se ferme pas normalement. L’événement est envoyé au démarrage de l’application après son blocage (l’application est considérée comme bloquée si la sortie n’est pas appelée). |
| Durée de session précédente | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Total cumulé Durée de session précédente en secondes. |
| Nombre de jours depuis la dernière utilisation | a.DaysSinceLastUse | c_a_DaysSinceLastUse | Nombre de jours depuis la dernière exécution. |
| Jour de la semaine | a.DayOfWeek | c_a_DayOfWeek | Numéro du jour de la semaine où l’application a été lancée. |
| Heure du jour | a.HourOfDay | c_a_HourOfDay | Mesure l’heure à laquelle l’application a été lancée. Format numérique de 24 heures. Utilisée pour le découpage temporel afin de déterminer les heures hautes d’utilisation. |
| Version du système d’exploitation | a.OSVersion | c_a_OSVersion | Version du système d’exploitation. |
| Nombre de jours depuis la dernière mise à niveau | a.DaysSinceLastUpgrade | c_a_DaysSinceLastUpgrade | Nombre de jours depuis que le numéro de version de l’application a changé. |
| Lancements depuis la dernière mise à niveau | a.LaunchesSinceUpgrade | c_a_LaunchesSinceUpgrade | Nombre de lancements depuis que le numéro de version de l’application a changé. |
| Nom de l'appareil | a.DeviceName | c_a_DeviceName | Stocke le nom de l’appareil. | iOS : chaîne de 2 chiffres séparée par une virgule qui identifie l’appareil iOS. Le premier chiffre représente généralement la génération de l’appareil, le second les différents membres de la famille d’appareils. Pour obtenir la liste des noms de périphérique courants, reportez-vous à Versions des appareils iOS. |
| Nom de l’opérateur | a.CarrierName | c_a_CarrierName | Stocke le nom du fournisseur de services mobiles transmis par l’appareil. |
| Résolution | a.Resolution | c_a_Resolution | Largeur x Hauteur en pixels |

*Remarque :**Jours depuis la dernière mise à niveau**, les **lancements depuis la dernière mise à niveau**et le nom **de l’**opérateur ne sont pas automatiquement stockés dans une variable Analytics. You must create a processing rule to copy these values to an Analytics variable for reporting.*

## Données contextuelles

Les données contextuelles constituent la méthode préférée pour envoyer des données d’application aux serveurs de collecte.

Au lieu d’affecter de façon explicite des valeurs aux props et eVars, vous pouvez utiliser des variables de données contextuelles pour envoyer des paires nom-valeur qui sont mises en correspondance dans SiteCatalyst. En fonction de ces paires clé-valeur, vous pouvez définir des événements, copier des valeurs dans des eVars et des props et exécuter des instructions conditionnelles supplémentaires. Cela vous évite de mettre à jour le code pour prendre en charge différentes configurations de suite de rapports.

Il existe deux façons d’envoyer des données contextuelles avec les méthodes de suivi. Les données contextuelles définies directement sur l’objet PersistentContextData sont envoyées avec chaque appel. Vous pouvez également transmettre les données contextuelles en tant que paramètre à un appel de suivi unique qui est envoyé avec cet appel uniquement.

### Données contextuelles persistantes

Les valeurs placées dans les données contextuelles persistantes sont envoyées avec chaque appel du serveur. Dans l’exemple suivant, "key" (clé) et "value" (valeur) sont envoyés avec tous les appels trackAppState :

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### Données contextuelles dans le cadre d’un appel unique

Pour envoyer des données contextuelles pour un appel unique, envoyez contextData en tant que paramètre à l’appel de suivi (trackAppState, trackEvents, etc.).

Dans l’exemple suivant, "key" et "value" sont envoyés avec les trois appels trackAppState. Toutefois, "key2" et "value2" ne sont envoyés qu’avec le second appel trackAppState :

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## Variables de configuration

Les variables ci-après sont définies lorsque l’application est lancée.:

*Remarque : Toutes les variables de configuration sont facultatives, à l’exception de ReportSuiteID et trackingServer.*

**Instance partagée**

Avant d’effectuer des appels de mesure, vous devez récupérer une instance de la bibliothèque pour chaque méthode appelée dans la bibliothèque de mesures :

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Remarque : Les variables de configuration sont privées. Utilisez les méthodes get et set pour modifier ces valeurs.*

### Variables de configuration

**reportSuiteIDs**: (Obligatoire) La ou les suites de rapports (balisage multi-suite) dont vous souhaitez effectuer le suivi. Pour effectuer le suivi de plusieurs suites de rapports, transmettez la liste des noms séparés par des virgules à chaque suite.

Vous ne pouvez pas remplacer cette variable pour un appel unique. Vous devez modifier la valeur persistante.

Syntaxe :

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

Exemples:

`measure.setReportSuiteIDs("rsid");`

Marquage multisuite:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**: (Obligatoire) Identifie le serveur de collecte.

Cette variable doit être renseignée avec le domaine de votre serveur de suivi, sans préfixe de protocole « http:// » ou « https:// ». Le préfixe de protocole est géré automatiquement par la bibliothèque en fonction de la variable ssl.

Si ssl est défini sur true, une connexion sécurisée est établie avec le serveur. Si ssl est défini sur false, une connexion non sécurisée est établie avec le serveur.

Vous ne pouvez pas remplacer cette variable pour un appel unique. Vous devez modifier la valeur persistante.

Syntaxe :

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

Exemples:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**: Par défaut : uuidIdentifiant unique de chaque visiteur. Si vous ne définissez pas de visitorID personnalisé, un visitorID unique est généré.

Il est recommandé d’utiliser la valeur par défaut, sauf si vous avez une raison spécifique de définir visitorID. La définition d’une variable visitorID personnalisée peut entraîner une duplication des visites lors de l’utilisation du suivi du cycle de vie. Pour éviter ce type de problème, définissez cette variable avant de configurer AppMeasurement.

**characterSet**: La valeur par défaut est UTF-8

Syntaxe :

```
String getCharSet()
void setCharSet(String charSet)
```

Exemples:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**:La valeur par défaut est none (la valeur définie pour la suite de rapports est utilisée)

Code de devise utilisé pour les achats ou les événements de devise qui sont suivis dans l’application Android.

Syntaxe :

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

Exemples:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**: La valeur par défaut est de 5 minutes

Spécifie la durée, en secondes, qui doit s’écouler entre les lancements de l’application pour qu’un lancement soit considéré comme une nouvelle session. Ce délai d’attente s’applique également lorsque l’application est placée en arrière-plan et réactivée. La durée passée en arrière-plan n’est pas prise en compte dans la durée de la session.

Syntaxe :

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

Exemples:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**: La valeur par défaut est false

Active (true) ou désactive (false) l’envoi de données de mesure via SSL (HTTPS). Vous ne pouvez pas remplacer cette variable pour un appel unique. Vous devez modifier la valeur persistante.

Syntaxe :

`void setSSL(boolean ssl)`

Exemples:

`measure.setSSL(true);`

**debugLogging** Default est false

Active (true) ou désactive (false) l’affichage des informations de débogage et de la version de la bibliothèque dans la console de sortie. Par défaut, cette variable a la valeur false. Vous ne pouvez pas remplacer cette variable pour un appel unique. Vous devez modifier la valeur persistante.

Syntaxe :

`void setDebugLogging(boolean debugLogging)`

Exemples:

`measure.setDebugLogging(true);`

## Variables de suivi

**Instance partagée**

Avant d’effectuer des appels de mesure, vous devez récupérer une instance de la bibliothèque pour chaque méthode appelée dans la bibliothèque de mesures :

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Remarque : Les variables de configuration sont privées. Utilisez les méthodes get et set pour modifier ces valeurs.*

### Variables de suivi persistantes

**Evar**: Définit l'eVar spécifiée sur la valeur fournie. La variable eVar est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant Clear Vars.

Syntaxe :

`void setEvar(int evarNum, String evarValue)`

Exemple : `measure.setEvar(1, "value");`

**Prop**: Définit la prop spécifiée sur la valeur fournie. La variable prop est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant clearVars.

Syntaxe :

`void setProp(int propNum, String propValue)`

Exemple :

`measure.setProp(1, "value");`

**Hier**: Définit la variable d’héritier spécifiée sur la valeur fournie. La variable hier est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant clearVars.

Syntaxe :

`void setHier(int hierNum, String hierValue)`

Exemple :

`measure.setHier(1, "value");`


**ListVar**: Définit la variable listVar spécifiée sur la valeur fournie. La variable listVar est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant clearVars.

Syntaxe :

`void setListVar(int listNum, String listValue)`

Exemple :

`measure.setListVar(1, "value");`

**purchaseID**: La variable purchaseID permet d’éviter qu’une commande ne soit comptée plusieurs fois par SiteCatalyst.

Lorsqu’un événement d’achat est utilisé sur votre site, vous devez affecter un identifiant unique à cet achat à l’aide de la variable purchaseID.

`measure.setPurchaseID("unique_id");`

**transactionID**: Les sources de données d’intégration utilisent un ID de transaction pour lier les données hors ligne à une transaction en ligne (une piste ou un achat généré en ligne, par exemple).

Chaque variable transactionID unique envoyée à Adobe est enregistrée en vue d’un téléchargement des sources de données des informations hors ligne concernant cette transaction.

`measure.setTransactionID("unique_id");`

**appState**: (nom de page) La valeur fournie pour l’état de l’application est stockée dans la variable du nom de page.

`measure.setAppState("state");`

**channel**: measure.setChannel("mobile");

**appSection**: La valeur fournie pour la section Application est stockée dans la variable server.

Syntaxe :

`void setAppSection(String Section)`

Exemple : `measure.setAppSection("news");`

**campaign**

Syntaxe :

`void setCampaign(String Campaign)`

Exemple :

`measure.setCampaign("112233");`

**products**

Syntaxe :

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

Exemple :

`measure.setProducts("Running;Shoe");`

**events**

Syntaxe :

`void setEvents(String Event) //comma-delimited list`

Exemple :

`measure.setEvents("event1, event2");`

**geoState**

Syntaxe :

`void setGeoState(String GeoState)`

Exemple :

`measure.setGeoState("UT");`

**geoZip**

Syntaxe :

`void setGeoZip(String GeoZip)`

Exemple :

`measure.setGeoZip("12345");`

**Données** contextuelles persistantes : Les valeurs placées dans les données contextuelles persistantes sont envoyées avec chaque appel au serveur. Pour envoyer des données contextuelles pour un appel unique, envoyez une table de hachage de contextData en tant que paramètre à l’appel de suivi (trackAppState, trackEvents, etc.).

Exemple :

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Voir Données contextuelles.

**linkTrackVars**: Liste délimitée par des virgules de noms de variables qui limite l’ensemble actuel de variables pour le suivi des liens. Si linkTrackVars n’est pas défini, AppMeasurement pour Android envoie toutes les variables définies avec un appel trackLink.

Syntaxe :

`void setLinkTrackVars(String Vars) //comma-delimited list`

Exemple :

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**: Liste d’événements délimités par des virgules qui limite l’ensemble actuel d’événements pour le suivi des liens. Si linkTrackEvents n’est pas défini, AppMeasurement pour Android envoie tous les événements avec un appel trackLink.

Syntaxe :

`void setLinkTrackEvents(String Events) //comma-delimited list`

Exemple :

`measure.setLinkTrackEvents("event1, event2");`

## Méthodes

Cette section contient la liste des méthodes fournies par la bibliothèque Android.

**Instance partagée**

Avant d’effectuer des appels de mesure, vous devez récupérer une instance de la bibliothèque pour chaque méthode appelée dans la bibliothèque de mesures :

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### Configuration initiale

Cette méthode configure les variables requises et doit être appelée avant les autres méthodes.

**configureMeasurement**: Cette méthode permet de configurer les deux paramètres nécessaires au démarrage de la mesure de l’application. Vous devez définir les valeurs reportSuiteIDs et trackingServer sur l’objet de mesure à l’aide de cette méthode avant d’envoyer un appel de serveur.

Syntaxe :

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

Exemples:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### Suivi des événements et états

Il s’agit des méthodes principales pour effectuer le suivi des états de l’application et des événements personnalisés.

**trackAppState**: Il s’agit de la méthode recommandée pour effectuer le suivi des états d’application dans votre application. La valeur fournie dans appState apparaît comme variable de nom de page de l’appel du serveur. La chaîne appState doit être fournie pour chaque appel, car elle n’est pas transférée vers l’appel suivant.

Les données contextuelles envoyées avec cet appel sont ajoutées aux valeurs de persistentContextData et envoyées avec l’appel. Seules les valeurs définies dans persistentContextData restent pour l’appel suivant.

Syntaxe :

`void trackAppState(string AppStateName)`

Exemples:

`measure.trackAppState("state");`

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**: Il s’agit de la méthode recommandée pour effectuer le suivi des événements dans votre application. trackEvents est similaire à trackAppState, mais envoie des événements à la place des noms de page. Les événements sont fournis sous la forme d’une chaîne délimitée par des virgules. La chaîne events doit être fournie pour chaque appel, car elle n’est pas transférée vers l’appel suivant.

Cette méthode effectue un appel sous-jacent à trackLinkURL, où linkURL est défini sur nil, linkType est défini sur "o" et linkName est renseigné avec l’ID de l’application.

Cela signifie que linkTrackVars et linkTrackEvents s’appliquent à des appels à trackEvents.

Les données contextuelles envoyées avec cet appel sont ajoutées aux valeurs de persistentContextData et envoyées avec l’appel. Seules les valeurs définies dans persistentContextData restent pour l’appel suivant.

Syntaxe :

`void trackEvents(string Events)`

Exemples:

`measure.trackEvents("event1");`

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**Remarque importante en cas d’utilisation de la méthode trackLink**

trackEvents effectue un appel sous-jacent à trackLink, où linkURL est défini sur null, linkType est défini sur "o" et linkName a pour valeur l’identifiant de l’application. Cela permet d’empêcher le nombre de pages vues (états vus) d’être incrémenté chaque fois que vous envoyez un événement.

Si vous appelez directement trackLink et définissez les valeurs de linkTrackVars et linkTrackEvents, ces limites de variable et d’événement s’appliquent à TrackEvents. Cela signifie que seuls les variables et événements définis dans cette liste sont envoyés avec TrackEvents. Vous devez définir linkTrackVars et linkTrackEvents sur la valeur null, sauf si vous souhaitez que ces limites soient appliquées à trackEvents.

### Suivi avancé (track et trackLink)

Ces méthodes offrent des options de suivi supplémentaires, vous permettant de renseigner directement les props, eVars et les autres variables SiteCatalyst. Elles doivent être utilisées par des clients disposant d’une mise en œuvre existante ou maîtrisant les autres mises en œuvre de SiteCatalyst.

`track` et `trackLink` sont les principales méthodes de mesure qui sont mises en œuvre dans toutes les versions des bibliothèques de mesures d’Adobe pour plusieurs plates-formes. Dans la plupart des cas, lors du suivi des applications mobiles, il est plus facile d’utiliser les méthodes trackAppState et trackEvents que d’appeler directement les méthodes track et trackLink.

 Le suivi des pages vues (track) et le suivi des liens (trackLink) envoient toutes les variables persistantes ayant des valeurs (non nulles, non vides). Vous devez réinitialiser ou vider toutes les variables, si nécessaire, avant d’appeler track ou trackLink.

*Remarque : En raison de la nature multi-thread des applications modernes, la définition de valeurs de variable persistante à envoyer avec un appel de suivi ultérieur n’est pas recommandée (à l’aide de setEvar, setProp, setHier, SetListVar et setPersistentContextData). Par exemple, si une valeur de variable est définie dans plusieurs threads, la valeur peut être dans un état incohérent lors de l’appel de suivi. Pour éviter ce type de problème, il est recommandé de transmettre les données contextuelles avec chaque appel de suivi et de définir la valeur de la variable dans les règles de traitement.

**Description des méthodes**

**track**: Envoie une page vue standard, ainsi que toutes les variables supplémentaires définies sur l’objet de mesure, au serveur de collecte.

Chaque appel à la méthode track envoie toutes les données persistantes définies dans l’objet de mesure (elles sont répertoriées dans la description de clearVars), plus les variables ou les contextData fournies pour cet appel uniquement. Si vous envoyez une variable qui est définie, toute valeur dans la variable persistante correspondante est remplacée.

Syntaxe :

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

Exemples:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**: Envoie des données de lien personnalisées, de téléchargement ou de sortie aux serveurs de collecte de données Adobe, ainsi que les variables trackconfig qui possèdent des valeurs.

Utilisez trackLink pour effectuer le suivi de toute l’activité qui ne doit pas capturer de page vue.

Syntaxe :

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL** : identifie l’URL ayant fait l’objet d’un clic. Si aucune URL n’est spécifiée, le nom est utilisé. N’utilisez cette méthode que lorsque vous créez un lien d’accès à une page Web depuis l’application Android. Dans tous les autres cas, transmettez la valeur null pour ce paramètre.

**linkType** : identifie le rapport de liens qui affiche l’URL ou le nom. Les valeurs acceptables sont :
* “o” (liens personnalisés)
* “d” (téléchargements de fichier)
* “e” (liens de sortie)

**linkName** : nom figurant dans le rapport de liens. Si aucun nom n’est spécifié, l’URL figure dans le rapport.

Pour collecter les données, vous devez spécifier le paramètre linkURL ou linkName. Lorsque vous n’utilisez pas ces paramètres, des données contextuelles ou d’autres variables, transmettez la valeur null.

Exemples:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**: Définit l'eVar spécifiée sur la valeur fournie. La variable eVar est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant Clear Vars.

Syntaxe :

`void setEvar(int evarNum, String evarValue)`

**setProp**: Définit la prop spécifiée sur la valeur fournie. La variable prop est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant Clear Vars.

Syntaxe :

`void setProp(int propNum, String propValue)`

**setHier**: Définit la variable d’héritier spécifiée sur la valeur fournie. La variable hier est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant Clear Vars.

Syntaxe :

`void setHier(int hierNum, String hierValue)`

**setListVar**: Définit la variable listVar spécifiée sur la valeur fournie. La variable listVar est envoyée avec tous les appels de suivi jusqu’à ce qu’elle soit effacée en la définissant sur une chaîne vide ou en appelant Clear Vars.

Syntaxe :

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**: Les valeurs placées dans les données contextuelles persistantes sont envoyées avec chaque appel au serveur. Pour envoyer des données contextuelles pour un appel unique, envoyez une table de hachage de contextData en tant que paramètre à l’appel de suivi (trackAppState, trackEvents, etc.).

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Voir Données contextuelles.

**clearVars**: Supprime les valeurs des variables suivantes de l’objet :

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Syntaxe :

`void clearVars()`

Exemples:
`measure.clearVars();`

**Suivi hors ligne**

*Remarque : Pour activer AppMeasurement hors ligne, la suite de rapports doit être horodatée.*

Les variables ci-après permettent de stocker des appels de mesure lorsque l’application est hors ligne. Pour activer AppMeasurement hors ligne, la suite de rapports doit être horodatée. Une fois cette modification apportée, tous les accès doivent être horodatés (sinon, ils sont ignorés). Si vous collectez actuellement des données AppMeasurement dans une suite de rapports qui collecte également des données de JavaScript, il est possible que deviez configurer une suite de rapports distincte pour AppMeasurement hors ligne afin d’éviter toute perte de données.

Lorsqu’il est activé, AppMeasurement hors ligne se comporte comme suit :
* L’application envoie un appel du serveur, mais la transmission des données échoue.
* AppMeasurement génère un horodatage pour l’accès actuel.
* AppMeasurement met en mémoire tampon les données de l’accès, et les sauvegarde dans un stockage permanent pour éviter toute perte de données.

Pour chacun des accès suivants ou dans l’intervalle défini par offlineThrottleDelay, AppMeasurement tente d’envoyer les données de l’accès mises en mémoire tampon, en conservant l’ordre des accès. Si la transmission des données échoue, il continue à mettre en tampon les données de l’accès (tant que l’appareil est hors ligne).

### Méthodes de configuration

**setOfflineTrackingEnabled**: La valeur par défaut est false. Active ou désactive le suivi hors ligne pour la bibliothèque de mesures.

Syntaxe :

`void setOfflineTrackingEnabled(boolean Enabled);`

Exemples :
"measure.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**: La valeur par défaut est 1 000. Nombre maximal d’accès hors ligne stockés dans la file d’attente. Si la limite d’accès est supérieure à 5 000, cela peut avoir une influence sur les performances.

Syntaxe :

`void setOfflineHitLimit(int offlineHitLimit)`

Exemples:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**: Renvoie le nombre d’appels de suivi stockés dans la file d’attente hors ligne.

Syntaxe :

`int getTrackingQueueSize()`

Exemples:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**: Supprime tous les appels de suivi stockés de la file d’attente hors ligne.

Syntaxe :

`void clearTrackingQueue()`

Exemples:

`measure.clearTrackingQueue();`

**Avertissement : faites attention lorsque vous effacez manuellement la file d’attente, car cette opération ne peut pas être annulée.**


**setOnline et setOffline**: Définissez manuellement l'état en ligne ou hors ligne de l'objet de mesure. La bibliothèque détecte automatiquement si l’appareil est en ligne ou hors ligne. Ces méthodes ne sont donc nécessaires que si vous voulez forcer la mesure hors ligne. La méthode SetOnline n’est utilisée que pour renvoyer l’état en ligne après la mise hors ligne manuelle.

Lorsque la mesure est hors ligne :

* Si offlineTrackingEnabled a la valeur true : les accès sont stockés jusqu’à ce que la mesure soit en ligne.
* Si offlineTrackingEnabled a la valeur false : les accès sont ignorés.

Syntaxe :

```
void setOnline()
void setOffline()
```

Exemples:

```
measure.setOffline();
measure.setOnline();
```

## Suivi hors ligne

AppMeasurement vous permet de mesurer l’utilisation de l’application même lorsque l’appareil Android est hors ligne.

*Remarque : Pour activer AppMeasurement hors ligne, la suite de rapports doit être horodatée.*

Reportez-vous à Suivi hors ligne

## Target

Adobe permet de diffuser du contenu ciblé au sein d’applications Android.

Le contenu renvoyé par Test&amp;Target peut être tout contenu texte, tel que du code HTML, XML ou du texte brut. Une fois le contenu chargé, il appartient au développeur d’applications Android de déterminer son mode d’utilisation dans l’application. Le contenu peut être affiché au format HTML ou utilisé pour modifier le comportement de l’application. Ce guide contient un exemple simple d’utilisation des classes Test&amp;Target.

Configuration requise

* JDK 5/6/7
* SDK Android pour la plate-forme 1.5 ou version ultérieure.

L’exemple présenté dans cette section repose sur Eclipse.

**Obtention de la bibliothèque**

Consultez la page Mesures et optimisation des applications mobiles sur Developer Connection pour télécharger la bibliothèque Android.

Après avoir décompressé le fichier téléchargé, vous disposerez des composants logiciels suivants :

* admsAppLibrary.jar : bibliothèque conçue pour l’utilisation avec les appareils et simulateurs Android. Requiert Android 2.0 ou une version ultérieure.
* Examples\TrackingHelper.java : classe facultative, conçue pour séparer le code de suivi de la logique applicative.

**Ajout de la bibliothèque à votre projet**

1. Dans Eclipse IDE, cliquez avec le bouton droit sur le nom du projet.
1. Sélectionnez Créer chemin &gt; Ajouter archives externes.
1. Sélectionnez admsAppLibrary.jar.
1. Cliquez sur Ouvrir.
1. Cliquez de nouveau avec le bouton droit sur le projet, puis sélectionnez Build Path (Créer chemin) &gt; Configure Build Path (Configurer création chemin).
1. Cliquez sur l’onglet Order and Export (Classer et exporter).
1. Vérifiez que admsAppLibrary.jar est sélectionné.

Votre application peut importer les classes/interfaces de la bibliothèque admsAppLibrary.jar à l’aide de `importcom.adobe.ADMS.*;`

**Ajout des autorisations d’application**

La bibliothèque AppMeasurement nécessite les autorisations suivantes pour envoyer des données et enregistrer les appels de suivi hors ligne :

* INTERNET
* ACCESS_NETWORK_STATE

Pour ajouter ces autorisations, ajoutez les lignes suivantes à votre fichier AndroidManifest.xml (dans le répertoire du projet d’application) :

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Exemple

Une fois que vous avez ajouté la bibliothèque à votre projet ainsi que les autorisations d’application, vous pouvez utiliser les deux classes Test&amp;Target, MboxFactory et Mbox.

L’exemple ci-après montre comment charger le contenu HTML à partir de Test&amp;Target dans un WebView au sein d’une application Android simple. Il suppose que la campagne et les offres HTML associées ont déjà été créées dans l’outil d’administration Test&amp;Target et que la campagne a été approuvée.

1. Suivez les étapes décrites dans la section Mise en œuvre, puis importez le package testandtarget en haut de la sous-classe d’activité ou d’application :

   `com.adobe.adms.testandtarget.*;`

2. Suivez le code numéroté ci-dessous pour créer une mbox (reportez-vous aux commentaires pour obtenir une explication de chaque ligne de code). Pour exécuter cette procédure, vous devez connaître le code client et le nom de la mbox utilisée dans la configuration de la campagne dans l’outil d’administration Test&amp;Target.

   ```
   public class AndroidDemoApplication extends Activity {
   private WebView _webView;
   public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   _webView = new WebView(this);
   setContentView(_webView);
   // 1. Create an instance of the MboxFactory class with your client code.
   MboxFactory factory = new MboxFactory("androiddemo16");
   // 2. Use the MboxFactory instance to create an Mbox.
   Mbox mbox = factory.create("DemoApp");
   // 3. Set the default content for the Mbox.
   mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
   /**
   * 4. Create a custom MboxContentConsumer to consume the content returned. The
   * CustomMboxContentConsumer class defined below simply displays the content
   * returned in a BrowserField as HTML.
   */
   CustomConsumer consumer = new CustomConsumer(_webView);
   mbox.addOnLoadConsumer(consumer);
   // 5. Load the Mbox.
   mbox.load();
   ...
   ```

3. Définissez la classe personnalisée qui met en œuvre l’interface MboxContentConsumer. Cette interface abstraite vous demande seulement de définir une méthode appelée consume pour y transmettre le contenu. La classe CustomConsumer définie ci-dessous affiche simplement le contenu dans un WebView.

   ```
   class CustomConsumer implements MboxContentConsumer {
   private WebView _view;
   public CustomConsumer(WebView webview) {
   _view = webview;
   }
   public void consume(String content) {
   _view.loadData(content, "text/html", "utf-8");
   }
   }
   ```

4. Cliquez avec le bouton droit sur votre projet, puis sélectionnez Run As (Exécuter comme) &gt; Android Application (Application Android) pour créer et tester votre application. Si vous avez configuré correctement votre campagne Test&amp;Target et l’avez approuvée, votre offre doit être affichée dans l’émulateur d’appareil Android.

**Mesures de cycle de vie**

Si les mesures de cycle de vie sont activées, elles sont envoyées en tant que paramètres à chaque chargement de la mbox.

* (Recommandé) Suivi des événements de cycle de vie
* Mesures de cycle de vie

## Gestion de l’audience

Adobe offre la possibilité d’envoyer des signaux et de récupérer des segments de visiteurs de la gestion de l’audience.

### Configuration requise

* JDK 5/6/7
* SDK Android pour la plate-forme 1.5 ou version ultérieure.

L’exemple présenté dans cette section repose sur Eclipse.

### Obtention de la bibliothèque

Consultez la page Mesures et optimisation des applications mobiles sur Developer Connection pour télécharger la bibliothèque Android.

Après avoir décompressé le fichier téléchargé, vous disposerez des composants logiciels suivants :

* admsAppLibrary.jar : bibliothèque conçue pour l’utilisation avec les appareils et simulateurs Android. Requiert Android 2.0 ou une version ultérieure.
* Examples\TrackingHelper.java : classe facultative, conçue pour séparer le code de suivi de la logique applicative.

### Ajout de la bibliothèque à votre projet

1. Dans Eclipse IDE, cliquez avec le bouton droit sur le nom du projet.
1. Sélectionnez Créer chemin &gt; Ajouter archives externes.
1. Sélectionnez admsAppLibrary.jar.
1. Cliquez sur Ouvrir.
1. Cliquez de nouveau avec le bouton droit sur le projet, puis sélectionnez Build Path (Créer chemin) &gt; Configure Build Path (Configurer création chemin).
1. Cliquez sur l’onglet Order and Export (Classer et exporter).
1. Vérifiez que admsAppLibrary.jar est sélectionné.

Votre application peut importer les classes/interfaces de la bibliothèque admsAppLibrary.jar à l’aide de `importcom.adobe.ADMS.*;`

### Ajout des autorisations d’application

La bibliothèque AppMeasurement nécessite les autorisations suivantes pour envoyer des données et enregistrer les appels de suivi hors ligne :
* INTERNET
* ACCESS_NETWORK_STATE

Pour ajouter ces autorisations, ajoutez les lignes suivantes à votre fichier AndroidManifest.xml (dans le répertoire du projet d’application) :

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Exemple de code

Après avoir ajouté la bibliothèque à votre projet, vous pouvez utiliser la classe ADMS_AudienceManager. To import the audience manager package add: `import com.adobe.adms.audiencemanager;`

1. Configurez la gestion de l’audience :

   `ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

   Remplacez mycompany.demdex.net par votre point de terminaison. La gestion de l’audience peut être configurée à tout moment dans votre application.


2. Si vous le souhaitez, définissez dpid et dpuuid.

   `ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. Créez un dictionnaire de caractéristiques et envoyez-le au moyen d’un signal.

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

Le dictionnaire de profil du visiteur est renvoyé lors du rappel en tant que paramètre content.

### Mesures de cycle de vie

Si les mesures de cycle de vie sont activées et que la gestion de l’audience est configurée dans application:didFinishLaunchingWithOptions:, un signal comportant les mesures de cycle de vie est envoyé à l’issue de la configuration.

* (Recommandé) Suivi des événements de cycle de vie
* Mesures de cycle de vie

### Référence ADMS_AudienceManager

**Méthodes**

**ConfigureAudienceManager**: Définit le point de terminaison de la gestion de l’audience.

Syntaxe :

`public static void ConfigureAudienceManager(String server, Context context);`

Exemple :

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**: Renvoie une valeur booléenne indiquant si les méthodes Audience Manager fournissent ou non la journalisation du débogage dans votre console.

Syntaxe :

`public static boolean GetDebugLogging();`

**GetDpid**: Renvoie le dpid.

Syntaxe :

`public static String GetDpid();`

**GetDpuuid**: Renvoie le dpuuid.

Syntaxe :

`public static String GetDpuuid();`

**GetVisitorProfile**: Cette méthode peut être appelée à tout moment après avoir envoyé un signal pour récupérer le profil du visiteur le plus récent.

Le profil du visiteur comporte toutes les paires clé-valeur qui ont été renvoyées dans l’objet stuff.

Syntaxe :

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**: Active ou désactive la journalisation du débogage dans votre console.

Syntaxe :

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**: Si newDpid et newDpuuid sont définis, ils seront envoyés avec chaque signal.

Syntaxe :

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**: Envoie un dictionnaire de caractéristiques et reçoit le profil du visiteur mis à jour dans callback.

L’uuid provenant de la réponse JSON est enregistré en interne et associé à tous les signaux suivants. Une requête de pixels est également envoyée à chaque URL trouvée dans l’objet dests.

Syntaxe :

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### Interfaces

**Méthodes**


**AudienceManagerCallback**

Syntaxe :

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

L’interface pour l’objet utilisé dans le rappel à partir de l’appel SubmitSignal.


## Module PhoneGap

Ce module permet d’envoyer des appels AppMeasurement pour Android à partir de votre projet PhoneGap.

Pour obtenir de l’aide sur la création d’un projet PhoneGap, reportez-vous à Prise en main de PhoneGap avec Android.

Pour télécharger le module, visitez Modules PhoneGap iOS et Android pour SiteCatalyst.

### Inclusion du module

1. Copiez ADMS_plugin.java dans le package de votre dossier src.
2. Copiez ADMS_Helper.js dans le dossier assets/www/js de votre projet PhoneGap.
3. In the res/xml folder, open config.xml file and register an new plugin by creating a new child node under plugins: `<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />`

For example, if you package is named com.example.phonegaptest, then your plugin node would be the following: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### Inclusion de la bibliothèque AppMeasurement

Pour télécharger la bibliothèque AppMeasurement, reportez-vous à la section Obtention de la bibliothèque.

1. Copiez admsAppLibrary.jar dans le dossier libs de votre projet PhoneGap.
2. Vérifiez que admsAppLibrary.jar figure dans le chemin de création en cliquant avec le bouton droit sur libs &gt; Chemin de création &gt; Configurer le chemin de création.
3. Dans l’onglet Bibliothèques, s’il ne figure pas déjà dans votre liste, cliquez sur Ajouter des fichiers JAR et sélectionnez admsAppLibrary.jar dans votre dossier libs.


### Mesures de cycle de vie et suivi automatique

Le suivi des mesures de cycle de vie requiert une configuration en dehors de PhoneGap. Pour activer le suivi automatique du cycle de vie, suivez la procédure décrite dans la section Mise en œuvre du guide Développeurs : démarrage rapide.

### Utilisation du module

Dans les fichiers html dans lesquels vous voulez utiliser le suivi, incluez :

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

Vous pouvez désormais effectuer des appels de mesure. Voir Méthodes du module PhoneGap.

### Résolution des problèmes

**Ma syntaxe est correcte. Pourquoi le code du module n’est-il pas utilisé ?**

Check your output console for the following error: `java.lang.ClassNotFoundException: ADMS_plugin`

Si cette erreur se produit, vérifiez que vous avez suivi l’étape 3 de la section Inclusion du module.

## Méthodes du module PhoneGap

Dans les fichiers html dans lesquels vous voulez utiliser ces méthodes, incluez :

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**Méthodes de configuration**


**configureMeasurementWithReportSuiteIDsTrackingServer**: Cette méthode permet de configurer les deux paramètres nécessaires au démarrage de la mesure de l’application. Vous devez définir les valeurs reportSuiteIDs et trackingServer sur l’objet de mesure à l’aide de cette méthode avant d’envoyer un appel de serveur.

Syntaxe :

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

Exemple :

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnline et setOffline**: Définissez manuellement l'état en ligne ou hors ligne de l'objet de mesure. La bibliothèque détecte automatiquement si l’appareil est en ligne ou hors ligne. Ces méthodes ne sont donc nécessaires que si vous voulez forcer la mesure hors ligne. La méthode SetOnline n’est utilisée que pour renvoyer l’état en ligne après la mise hors ligne manuelle.

Lorsque la mesure est hors ligne :

* Si offlineTrackingEnabled a la valeur true : les accès sont stockés jusqu’à ce que la mesure soit en ligne.
* Si offlineTrackingEnabled a la valeur false : les accès sont ignorés.

Syntaxe :

```
void setOnline();
void setOffline();
```

Exemple :

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**: Active (true) ou désactive (false) l'affichage des informations de débogage. Par défaut, cette variable a la valeur false.

Vous ne pouvez pas remplacer cette variable en utilisant le remplacement de variable.

Syntaxe :

`void setDebugLogging(bool debugLogging);`

Exemple :

`ADMS.setDebugLogging(true);`

### Méthodes de suivi des événements et des états


**trackAppState**: Il s’agit de la méthode recommandée pour effectuer le suivi des états d’application (par exemple, les pages) dans votre application. La valeur fournie dans appState apparaît comme variable de nom de page de l’appel du serveur. La chaîne appState doit être fournie pour chaque appel, car elle n’est pas transférée vers l’appel suivant.

Syntaxe :

`void trackAppState(string stateName);`

Exemple :

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**: Il s’agit de la méthode recommandée pour effectuer le suivi des états d’application (par exemple, les pages) dans votre application. La valeur fournie dans appState apparaît comme variable de nom de page de l’appel du serveur. La chaîne appState doit être fournie pour chaque appel, car elle n’est pas transférée vers l’appel suivant.

Les données contextuelles envoyées avec cet appel sont ajoutées aux valeurs de persistentContextData et envoyées avec l’appel. Seules les valeurs définies dans persistentContextData restent pour l’appel suivant.

Syntaxe :

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData : objet JSON avec des paires clé-valeur à envoyer dans les données contextuelles.

Exemple :

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**: Il s’agit de la méthode recommandée pour effectuer le suivi des événements dans votre application. trackEvents est similaire à trackAppState, mais envoie des événements à la place des noms de page. Les événements sont fournis sous forme de chaîne délimitée par des virgules trackEvents. La chaîne events doit être fournie pour chaque appel, car elle n’est pas transférée vers l’appel suivant.

Cette méthode effectue un appel sous-jacent à trackLinkURL, où linkURL est défini sur null, linkType est défini sur "o" et linkName est renseigné avec l’ID d’application.

Cela signifie que linkTrackVars et linkTrackEvents s’appliquent à des appels à `trackEvents`.

Syntaxe :

`void trackEvents(string eventNames);`

Exemple :

`ADMS.trackEvents("login,event2");`

**Remarque importante en cas d’utilisation de la méthode trackLink**

`trackEvents` effectue un appel sous-jacent à trackLinkURL, où linkURL est défini sur null, linkType est défini sur "o" et linkName a pour valeur l’identifiant de l’application. Cela permet d’empêcher le nombre de pages vues (états vus) d’être incrémenté chaque fois que vous effectuez le suivi des événements.

Si vous appelez directement trackLinkURL et définissez les valeurs de linkTrackVars et linkTrackEvents, ces limites de variable et d’événement s’appliquent à TrackEvents. Cela signifie que seuls les variables et événements définis dans cette liste sont envoyés avec TrackEvents. Vous devez définir linkTrackVars et linkTrackEvents sur la valeur null, sauf si vous souhaitez que ces limites soient appliquées à trackEvents.

**trackEventsWithContextData**: Il s’agit de la méthode recommandée pour effectuer le suivi des événements dans votre application. trackEvents est similaire à trackAppState, mais envoie des événements à la place des noms de page. Les événements sont fournis sous la forme d’une chaîne délimitée par des virgules. La chaîne events doit être fournie pour chaque appel, car elle n’est pas transférée vers l’appel suivant.

Cette méthode effectue un appel sous-jacent à trackLinkURL, où linkURL est défini sur null, linkType est défini sur "o" et linkName a pour valeur l’identifiant de l’application.

Cela signifie que linkTrackVars et linkTrackEvents s’appliquent à des appels à trackEvents.

Les données contextuelles envoyées avec cet appel sont ajoutées aux valeurs de persistentContextData et envoyées avec l’appel. Seules les valeurs définies dans persistentContextData restent pour l’appel suivant.

Syntaxe :

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData : objet JSON avec des paires clé-valeur à envoyer dans les données contextuelles.

Exemple :

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**Remarque importante en cas d’utilisation de la méthode trackLink**

trackEvents effectue un appel sous-jacent à trackLinkURL, où linkURL est défini sur null, linkType est défini sur "o" et linkName a pour valeur l’identifiant de l’application. Cela permet d’empêcher le nombre de pages vues (états vus) d’être incrémenté chaque fois que vous effectuez le suivi des événements.

Si vous appelez directement trackLinkURL et définissez les valeurs de linkTrackVars et linkTrackEvents, ces limites de variable et d’événement s’appliquent à TrackEvents. Cela signifie que seuls les variables et événements définis dans cette liste sont envoyés avec TrackEvents. Vous devez définir linkTrackVars et linkTrackEvents sur la valeur null, sauf si vous souhaitez que ces limites soient appliquées à trackEvents.

**Méthodes de suivi avancées (track et trackLink)**

Ces méthodes offrent des options de suivi supplémentaires, vous permettant de renseigner directement les props, eVars et les autres variables SiteCatalyst. Elles doivent être utilisées par des clients disposant d’une mise en œuvre existante ou maîtrisant les autres mises en œuvre de SiteCatalyst.

`track` et `trackLink` sont les principales méthodes de mesure qui sont mises en œuvre dans toutes les versions des bibliothèques de mesures d’Adobe pour plusieurs plates-formes. Dans la plupart des cas, lors du suivi des applications mobiles, il est plus facile d’utiliser les méthodes trackAppState et trackEvents que d’appeler directement les méthodes track et trackLink.

 Le suivi des pages vues (track) et le suivi des liens (trackLink) envoient toutes les variables persistantes ayant des valeurs (non nulles, non vides). Vous devez réinitialiser ou vider toutes les variables, si nécessaire, avant d’appeler track ou trackLink.

**Méthodes**

**track**: Envoie une page vue standard, ainsi que toutes les variables supplémentaires définies sur l’objet de mesure, au serveur de collecte.

Syntaxe :

`void track();`

Exemple :

`ADMS.track();`

**trackWithContextData**: Envoie une page vue standard, ainsi que toutes les variables supplémentaires définies sur l’objet de mesure, au serveur de collecte.

Chaque appel à trackWithContextData envoie toutes les données persistantes définies sur l'objet de mesure (elles sont répertoriées dans la description de clearVars), plus les contextData fournies pour cet appel uniquement.

Syntaxe :

`void trackWithContextData(JSON cData);`

cData : objet JSON avec des paires clé-valeur à envoyer dans les données contextuelles.

Exemple :

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**: Envoie une page vue standard, ainsi que toutes les variables supplémentaires définies sur l’objet de mesure, au serveur de collecte.

Chaque appel à trackWithContextDataAndVariables envoie toutes les données persistantes définies sur l'objet de mesure (elles sont répertoriées dans la description de clearVars), plus les contextData et les variables fournies pour cet appel uniquement. Si vous envoyez une variable qui est définie, toute valeur dans la variable persistante correspondante est remplacée.

Syntaxe :

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData : objet JSON avec des paires clé-valeur à envoyer dans les données contextuelles.

Exemple :

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**: Envoie des données de lien personnalisées, de téléchargement ou de sortie aux serveurs de collecte de données Adobe, ainsi que toute variable de configuration de suivi ayant des valeurs.

Utilisez trackLink pour effectuer le suivi de toute l’activité qui ne doit pas capturer de page vue.

Chaque appel à trackLinkURLWithLinkTypeNameContextDataVariables envoie toutes les données persistantes définies sur l'objet de mesure (elles sont répertoriées dans la description de clearVars), plus les contextData fournies pour cet appel uniquement.

Syntaxe :

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData : objet JSON avec des paires clé-valeur à envoyer dans les données contextuelles.

Exemple :

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### Définition et obtention des variables AppMeasurement

**Méthodes**

**setEvarToValue**: Définit l'eVar spécifiée sur la valeur fournie. La variable eVar est envoyée avec l’appel de suivi suivant.

Syntaxe :

`void setEvarToValue(int evar, string value);`

Exemple :

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**: Définit la prop spécifiée sur la valeur fournie. La variable prop est envoyée avec l’appel de suivi suivant.

Syntaxe :

void setPropToValue(int prop, valeur de chaîne);

Exemple :

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**: Définit la variable hier spécifiée sur la valeur fournie. Elle est envoyée avec l’appel de suivi suivant.

Syntaxe :

`void setHierToValue(int hier, string value);`

Exemple :

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**: Définit la variable listvar spécifiée sur la valeur fournie. Elle est envoyée avec l’appel de suivi suivant.

Syntaxe :

`void setListVarToValue(int list, string value);`

Exemple :

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**: Obtient la variable spécifiée.

Syntaxe :

`void getEvar(int evar, function success, function fail);`

Exemple :

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**: Obtient la variable spécifiée.

Syntaxe :

`void getProp(int prop, function success, function fail);`

Exemple :

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**: Obtient la variable spécifiée.

Syntaxe :

`void getHier(int hier, function success, function fail);`

Exemple :

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**: Obtient la variable spécifiée.

Syntaxe :

`void getListVar(int list, function success, function fail);`

Exemple :

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**: Supprime les valeurs des variables suivantes de l’objet :

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Syntaxe :

`void clearVars();`

Exemple :

`ADMS.clearVars();`

**trackingQueueSize**: Obtient ou définit le nombre d'appels de suivi stockés dans la file d'attente hors ligne.

Syntaxe :

`void trackingQueueSize(function success, function fail);`

Exemple :

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**: Supprime tous les appels de suivi stockés de la file d’attente hors ligne. Avertissement : faites attention lorsque vous effacez manuellement la file d’attente, car cette opération ne peut pas être annulée.

Syntaxe :

`void clearTrackingQueue();`

Exemple :

`ADMS.clearTrackingQueue();`

### Définition et obtention des variables de configuration

**Méthodes**

**getVersion**: Obtient la version de la bibliothèque.

Syntaxe :

`void getVersion(function success, function fail);`

Exemple :

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**: (Obligatoire) La ou les suites de rapports (balisage multi-suite) dont vous souhaitez effectuer le suivi. Pour effectuer le suivi de plusieurs suites de rapports, transmettez la liste des noms séparés par des virgules à chaque suite.

Vous ne pouvez pas remplacer cette variable pour un appel unique. Vous devez modifier la valeur persistante.

du lien personnalisé:
`void setReportSuiteIDs(string reportSuiteIDs);`

Exemple :

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**: (Obligatoire) Identifie le serveur de collecte.

Cette variable doit avoir la valeur générée pour vous dans le gestionnaire de code.

La même valeur est utilisée pour le suivi sécurisé lorsque SSL est activé.

Vous ne pouvez pas remplacer cette variable pour un appel unique. Vous devez modifier la valeur persistante.

Syntaxe :

`void setTrackingServer(string trackingServer);`

Exemple :

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

Syntaxe :

`void setDataCenter(string dataCenter);`

Exemple :

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**: La valeur par défaut est CFUUID.

Identifiant unique de chaque visiteur. Si vous ne définissez pas de visitorID personnalisé, un visitorID unique est généré (à l’aide du CFUUID d’Apple) au lancement initial puis stocké dans une clé utilisateur. Cette clé est ensuite utilisée par AppMeasurement et PhoneGap. Elle sera également sauvegardée et restaurée au cours du processus de sauvegarde d’application standard.

Syntaxe :

`void setVisitorID(string visitorId);`

Exemple :

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**: La valeur par défaut est UTF-8.

Syntaxe :

`void setCharSet(string charSet);`

Exemple :

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**: La valeur par défaut est none (la valeur définie pour la suite de rapports est utilisée).

Code de devise utilisé pour les achats ou les événements de devise qui sont
suivis dans l’application iOS.

Syntaxe :

`void setCurrencyCode(string currencyCode);`

Exemple :

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**: La valeur par défaut est false.

Active (true) ou désactive (false) l’envoi de données de mesure via SSL (HTTPS). Vous ne pouvez pas remplacer cette variable pour un appel unique. Vous devez modifier la valeur persistante.

Syntaxe :

`void setSSLEnabled(bool sslEnabled);`

Exemple :

`ADMS.setSSLEnabled(false);`

### Définition et obtention des variables de suivi persistantes

**Méthodes**

**setPurchaseID**:

Syntaxe :

`void setPurchaseID(string purchaseId);`

Exemple :

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

Syntaxe :

`void setTransactionID(string transactionId);`

Exemple :

`ADMS.setTransactionID("transaction1");`

**setAppState**:

Syntaxe :

`void setAppState(string stateName);`

Exemple :

`ADMS.setAppState("myAppState");`

**setChannel**:

Syntaxe :

`void setChannel(string channel);`

Exemple :

`ADMS.setChannel("myChannel");`

**setAppSection**:

Syntaxe :

`void setAppSection(string appSection);`

Exemple :

`DMS.setAppSection("myAppSection");`

**setCampaign**:

Syntaxe :

`void setCampaign(string campaign);`

Exemple :

`ADMS.setCampaign("myCampaign");`

**setProducts**:

Syntaxe :

`void setProducts(string products);`

Exemple :

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

Syntaxe :

`void setEvents(string events);`

Exemple :

`ADMS.setEvents("event1, event2");`

**setGeoState**

Syntaxe :

`void setGeoState(string state);`

Exemple :

`ADMS.setGeoState("FL");`

**setGeoZip**:

Syntaxe :

`void setGeoZip(string zip);`

Exemple :

`ADMS.setGeoZip("39984");`

**setPersistentContextData**: Les données contextuelles sont la méthode recommandée pour collecter les données. Pour envoyer des données contextuelles, créez un objet JSON et affectez des paires clé-valeur pour les valeurs à envoyer.

Syntaxe :

`void setPersistentContextData(JSON cData);`

Exemple :

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistentContextData**:

Syntaxe :

`void persistentContextData(function success, function fail);`

Exemple :

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**: Liste délimitée par des virgules de noms de variables qui limite l’ensemble actuel de variables pour le suivi des liens.

Si linkTrackVars n’est pas défini, le module PhoneGap envoie toutes les variables définies avec un appel trackLink.

Syntaxe :

`void setLinkTrackVars(string linkTrackVars);`

Exemple :

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**: Liste d’événements délimités par des virgules qui limite l’ensemble actuel d’événements pour le suivi des liens. Si linkTrackEvents n’est pas défini, le module PhoneGap envoie tous les événements avec un appel trackLink.

Syntaxe :

`void setLinkTrackEvents(string linkTrackEvents);`

Exemple :

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**: Liste de variables délimitées par des virgules qui limite le jeu actuel de variables pour les appels de suivi léger. Ces variables envoyées avec un appel de serveur léger sont configurées par ClientCare.

Syntaxe :

`void setLightTrackVars(string lightTrackVars);`

Exemple :

`ADMS.setLightTrackVars("prop1,hier3");`

### Suivi hors ligne

**Méthodes**

**setOfflineTrackingEnabled**:

Syntaxe :

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

Exemple :

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

Syntaxe :

`void setOfflineHitLimit(int offlineHitLimit);`

Exemple :

`ADMS.setOfflineHitLimit(3000);`

## Guide de migration de la version 2.x d’Android vers la version 3.x

* AppMeasurement s’appelle désormais ADMS_Measurement. Recherchez les emplacements où cette classe est référencée et remplacez son nom par ADMS_Measurement.
* getInstance s’appelle désormais sharedInstance. Recherchez les emplacements où vous appelez getInstance et remplacez-le par sharedInstance.
* Supprimez tous les appels à la mesure churn (activité) (getChurnInstance). Ces appels sont gérés par le suivi automatique et les variables sont désormais insérées à l’aide de données contextuelles.
* Timestamp est supprimé. La bibliothèque gère automatiquement les horodatages.

La syntaxe des méthodes suivantes a été modifiée. Des exemples mis à jour pour toutes les propriétés et méthodes sont disponibles dans Variables et méthodes de configuration.


### Suite de rapports

**Version précédente (2.1.x)**

`account`

**Nouvelle version (3.x)**

`reportSuiteIDs`

### Track

**Version précédente (2.1.x)**


`String track()`

`String track(Hashtable variableOverrides)`

**Nouvelle version (3.x)**

Transmettez null pour les valeurs inutilisées.

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### Suivi du lien

**Version précédente (2.1.x)**

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**Nouvelle version (3.x)**

Ces deux appels ont été remplacés par un appel unique. Transmettez null pour les valeurs inutilisées.

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### Méthodes de suivi hors ligne

**Version précédente (2.1.x)**

`void forceOffline();`


`void forceOnline();`

**Nouvelle version (3.x)**

`void setOnline();`

`void setOffline();`


### Variables renommées

La liste suivante montre les variables de la version 2.x et leurs valeurs correspondantes dans la version 3.x. Plusieurs variables ont été supprimées de la version 3.x pour que la bibliothèque soit davantage axée sur la mobilité et pour simplifier la mise en œuvre.


*Remarque : La version 3.x utilise des méthodes get et set au lieu de variables publiques. Vous devez mettre à jour les emplacements de votre code où vous définissez des variables directement afin d’utiliser les méthodes get et set.*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## Utilisation de Bloodhound pour tester les applications mobiles

L’outil Bloodhound permet d’envoyer des appels de serveur à un ordinateur local pour tester des applications mobiles.

*Important : Depuis le 30 avril 2017, Adobe Bloodhound fait l’objet d’une élimination progressive. Depuis le 1er mai 2017, plus aucune amélioration n’y est apportée et aucune assistance d’ingénierie supplémentaire ou assistance Adobe Expert Care n’est fournie.*

Pendant le développement des applications, Bloodhound permet d’afficher les appels de serveur localement et éventuellement de transférer les données vers les serveurs de collecte Adobe.

Bloodhound est disponible pour les systèmes d’exploitation Mac et Windows.

### Configuration requise

* Ordinateur Mac Intel exécutant Snow Leopard (10.6) ou version ultérieure ou un PC Windows.
* Connexion réseau à vos périphériques mobiles ou aux simulateurs.

### Télécharger

Consultez Bloodhound : outil de CQ de mesure d’application sur Developer Connection.

### Installation

* Mac : ouvrez le fichier dmg que vous avez téléchargé, puis faites glisser Bloodhound jusqu’au dossier Applications.
* Windows : exécutez le fichier d’installation que vous avez téléchargé.

### Utilisation de Bloodhound

Une fois l’outil démarré, le serveur est désactivé jusqu’à ce que vous cliquiez sur le bouton Start (Démarrer). Cliquez sur le bouton Start lorsque vous êtes prêt à capturer les appels de serveur à partir de l’application.

Vous pouvez éventuellement spécifier un numéro de port personnalisé (doit être supérieur à 1024) avant de démarrer le serveur. Si vous ne spécifiez pas de numéro de port, le serveur sélectionne automatiquement un port ouvert.

Lorsque le serveur est en cours d’exécution, vous devez configurer vos applications ou périphériques pour envoyer les données à l’outil, comme expliqué dans la section suivante.

### Configuration des périphériques pour envoyer les accès à Bloodhound

Vous pouvez modifier les paramètres proxy sur le périphérique pour envoyer des requêtes http à l’outil. Les requêtes envoyées à l’outil peuvent être éventuellement transférées vers les serveurs de collecte de données Adobe.

Si votre périphérique ne prend pas en charge de proxy, vous pouvez envoyer les accès directement à Bloodhound pour les tests.

*Remarque : Bloodhound ne prend pas en charge le suivi SSL. Vous devez désactiver SSL dans la bibliothèque AppMeasurement lorsque vous effectuez des tests à l’aide de Bloodhound.*

#### Appareils iOS

L’appareil iOS doit se trouver sur le même réseau que l’ordinateur qui héberge Bloodhound.

1. Accédez à Settings (Paramètres) &gt; Wi-Fi.
1. Cliquez sur la flèche bleue située à droite du réseau Wi-Fi actuel.
1. Accédez aux paramètres de proxy HTTP.
1. Sélectionnez Auto.
1. Saisissez l’URL du proxy et le port (de l’interface utilisateur Bloodhound) dans le champ URL.

#### Autres périphériques

Si le périphérique prend en charge la configuration automatique du proxy, utilisez l’URL du proxy (de l’interface utilisateur de Bloodhound) comme URL de configuration automatique du proxy (PAC). La prise en charge des proxys varie selon les versions d’Android (il existe des outils de configuration de proxy pour Android afin de simplifier la configuration).

### Envoi direct des accès

Pour les périphériques qui ne prennent pas en charge les proxys (simulateur iOS, anciennes versions d’Android, etc.), il est possible d’utiliser Bloodhound comme serveur de suivi pour capturer les accès générés. Pour ce faire, définissez votre serveur de suivi sur<Bloodhound IP>:<BloodhoundPort>".

Par exemple :

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### Résolution des problèmes/Problèmes courants

* Bloodhound fonctionne uniquement avec un suivi non SSL. Les accès de suivi envoyés via SSL ne sont pas capturés, indépendamment de la méthode utilisée ci-dessus.

## Widgets Android

Les widgets Android peuvent être suivis en utilisant les mêmes méthodes que votre application. Les widgets et votre application partagent le même contexte d’application, de manière à ce que l’ordre d’accès et que l’identification visiteur soient préservés.

Les recommandations suivantes vous aideront à effectuer le suivi des widgets Android :

* Ne mettez pas en œuvre d’appels de mesures de cycle de vie (startActivity/stopActivity) dans le widget même.
* Afin d’être informé lorsqu’un widget est ajouté à l’écran d’accueil, ajoutez un appel trackState ou trackEvent à la méthode onEnabled du widget.
* Afin d’être informé lorsqu’une application est lancée à partir d’un widget, ajoutez un appel trackState ou trackEvent avant de lancer votre application.
* Si vous souhaitez suivre le contexte d’une action, vous pouvez définir une variable ContextData qui vous permet de segmenter chaque action séparément (par exemple : AppExperienceType="widget" vs. "app").
