---
description: Le déploiement d’Analytics se divise en trois étapes principales.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Optimisation - Aperçu
topic: Developer and implementation
uuid: 8e8ecc5b-d4b1-4d13-8525-39e4924df247
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Optimisation - Aperçu

Le déploiement d’Analytics se divise en trois étapes principales.

1. Cela implique de coller un fragment de code HTML sur chaque page (ou modèle de page) d’un site Web. Particulièrement petit (de 400 à 1 000 octets), le fragment de code HTML contient des variables JavaScript et d’autres identifiants qui facilitent le processus de collecte de données.
1. Le fragment de code appelle un fichier de bibliothèque JavaScript, lequel contient des fonctions JavaScript spécifiques à Analytics utilisées au cours de la collecte de mesures. Si l’implémentation du code Analytics est effectuée correctement, le navigateur est généralement en mesure d’exécuter le fichier de bibliothèque JavaScript très rapidement.

1. Le fichier de bibliothèque effectue une demande d’image auprès d’un serveur de collecte de données Adobe. Le serveur collecte les données en cours d’envoi et renvoie une image transparente 1x1 au navigateur du visiteur. Cette troisième étape augmente de manière négligeable la durée totale de téléchargement de la page.

> [!NOTE] Les clients peuvent prendre d’autres mesures pour réduire la surcharge au niveau d’Analytics.

