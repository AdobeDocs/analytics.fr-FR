---
description: Découvrez comment copier, coller et déplacer des requêtes vers une autre partie de la feuille de calcul.
title: Copie de requêtes adjacentes
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
feature: Report Builder
role: User, Admin
exl-id: 99476ec5-f1f0-49f5-a2d8-354cec63c6b1
TQID: https://experienceleague.adobe.com/q1uVTribovAk-NJRXuAjW-kUIQfpquEPIbbOM9W8UmY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 269
ht-degree: 24%

---

# Copie de requêtes adjacentes

{{legacy-arb}}

De la même manière que vous copiez et collez des demandes, vous pouvez également déplacer des demandes vers une autre partie de la feuille de calcul en sélectionnant [!UICONTROL Couper la demande] dans le menu contextuel.

Lorsque vous coupez une requête, elle est supprimée de son emplacement d’origine, puis placée à un nouvel emplacement après que vous avez sélectionné [!UICONTROL Coller la requête]. Si, après avoir coupé une requête, vous changez d’avis et décidez de copier ou couper une autre requête d’une autre cellule, le Report Builder laisse la première requête dans sa cellule d’origine et agit uniquement (copie ou coupe) sur la seconde.

>[!NOTE]
>
>Report Builder ne prend pas en charge la commande Annuler d’Excel pour couper ou coller des requêtes.

Vous ne pouvez pas vous limiter à copier et coller dans la même feuille du classeur. Vous pouvez copier une demande dans une feuille et la coller à un emplacement dans une autre feuille du même classeur.

Vous n’êtes pas limité à copier et coller une demande à la fois. Vous pouvez sélectionner plusieurs demandes dans la feuille de calcul et les coller dans une zone vide de la feuille de calcul. Comme pour la copie et le collage d’une requête, assurez-vous que la région de collage ne comporte aucune cellule avec des requêtes qui seront remplacées par l’opération de collage. Si le système trouve que la région de collage cible contient déjà une ou plusieurs requêtes, Report Builder n’affiche pas le menu [!UICONTROL Coller les requêtes] pour les requêtes copiées ou coupées. Vous devez sélectionner une autre cellule comme destination de l’opération de collage afin que les requêtes ne se chevauchent pas.
