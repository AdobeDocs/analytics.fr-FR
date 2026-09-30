---
description: Découvrez les bonnes pratiques relatives au traitement et à la diffusion des flux de données dans Analytics.
keywords: Flux de données;bonnes pratiques;pic de trafic;horaire;ftp
title: Bonnes pratiques et informations générales
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
TQID: 'https://experienceleague.adobe.com/-8EoregiCONFrXywjKP5zMdypH-FM67ij1nVfxupBdY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
    internal-label: Data feeds
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 84%
---
# Bonnes pratiques relatives aux flux de données

Vous trouverez ci-dessous quelques bonnes pratiques concernant le traitement et la diffusion des flux de données.

* Veillez à communiquer les pics de trafic anticipés à l’avance. La latence affecte directement les temps de traitement des flux de données. Consultez [Prévision d’un pic de trafic](/help/admin/tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md) dans le guide de l’utilisateur d’administration.

* Les flux de données ne contiennent pas de contrat de niveau de service sauf lorsque cela est indiqué de manière explicite dans votre contrat avec Adobe. Les flux sont généralement diffusés quelques heures après que la fenêtre de création de rapports est passée, bien que cela puisse prendre de temps en temps jusqu’à 12 heures ou plus.

* Les flux horaires utilisant la diffusion de plusieurs fichiers sont traités le plus rapidement. Pensez à utiliser plusieurs flux de fichiers horaires si une livraison dans les temps est une priorité élevée pour votre entreprise.

* Si vous automatisez votre processus d’ingestion des flux, envisagez la possibilité que les hits et les fichiers puissent être transférés plus d’une fois. Votre processus d’ingestion des flux doit gérer les hits et les fichiers en double sans générer d’erreur ni dupliquer les données. Nous vous recommandons d’utiliser la combinaison des colonnes `hitid_high` et `hitid_low` pour identifier de manière unique un hit.

  Dans de rares cas, vous pourriez voir les valeurs `hitid_high` et `hitid_low` en double. Si cela se produit, vérifiez que le fichier n’a pas été précédemment envoyé et traité. Si seules certaines des lignes dʼun fichier sont dupliquées, pensez à ajouter `visit_num` et `visit_page_num` pour aider à en établir lʼunicité.

* Si vous utilisez le protocole FTP (non recommandé), assurez-vous de disposer de suffisamment d’espace sur votre site FTP. Supprimez régulièrement les fichiers de la destination pour éviter de pas manquer d’espace disque par inadvertance.

* Si vous utilisez le protocole sFTP (non recommandé), ne lisez ou ne supprimez pas les fichiers comportant un suffixe `.part`. Le suffixe `.part` indique que le fichier a été transféré en partie. Une fois le fichier transféré, le suffixe `.part` disparaît.