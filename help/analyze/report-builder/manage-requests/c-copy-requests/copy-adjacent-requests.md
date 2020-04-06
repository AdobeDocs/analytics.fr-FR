---
description: De même que vous copiez et collez des requêtes, vous pouvez déplacer des requêtes dans la feuille de calcul en sélectionnant Couper la requête dans le menu contextuel.
title: Copie de requêtes adjacentes
topic: Report builder
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Copie de requêtes adjacentes

De même que vous copiez et collez des requêtes, vous pouvez déplacer des requêtes dans la feuille de calcul en sélectionnant Couper la requête dans le menu contextuel.

Cutting a request removes it from its original location and places it in the new location after you select [!UICONTROL Paste Request]. Si, après avoir coupé une requête, vous changez d’avis et décidez de copier ou couper une autre requête d’une autre cellule, le Report Builder laisse la première requête dans sa cellule d’origine et agit uniquement (copie ou coupe) sur la seconde.

>[!NOTE] Le Créateur de rapports ne prend pas en charge la fonction Annuler d’Excel lorsque vous coupez ou collez des requêtes. Soyez donc prudent lorsque vous coupez des requêtes.

Vous n’êtes pas limité à la copie et au collage dans la même feuille du classeur. Vous pouvez copier une requête dans une feuille et la coller dans une autre feuille du même classeur.

Vous n’êtes pas limité à la copie et au collage d’une requête à la fois. Vous pouvez sélectionner plusieurs requêtes dans la feuille de calcul et les coller dans une zone vide de la feuille de calcul. Tout comme pour copier et coller une requête, assurez-vous que la région de collage ne comporte aucune cellule avec des requêtes qui seront remplacées par l’opération de collage. If the system finds that the target paste region already contains one or more requests, report builder does not display the [!UICONTROL Paste Requests] menu for any copied or cut requests. Vous devez sélectionner une autre cellule comme destination de l’opération de collage afin que les requêtes ne se chevauchent pas.
