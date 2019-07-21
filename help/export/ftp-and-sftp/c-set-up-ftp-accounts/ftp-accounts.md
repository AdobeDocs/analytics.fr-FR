---
description: Configurez et utilisez des comptes FTP hébergés par Adobe.
keywords: ftp ; sftp
seo-description: Configurez et utilisez des comptes FTP hébergés par Adobe.
seo-title: Configuration des comptes FTP - Présentation
solution: Analytics
title: Configuration des comptes FTP - Présentation
uuid: e 5524619-248 a -4 aae -9 f 64-cd 7 d 33 f 3 c 407
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configuration des comptes FTP - Présentation

Configurez et utilisez des comptes FTP hébergés par Adobe.

Adobe gère des grappes FTP haute performance et hautement accessibles, spécialement conçues pour améliorer la fiabilité du transfert des fichiers, sans pour autant nuire aux performances.

Les clients d’Adobe reçoivent des notifications de maintenance par le biais de leur processus standard, en fonction des événements de maintenance programmés. Afin que les systèmes FTP Adobe fonctionnent comme prévu et que le transfert des données reste sécurisé, fiable et hautement performant, Adobe exige que les directives suivantes soient respectées :

* La plupart des comptes FTP Adobe (classifications, sources de données et autres) sont activés automatiquement lorsque la fonction donnée est configurée. Pour les comptes de flux de données et de distribution générale des fichiers, l’assistance clientèle d’Adobe peut configurer un nouveau compte FTP en votre nom. Ce processus permet de garantir la sécurité et la disponibilité de l’espace pour le compte FTP.
* Une fois les données transférées sur leurs systèmes par l’intermédiaire du compte FTP Adobe, il est recommandé aux utilisateurs de les supprimer du FTP.
* Quand les comptes FTP ne sont plus nécessaires, avertissez Adobe afin qu’il les désactive.

The Adobe FTP host name is [!DNL ftp.omniture.com] or [!DNL ftp2.omniture.com].

This information, along with a username and password, should be provided either within the [!UICONTROL Experience Cloud] (for classifications and Data Sources), or by the Adobe representative responsible for setting up the account at your request. Si vous ne savez pas quelle adresse FTP utiliser, contactez votre gestionnaire de compte Adobe pour qu’il vous la fournisse. Par ailleurs, en ce qui concerne les comptes de classifications et de sources de données, Adobe n’a pas défini de créneau horaire spécifique pour le traitement des fichiers FTP. Adobe utilise plutôt un script qui sonde constamment les comptes FTP pour y rechercher les nouveaux fichiers à traiter. Les fichiers chargés dans ces comptes sont traités aussi rapidement que possible.
