---
description: 'Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, Vous devriez '
keywords: Flux de données ; bonnes pratiques ; pic de trafic ; horaire ; ftp
seo-description: 'Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, Vous devriez '
seo-title: Bonnes pratiques et informations générales
solution: Analytics
title: Bonnes pratiques et informations générales
uuid: f 2 d 6 c 13 a -5 d 4 e -4 fc 2-8 baa -28 c 69 f 0 cf 5 f 6
translation-type: tm+mt
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566

---


# Bonnes pratiques et informations générales

Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, notamment :

* Dans 95 % des cas, les flux de données sont diffusés dans les 12 heures suivant la fin d’une période spécifique.

   Par exemple, pour un flux horaire, le flux de données pour la période comprise entre 3 heures et 4 heures sera normalement diffusé avant 16 heures dans 95 % des cas. Le traitement et la diffusion des flux de données concernant les suites de rapports avec un volume de trafic conséquent peuvent être plus longs, surtout s’il s’agit de flux quotidiens et non horaires.
* Veillez à [communiquer les pics de trafic anticipés](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) à l’avance. Toute latence en amont a un impact direct sur le temps de démarrage du processus de flux de données.
* Veillez à avoir suffisamment d’espace sur votre site FTP. Nettoyez-le régulièrement afin de ne pas manquer d’espace par inadvertance.
* Lorsque vous modifiez les informations d’identification du site FTP, veillez à ce qu’elles soient à jour dans le système de flux de données d’Adobe.
* Utilisez si possible la remise horaire. Ainsi, les fichiers sont plus petits et leur production/transmission plus rapide.
* Envisagez d’utiliser la remise « fichiers multiples » (généralement avec les flux quotidiens volumineux). Les remises de fichiers multiples divisent le fichier monolithique en fichiers plus petits qui sont tous remis simultanément. Là encore, des fichiers plus petits permettent de créer, de compresser/décompresser et de transmettre plus rapidement les données.
* Si vous utilisez la méthode de diffusion sFTP, ne lisez ni ne supprimez les fichiers dotés d’un suffixe « .part ». Ce suffixe indique que le transfert du fichier est inachevé. Une fois le fichier transféré, il sera renommé sans le suffixe « .part ».
* Créez votre processus ETL en gardant à l’esprit qu’à certaines occasions, un fichier peut être transféré plus d’une fois. Vous éviterez ainsi les doublons de données.
