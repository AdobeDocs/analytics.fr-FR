---
description: Voici des instructions pour vous aider à trouver les ID de votre compte Google et Bing.
title: Localisation des identifiants de compte
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 0453f374e9027d1c539682212e880c4ebc81152f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 55%

---

# Localisation des identifiants de compte

Voici des instructions pour vous aider à trouver les ID de votre compte Google et Bing.

## Google Ads (AdWords) {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords utilise deux types de comptes :
>
>- un compte MCC (My Client Center), et
>- Compte Standard.
>
>Pour cette intégration à Adobe Analytics, **vous devez utiliser un identifiant de connexion de compte standard** et non un identifiant de connexion de compte MCC. Cela tient au fait que les comptes MCC fonctionnent comme un compte « parapluie » qui peut accéder à de nombreux comptes AdWords grâce à une seule connexion, alors qu’un compte standard ne peut accéder qu’à un seul compte AdWords par connexion. Google prend en charge la liaison d’une adresse e-mail pour la gestion de 5 comptes, mais Advertising Analytics ne prend pas encore en charge cette fonctionnalité. Une adresse e-mail ne peut être liée qu’à un seul compte Adwords.

Cliquez sur l’icône Compte en haut à droite pour afficher le numéro de compte AdWords (ID de client).

![Compte Google Ads Manager](assets/google-account.png)

## Microsoft Advertising (Bing) {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Si votre compte Microsoft Advertising (anciennement appelé Bing) utilise la fonction d’importation Google, veillez à mettre à jour la chaîne de suivi appropriée. La chaîne de suivi n’est pas automatiquement mise à jour de la version de Google vers la chaîne de suivi Bing appropriée et peut entraîner des données non spécifiées. Retrouvez plus de détails sur cette fonctionnalité [ici](https://help.ads.microsoft.com/apex/index/3/fr/50851/).

Les **[!UICONTROL ID de compte]** et **[!UICONTROL Numéro de compte]** sont tous deux obligatoires. Ils sont répertoriés dans l’onglet **[!UICONTROL Paramètres des comptes]** de **[!UICONTROL Paramètres]**.

>[!NOTE]
>
>Le numéro de compte n’est pas le même que l’ID de compte.

![Microsoft Advertising](assets/bing-id.png)
