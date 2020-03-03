---
description: 'Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données. Vous devez : '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: Bonnes pratiques et informations générales
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bonnes pratiques

Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données.

* Veillez à communiquer les pics de trafic anticipés à l’avance. La latence affecte directement les temps de traitement des flux de données. Consultez [Prévision d’un pic de trafic](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) dans le guide de l’utilisateur d’administration.
* Les flux de données ne contiennent pas de contrat de niveau de service sauf lorsque cela est indiqué de manière explicite dans votre contrat avec Adobe. Les flux sont généralement diffusés quelques heures après que la fenêtre de création de rapports est passée, bien que cela puisse prendre de temps en temps jusqu’à 12 heures ou plus.
* Veillez à avoir suffisamment d’espace sur votre site FTP. Supprimez régulièrement les fichiers de la destination de manière à ne pas manque d’espace par inadvertance.
* Les flux horaires utilisant la remise de plusieurs fichiers traitent le plus rapide. Pensez à utiliser plusieurs flux de fichiers horaires si une livraison dans les temps est une priorité élevée pour votre entreprise.
* Si vous utilisez sFTP, ne lisez pas ou supprimez les fichiers comportant un suffixe `.part`. Le suffixe `.part` indique que le fichier a été transféré en partie. Une fois le fichier transféré, le suffixe `.part` disparaît.
* Si vous automatisez votre processus d’ingestion des flux, envisagez la possibilité qu’un fichier puisse être transféré plus d’une fois. Les fichiers en double peuvent être renvoyés par l’utilisateur ou plus rarement par Adobe.
