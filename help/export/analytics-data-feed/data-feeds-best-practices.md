---
description: Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données.
keywords: Flux de données;bonnes pratiques;pic de trafic;horaire;ftp
title: Bonnes pratiques et informations générales
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: c420a9468dc39922bd02047160bb07623503eee4
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 93%

---

# Bonnes pratiques

Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données.

* Veillez à communiquer les pics de trafic anticipés à l’avance. La latence affecte directement les temps de traitement des flux de données. Consultez [Prévision d’un pic de trafic](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) dans le guide de l’utilisateur d’administration.

* Les flux de données ne contiennent pas de contrat de niveau de service sauf lorsque cela est indiqué de manière explicite dans votre contrat avec Adobe. Les flux sont généralement diffusés quelques heures après que la fenêtre de création de rapports est passée, bien que cela puisse prendre de temps en temps jusqu’à 12 heures ou plus.

* Veillez à avoir suffisamment d’espace sur votre site FTP. Supprimez régulièrement les fichiers de la destination de manière à ne pas manque d’espace par inadvertance.

* Les flux horaires utilisant la remise de plusieurs fichiers traitent le plus rapide. Pensez à utiliser plusieurs flux de fichiers horaires si une livraison dans les temps est une priorité élevée pour votre entreprise.

* Si vous utilisez sFTP, ne lisez pas ou supprimez les fichiers comportant un suffixe `.part`. Le suffixe `.part` indique que le fichier a été transféré en partie. Une fois le fichier transféré, le suffixe `.part` disparaît.

* Si vous automatisez votre processus d’ingestion des flux, envisagez la possibilité que les accès et les fichiers puissent être transférés plus d’une fois. Votre processus d’ingestion des flux doit gérer les accès et les fichiers en double sans ignorer ni dupliquer les données. Nous vous recommandons d’utiliser la combinaison des colonnes `hitid_high` et `hitid_low` pour identifier de manière unique un accès.

   Dans de rares cas, vous pourriez voir les valeurs `hitid_high` et `hitid_low` en double. Si cela se produit, vérifiez que le fichier n’a pas été précédemment envoyé et traité. Si seules certaines des lignes d’un fichier sont dupliquées, pensez à ajouter `visit_num` et `visit_page_num` pour déterminer l’unicité.
