---
description: Le tableau ci-dessous montre les erreurs de code courantes et le code correct.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Erreurs de syntaxe courantes
topic: Developer and implementation
uuid: 9845dcb9-9f10-4f65-a43d-2af41edaa122
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Erreurs de syntaxe courantes

Le tableau ci-dessous montre les erreurs de code courantes et le code correct.

| Incorrect | Correct |
|---|---|
| prop1 | s.prop1 (utilise « s. ») |
| s.evar1 | s.eVar1 (utilise la mise en majuscule correcte) |
| s.pagetype='errorpage'; | s.pageType='errorPage'; (utilise la mise en majuscule correcte) |
| s.tl(this,o,pageA) | s.tl(this,'o','pageA'); (utilisation correcte des guillemets simples) |
| s.events='event1'; s.events='event2'; | s.events='event1,event2'; (format correct) |
| s.pageName="John" (guillemets anglais activés) | s.pageName="John" (guillemets anglais désactivés) |
| s.products="shoes,UX4879,1,19.99" | s.products="shoes;UX4879;1;19.99" (utilise des points-virgules, et non des virgules) |
| s.products=";MacBook Air;1;$1999.99" | s.products=";MacBook Air;1;1999.99" (n’utilise pas le symbole dollar) |
| s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183" | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95" (les longs prix sont arrondis ou tronqués) |
| var s_account="rsid1, rsid2" | var s_account="rsid1,rsid2" (pas d’espace entre les identifiants de suite de rapports lors du marquage multisuite) |
| s.events="event1, event2" | s.events="event1,event2" (pas d’espace entre les identifiants d’événement lors du marquage multisuite) |
| s.products="product name" | s.products=";product name" (utilisation d’un point-virgule lorsqu’aucune catégorie de produit n’est répertoriée) |

## Remarques supplémentaires {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

Conservez le commentaire HTML de fermeture à la fin du code Adobe (même si vous utilisez la partie NOSCRIPT du script).
