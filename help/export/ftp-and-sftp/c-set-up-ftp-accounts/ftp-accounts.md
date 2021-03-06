---
description: Configurez et utilisez des comptes FTP hébergés par Adobe.
keywords: ftp;sftp
title: Configuration de comptes FTP - Aperçu
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 100%

---

# Configuration de comptes FTP - Aperçu

Configurez et utilisez des comptes FTP hébergés par Adobe.

Adobe gère des grappes FTP haute performance et hautement accessibles, spécialement conçues pour améliorer la fiabilité du transfert des fichiers, sans pour autant nuire aux performances.

Les clients d’Adobe reçoivent des notifications de maintenance par le biais de leur processus standard, en fonction des événements de maintenance programmés. Afin que les systèmes FTP Adobe fonctionnent comme prévu et que le transfert des données reste sécurisé, fiable et hautement performant, Adobe exige que les directives suivantes soient respectées :

* La plupart des comptes FTP Adobe (classifications, sources de données et autres) sont activés automatiquement lorsque la fonction donnée est configurée. Pour les comptes de flux de données et de distribution générale des fichiers, l’assistance clientèle d’Adobe peut configurer un nouveau compte FTP en votre nom. Ce processus permet de garantir la sécurité et la disponibilité de l’espace pour le compte FTP.
* Une fois les données transférées sur leurs systèmes par l’intermédiaire du compte FTP Adobe, il est recommandé aux utilisateurs de les supprimer du FTP.
* Quand les comptes FTP ne sont plus nécessaires, avertissez Adobe afin qu’il les désactive.

L’hôte FTP Adobe se nomme [!DNL ftp.omniture.com] ou [!DNL ftp2.omniture.com].

Cette information, ainsi que le nom d’utilisateur et le mot de passe, doit être fournie dans [!UICONTROL Experience Cloud] (pour les classifications et les sources de données) ou par le représentant Adobe responsable de la configuration du compte à votre demande. Si vous ne savez pas quelle adresse FTP utiliser, contactez votre gestionnaire de compte Adobe pour qu’il vous la fournisse. Par ailleurs, en ce qui concerne les comptes de classifications et de sources de données, Adobe n’a pas défini de créneau horaire spécifique pour le traitement des fichiers FTP. Adobe utilise plutôt un script qui sonde constamment les comptes FTP pour y rechercher les nouveaux fichiers à traiter. Les fichiers chargés dans ces comptes sont traités aussi rapidement que possible.
