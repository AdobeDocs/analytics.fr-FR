---
description: Découvrez comment copier, coller et déplacer des requêtes vers une autre partie de la feuille de calcul.
title: Comment copier des requêtes adjacentes
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
feature: Report Builder
role: User, Admin
exl-id: 99476ec5-f1f0-49f5-a2d8-354cec63c6b1
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 59%

---

# Copie de requêtes adjacentes

{{legacy-arb}}

De même que vous copiez et collez des requêtes, vous pouvez déplacer des requêtes dans la feuille de calcul en sélectionnant [!UICONTROL Couper la requête] dans le menu contextuel.

Lorsque vous coupez une requête, elle est supprimée de son emplacement d’origine, puis placée à un nouvel emplacement après que vous avez sélectionné [!UICONTROL Coller la requête]. Si, après avoir coupé une requête, vous changez d’avis et décidez de copier ou couper une autre requête d’une autre cellule, le Report Builder laisse la première requête dans sa cellule d’origine et agit uniquement (copie ou coupe) sur la seconde.

>[!NOTE]
>
>Le Créateur de rapports ne prend pas en charge la commande Annuler d’Excel lorsque vous coupez ou collez des requêtes.

Vous n’êtes pas limité à la copie et au collage dans la même feuille du classeur. Vous pouvez copier une requête dans une feuille et la coller dans une autre feuille du même classeur.

Vous ne vous limitez pas à copier et coller une requête à la fois. Vous pouvez sélectionner plusieurs requêtes dans la feuille de calcul, puis les coller dans une région vide de la feuille de calcul. De même que lorsque vous copiez et collez une seule requête, veillez à ce que la région de collage ne contienne aucune cellule avec des requêtes, afin de ne pas remplacer ces dernières. Si le système détecte que la région de collage cible contient déjà une ou plusieurs requêtes, Report Builder n’affiche pas le menu [!UICONTROL Coller les requêtes] pour les requêtes copiées ou coupées. Vous devez sélectionner une autre cellule comme destination de l’opération de collage, de sorte que les requêtes ne se chevauchent pas.
