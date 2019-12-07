---
description: Lorsqu’un périphérique mobile demande une page d’un serveur Web, la demande est envoyée via une passerelle qui convertit la demande mobile (en règle générale, avec le protocole WAP ou I-Mode) en une demande HTTP envoyée au serveur Web.
keywords: Analytics Implementation;gateway;wap;i-mode;wbmp
title: Protocole mobile – Passerelle réseau
topic: Developer and implementation
uuid: a2c92ce2-53a9-4b5b-be1a-89d9f1bf776f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Protocole mobile – Passerelle réseau

Lorsqu’un périphérique mobile demande une page d’un serveur Web, la demande est envoyée via une passerelle qui convertit la demande mobile (en règle générale, avec le protocole WAP ou I-Mode) en une demande HTTP envoyée au serveur Web.

Lorsqu’un périphérique mobile demande une page d’un serveur Web, la demande est envoyée via une passerelle qui convertit la demande mobile (en règle générale, avec le protocole WAP ou I-Mode) en une demande HTTP envoyée au serveur Web. Le serveur Web répond à la passerelle, qui transfère la demande vers le téléphone. Cette passerelle joue un rôle similaire à celui d’un serveur proxy standard. Toutefois, elle transfère la chaîne de l’agent utilisateur du périphérique mobile vers le serveur Web. Le serveur Web peut ainsi répondre avec une page créée tout particulièrement pour le périphérique qui la demande.

La taille d’écran des périphériques mobiles WAP étant assez limitée, les pages mobiles sont très légères. Elles ne contiennent, bien souvent, que du texte et une image mise en cache. Lorsque la balise d’image est ajoutée aux pages, une demande est envoyée sur chaque page pour une image des serveurs Adobe. Lorsque l’image (fichier WBMP) est renvoyée, les serveurs Adobe demandent au navigateur de ne pas la mettre en cache. De ce fait, l’image est demandée de nouveau sur les pages suivantes. Le nombre aléatoire décrit ci-dessus doit être utilisé comme protection contre les navigateurs qui ne respectent pas les instructions de non mise en cache d’Adobe.
