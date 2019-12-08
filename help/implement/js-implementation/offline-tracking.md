---
description: Les variables et fonctions ci-après vous permettent de stocker des appels de mesure lorsque l’application est hors ligne.
keywords: Analytics Implementation
title: Suivi hors ligne
topic: Developer and implementation
uuid: f7c55aef-28a4-4f2f-8f47-792a05f9525b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suivi hors ligne

Les variables et fonctions ci-après vous permettent de stocker des appels de mesure lorsque l’application est hors ligne.

> [!NOTE] Pour activer le suivi hors ligne, la suite de rapports doit être horodatée. Si les horodatages sont activés sur votre suite de rapports, votre propriété de configuration `trackOffline` *doit* être définie sur « true ». Sinon, la propriété de configuration `trackOffline` *doit* être définie sur « false ». En cas de configuration incorrecte, les données seront perdues. Si vous ne savez pas si une suite de rapports est horodatée, [contactez le service d’assistance clientèle](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

Lorsqu’il est activé, AppMeasurement hors ligne se comporte comme suit :

* L’application envoie un appel du serveur, mais la transmission des données échoue.
* AppMeasurement génère un horodatage pour l’accès actuel.
* AppMeasurement met en mémoire tampon les données de l’accès, et les sauvegarde dans un stockage permanent pour éviter toute perte de données.

Pour chacun des accès suivants ou dans l’intervalle défini par `offlineThrottleDelay`, AppMeasurement tente d'envoyer les données de l'accès mises en mémoire tampon, en conservant l'ordre des accès. Si la transmission des données échoue, il continue à mettre en tampon les données de l’accès (tant que l’appareil est hors ligne).

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Propriété ou méthode </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>Valeur par défaut : false </p> <p>Active ou désactive le suivi hors ligne pour la bibliothèque de mesures. </p> <p> <b>Exemples:</b> </p> 
    <code class="syntax c">
      s.trackOffline=true; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>Valeur par défaut : aucune limite </p> <p>Nombre maximal d’accès hors ligne stockés dans la file d’attente. </p> <p> <b>Exemples:</b> </p> 
    <code class="syntax c">
      s.offlineHitLimit=100; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>Valeur par défaut : 0 </p> <p>Indique une cadence (ou un délai), en millisecondes, pour l’envoi de données d’accès en mémoire tampon lorsque AppMeasurement détecte une connexion réseau active. Sur le plan des performances, cela contribue à atténuer les effets consécutifs à l’envoi de plusieurs accès sur l’application. </p> <p>Par exemple, si offlineThrottleDelay=1000, et que 300 ms sont nécessaires pour envoyer les données d’accès, AppMeasurement attend 700 ms avant d’envoyer le prochain accès en mémoire tampon. </p> 
    <code class="syntax c">
      s.offlineThrottleDelay=1000; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> Permet de définir manuellement l’état hors ligne ou en ligne de l’objet de mesure. La bibliothèque détecte automatiquement si l’appareil est en ligne ou hors ligne. Ces méthodes ne sont donc nécessaires que si vous voulez forcer la mesure hors ligne. La méthode <code> forceOnline </code> n’est utilisée que pour revenir à l’état en ligne après une mise hors ligne manuelle. </p> <p>Lorsque la mesure est hors ligne : </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> Si <code> trackOffline </code> a la valeur « true » : les accès sont stockés jusqu’à ce que la mesure soit en ligne. </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> Si <code> trackOffline </code> a la valeur « false » : les accès sont ignorés. </li> 
    </ul> <p> <b>Exemples:</b> </p> 
    

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
