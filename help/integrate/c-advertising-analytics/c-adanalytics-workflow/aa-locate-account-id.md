---
description: Voici des instructions pour vous aider à trouver les ID de votre compte Google et Bing.
title: Localisation des identifiants de compte
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 67%

---

# Localisation des identifiants de compte

Voici des instructions pour vous aider à trouver les ID de votre compte Google et Bing.

## Google AdWords {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords utilise deux types de comptes :
>
>- Compte MCC (My Client Center) et
>- Compte standard.
>
>Pour cette intégration avec Adobe Analytics, **vous devez utiliser une connexion au compte standard**, et non une connexion au compte MCC. Cela tient au fait que les comptes MCC fonctionnent comme un compte « parapluie » qui peut accéder à de nombreux comptes AdWords grâce à une seule connexion, alors qu’un compte standard ne peut accéder qu’à un seul compte AdWords par connexion. Google prend en charge la liaison d’une adresse e-mail pour la gestion de 5 comptes, mais Advertising Analytics ne prend pas encore en charge cette fonctionnalité. Une adresse e-mail ne peut être liée qu’à un seul compte Adwords.

Cliquez sur l’icône Compte en haut à droite pour afficher le numéro de compte AdWords (ID de client).

![](assets/google_account.png)

## Bing   {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Si votre compte Bing utilise la fonction d’importation Google, veillez à mettre à jour la chaîne de suivi correcte. La chaîne de suivi n’est pas automatiquement mise à jour de la version Google vers la chaîne de suivi Bing correcte, ce qui peut entraîner des données non spécifiées. Retrouvez plus de détails sur cette fonctionnalité [ici](https://help.ads.microsoft.com/apex/index/3/fr/50851/).

L’ID de compte, ainsi que celui du client sont requis. Ils sont répertoriés dans l’onglet Comptes.

>[!NOTE]
>
>Le numéro de compte n’est pas le même que l’ID de compte.

![](assets/bing_id.png)
