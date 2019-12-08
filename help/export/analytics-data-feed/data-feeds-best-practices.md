---
description: 'Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, Tu devrais '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: Bonnes pratiques et informations générales
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bonnes pratiques

Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, 

* Veillez à communiquer les pics de trafic anticipés à l’avance. La latence affecte directement le temps de traitement des flux de données. Voir [Planification d’un pic](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) de trafic dans le guide de l’utilisateur Admin.
* Les flux de données ne contiennent pas d’accord de niveau de service, sauf disposition explicite dans votre contrat avec Adobe. Les flux sont généralement distribués dans les heures qui suivent la fin de la fenêtre de création de rapports, mais peuvent parfois prendre jusqu’à 12 heures ou plus.
* Veillez à avoir suffisamment d’espace sur votre site FTP. Supprimez régulièrement les fichiers de la destination afin de ne pas manquer d’espace disque par inadvertance.
* Les flux horaires utilisant plusieurs fichiers sont traités le plus rapidement. Pensez à utiliser des flux de plusieurs fichiers par heure si une remise en temps voulu est une priorité élevée pour votre entreprise.
* Si vous utilisez sFTP, ne lisez ni ne supprimez les fichiers avec un `.part` suffixe. Le `.part` suffixe indique que le fichier est partiellement transféré. Une fois le fichier transféré, le `.part` suffixe disparaît.
* Si vous automatisez le processus d’assimilation des flux, pensez à la possibilité de transférer plusieurs fois un fichier. Les fichiers en double peuvent être renvoyés par l’utilisateur ou rarement par Adobe.
