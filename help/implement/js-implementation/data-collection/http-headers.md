---
description: Les en-têtes de demande et de réponse HTTP servent à collecter d’autres données en plus de celles collectées par AppMeasurement. Cette section décrit les en-têtes utilisés pendant la collecte des données.
keywords: Analytics Implementation
title: En-têtes HTTP de collecte de données
topic: Developer and implementation
uuid: 3325e13c-b300-46e4-a592-3a83ed59718b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# En-têtes HTTP de collecte de données

Les en-têtes de demande et de réponse HTTP servent à collecter d’autres données en plus de celles collectées par AppMeasurement. Cette section décrit les en-têtes utilisés pendant la collecte des données.

## En-têtes de demande HTTP {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>En-tête</b> </td> 
   <td> <b>Utilisation</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>Cookies de lecture précédemment créés par les serveurs de collecte de données Adobe. </p> <p> À compter de 2014, les serveurs Adobe ignoreront tous les cookies accompagnant un appel de serveur, à l’exception de ceux définis par Adobe. Voir <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/">Cookies utilisés dans Experience Cloud</a> pour obtenir la liste complète des cookies d’Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td> User-Agent </td> 
   <td> Utilisé pour la détection du navigateur, du système d’exploitation et du périphérique mobile. </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> Utilisé en remplacement de l’en-tête User-Agent pour la détection correcte du navigateur, du système d’exploitation et du périphérique mobile pour certains navigateurs comme OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> Utilisé en remplacement de l’en-tête User-Agent pour la détection correcte du navigateur, du système d’exploitation et du périphérique mobile pour certains navigateurs comme OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-OperaMini-Phone-UA </td> 
   <td> Utilisé en remplacement de l’en-tête User-Agent pour la détection correcte du navigateur, du système d’exploitation et du périphérique mobile pour certains navigateurs comme OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> Utilisé en remplacement de l’en-tête User-Agent pour la détection correcte du navigateur, du système d’exploitation et du périphérique mobile pour certains navigateurs comme OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> Utilisé en remplacement de l’en-tête User-Agent pour la détection correcte du navigateur, du système d’exploitation et du périphérique mobile pour certains navigateurs comme OperaMini. </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> Utilisé en remplacement pour identifier le système d’exploitation. </td> 
  </tr> 
  <tr> 
   <td> UA-Pixels </td> 
   <td> Utilisé comme autre source pour la résolution d’écran du client. </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> Utilisé comme autre source pour la profondeur de couleur de l’écran du client. </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> Détecte que la demande de collecte de données était effectuée dans le cadre de la prérécupération d’une page Web. </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> Détecte que la demande de collecte de données était effectuée lorsque le navigateur affichait un aperçu d’une page Web. </td> 
  </tr> 
  <tr> 
   <td> Accept </td> 
   <td> Utilisé pour identifier les formats d’image pris en charge par le navigateur afin qu’Adobe sache s’il doit renvoyer une image GIF ou WBMP. </td> 
  </tr> 
  <tr> 
   <td> Referrer </td> 
   <td> Utilisé en tant qu’en-tête de secours pour obtenir des informations sur l’URL de la page à partir de laquelle la demande de collecte de données a été effectuée lorsqu’elle n’a pas été transmise sur la chaîne de requête ou lorsqu’elle est différente de la valeur de la chaîne de requête. </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> Utilisé pour rechercher l’adresse IP correcte du client qui a effectué la demande de collecte de données. L’adresse IP sert à générer des rapports sur la région géographique, l’opérateur de téléphonie mobile, ainsi que d’autres rapports. </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Les implémentations qui utilisent des variables dynamiques ont une possibilité de lecture dans d’autres en-têtes de demande HTTP qui ne sont pas répertoriés ci-dessus.

## En-têtes de réponse HTTP {#section_A9C7035198C84037A21A8033CC408F0E}

| **En-tête** | **Utilisation** |
|---|---|
| Access-Control-Allow-Origin | Utilisé pour activer la prise en charge des demandes de collecte de données de style de partage de ressources interorigines sur les serveurs Adobe. |
| Date d’expiration | Contrôle de la mise en cache du navigateur. |
| Last-Modified | Contrôle de la mise en cache du navigateur. |
| Cache-Control | Contrôle de la mise en cache du navigateur. |
| Pragma | Contrôle de la mise en cache du navigateur. |
| ETag | Contrôle de la mise en cache du navigateur. |
| Vary | Contrôle de la mise en cache du navigateur. |
| P3P | Fournit la stratégie P3P par défaut ou personnalisée de la demande de collecte de données. |
| État | Contient l’état « SUCCESS » ou « FAILURE » d’une demande d’aucun contenu. Utilisé uniquement quand la demande indique qu’aucun contenu ne doit être envoyé. |
| Reason | Contient le motif de l’état d’échec d’une demande d’aucun contenu. Utilisé uniquement quand la demande indique qu’aucun contenu ne doit être envoyé. |
| Emplacement | Utilisé pour rediriger le client effectuant la demande de collecte de données vers une autre URL. La négociation du cookie Adobe pour détecter la possibilité de définir le cookie identifiant visiteur est un exemple. |
| Content-Type | Spécifie le type de contenu renvoyé au client (GIF, texte, code JavaScript, etc.) |
| Content-Length | Spécifie la taille du contenu renvoyé au client. |

> [!NOTE] D’autres en-têtes HTTP peuvent être définis dans la réponse pour le contrôle d’état interne. Certains de ces en-têtes peuvent être renvoyés au navigateur, mais il n’est pas nécessaire qu’il les reçoit.
