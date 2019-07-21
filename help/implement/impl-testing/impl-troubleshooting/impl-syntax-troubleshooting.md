---
description: Le tableau ci-dessous montre les erreurs de code courantes et le code correct.
keywords: Mise en œuvre d’Analytics
seo-description: Le tableau ci-dessous montre les erreurs de code courantes et le code correct.
seo-title: Erreurs de syntaxe courantes
solution: Analytics
subtopic: Résolution des problèmes
title: Erreurs de syntaxe courantes
topic: Développeur et mise en œuvre
uuid: 9845 dcb 9-9 f 10-4 f 65-a 43 d -2 af 41 edaa 122
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
