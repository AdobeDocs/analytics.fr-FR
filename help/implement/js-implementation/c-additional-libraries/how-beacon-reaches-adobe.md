---
description: Lorsqu’un périphérique mobile demande une page d’un serveur Web, la demande est envoyée via une passerelle qui convertit la demande mobile (en règle générale, avec le protocole WAP ou I-Mode) en une demande HTTP envoyée au serveur Web.
keywords: Implémentation d'Analytics ; gateway ; wap ; i-mode ; wbmp
seo-description: Lorsqu’un périphérique mobile demande une page d’un serveur Web, la demande est envoyée via une passerelle qui convertit la demande mobile (en règle générale, avec le protocole WAP ou I-Mode) en une demande HTTP envoyée au serveur Web.
seo-title: Passerelle réseau de protocole mobile
solution: Analytics
title: Passerelle réseau de protocole mobile
topic: Développeur et mise en œuvre
uuid: a 2 c 92 ce 2-53 a 9-4 b 5 b-be 1 a -89 d 9 f 1 bf 776 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Passerelle réseau de protocole mobile

Lorsqu’un périphérique mobile demande une page d’un serveur Web, la demande est envoyée via une passerelle qui convertit la demande mobile (en règle générale, avec le protocole WAP ou I-Mode) en une demande HTTP envoyée au serveur Web.

Lorsqu’un périphérique mobile demande une page d’un serveur Web, la demande est envoyée via une passerelle qui convertit la demande mobile (en règle générale, avec le protocole WAP ou I-Mode) en une demande HTTP envoyée au serveur Web. Le serveur Web répond à la passerelle, qui transfère la demande vers le téléphone. Cette passerelle joue un rôle similaire à celui d’un serveur proxy standard. Toutefois, elle transfère la chaîne de l’agent utilisateur du périphérique mobile vers le serveur Web. Le serveur Web peut ainsi répondre avec une page créée tout particulièrement pour le périphérique qui la demande.

La taille d’écran des périphériques mobiles WAP étant assez limitée, les pages mobiles sont très légères. Elles ne contiennent, bien souvent, que du texte et une image mise en cache. Lorsque la balise d’image est ajoutée aux pages, une demande est envoyée sur chaque page pour une image des serveurs Adobe. Lorsque l’image (fichier WBMP) est renvoyée, les serveurs Adobe demandent au navigateur de ne pas la mettre en cache. De ce fait, l’image est demandée de nouveau sur les pages suivantes. Le nombre aléatoire décrit ci-dessus doit être utilisé comme protection contre les navigateurs qui ne respectent pas les instructions de non mise en cache d’Adobe. 
