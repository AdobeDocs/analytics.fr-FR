---
description: 'Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, Tu devrais '
keywords: Flux de données;bonnes pratiques;pic de trafic;horaire;ftp
seo-description: 'Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, Tu devrais '
seo-title: Bonnes pratiques et informations générales
solution: Analytics
title: Bonnes pratiques et informations générales
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Bonnes pratiques et informations générales

Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données, notamment :

* Dans 95 % des cas, les flux de données sont diffusés dans les 12 heures suivant la fin d’une période spécifique.

   Par exemple, pour un flux horaire, le flux de données pour la période comprise entre 3 heures et 4 heures sera normalement diffusé avant 16 heures dans 95 % des cas. Le traitement et la diffusion des flux de données concernant les suites de rapports avec un volume de trafic conséquent peuvent être plus longs, surtout s’il s’agit de flux quotidiens et non horaires.
* Veillez à [communiquer les pics de trafic anticipés](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) à l’avance. Toute latence en amont a un impact direct sur le temps de démarrage du processus de flux de données.
* Veillez à avoir suffisamment d’espace sur votre site FTP. Nettoyez-le régulièrement pour ne pas manquer d'espace disque par inadvertance.
* Lorsque vous modifiez les informations d’identification du site FTP, veillez à ce qu’elles soient à jour dans le système de flux de données d’Adobe.
* Utilisez si possible la remise horaire. Ainsi, les fichiers sont plus petits et leur production/transmission plus rapide.
* Envisagez l’utilisation de la diffusion à "fichiers multiples" (généralement réalisée avec des flux quotidiens volumineux). Les remises de fichiers multiples divisent le fichier monolithique en fichiers plus petits qui sont tous remis simultanément. Là encore, des fichiers plus petits permettent de créer, de compresser/décompresser et de transmettre plus rapidement les données.
* Si vous utilisez sFTP comme méthode de remise, ne lisez pas et ne supprimez pas les fichiers avec le suffixe ".part". Le suffixe ".part" indique que le fichier est partiellement transféré, mais qu’il n’est pas terminé. Une fois le fichier transféré, il sera renommé sans le suffixe ".part".
* Créez votre processus ETL en gardant à l’esprit qu’à certaines occasions, un fichier peut être transféré plus d’une fois. Vous éviterez ainsi les doublons de données.
