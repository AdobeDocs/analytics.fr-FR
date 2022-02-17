---
description: Voici des instructions pour vous aider à trouver les ID de votre compte Google et Bing.
title: Localisation des identifiants de compte
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%

---

# Localisation des identifiants de compte

Voici des instructions pour vous aider à trouver les ID de votre compte Google et Bing.

## Google AdWords {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords utilise deux types de comptes : a) compte MCC (My Client Center) et b) compte standard. Pour cette intégration avec Adobe Analytics, **vous devez utiliser la connexion de votre compte standard et pas celle de votre compte MCC**. Cela tient au fait que les comptes MCC fonctionnent comme un compte « parapluie » qui peut accéder à de nombreux comptes AdWords grâce à une seule connexion, alors qu’un compte standard ne peut accéder qu’à un seul compte AdWords par connexion. Google prend en charge la liaison d’une adresse e-mail pour la gestion de 5 comptes, mais Advertising Analytics ne prend pas encore en charge cette fonctionnalité. Une adresse e-mail ne peut être liée qu’à un seul compte Adwords.

Cliquez sur l’icône Compte en haut à droite pour afficher le numéro de compte AdWords (ID de client).

![](assets/google_account.png)

## Bing   {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Si votre compte Bing utilise la fonctionnalité d’importation de Google, veillez à mettre à jour la chaîne de suivi appropriée. La mise à jour de la chaîne de suivi depuis la version de Google vers la chaîne de suivi Bing appropriée ne s’effectue pas automatiquement. Par conséquent, cela peut générer des données non spécifiées. Retrouvez plus de détails sur cette fonctionnalité [ici](https://help.ads.microsoft.com/apex/index/3/fr/50851/).

L’ID de compte, ainsi que celui du client sont requis. Ils sont répertoriés dans l’onglet Comptes.

>[!NOTE]
>
>Le numéro de compte n’est pas le même que l’ID de compte.

![](assets/bing_id.png)
