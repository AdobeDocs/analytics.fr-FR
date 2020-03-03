---
description: La politique FTP d’Adobe désactive automatiquement l’accès aux comptes FTP qui restent inactifs pendant 90 jours consécutifs.
keywords: ftp;sftp
title: Suppression des données et des comptes liés au FTP
uuid: 1cbd3add-3561-492a-9ed4-aedbd3d5b257
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suppression des données et des comptes liés au FTP

La politique FTP d’Adobe désactive automatiquement l’accès aux comptes FTP qui restent inactifs pendant 90 jours consécutifs.

Adobe supprime alors les comptes FTP désactivés (et supprime définitivement toutes les données stockées dans ces comptes) après une période de grâce de 90 jours supplémentaires. Par exemple, un compte FTP qui reste inactif pendant 90 jours (du 5 juillet 2012 au 2 octobre 2012) est désactivé le 3 octobre 2012. Il est ensuite définitivement supprimé le 2 janvier 2013.

Aucun compte n’est désactivé avant le 5 octobre 2012, aucun compte n’est supprimé avant le 2 janvier 2013.

En outre, Adobe supprime définitivement les anciennes données des comptes actifs, si elles n’ont pas été consultées pendant 90 jours.

Ces politiques restent en vigueur pour tous les comptes FTP, à compter du 5 juillet 2012.

À cette fin et afin de nous assurer que le transfert des données reste sûr et fiable dans l’environnement FTP optimisé, nous demandons à nos clients de procéder comme suit :

* Supprimez les données sortantes du système FTP une fois que les données ont été transférées vers votre environnement en interne. Adobe identifie et supprime les fichiers restant sur le système après 90 jours.
* Quand les comptes FTP ne sont plus nécessaires, avertissez Adobe afin qu’il les désactive et les supprime.

