---
description: Adobe fournit quelques bonnes pratiques pour la mise à jour de votre code Analytics.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Remplacement de votre code Analytics
topic: Developer and implementation
uuid: d3ea6585-199f-4dbe-9ee8-15b204689f2f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Remplacement de votre code Analytics

Adobe fournit quelques bonnes pratiques pour la mise à jour de votre code Analytics.

Les clients utilisent fréquemment le [!UICONTROL gestionnaire de code] d’Adobe pour remplacer leur code par la version la plus récente. Cette méthode est conseillée si vous tenez compte de certains points.

## Utilisation de l’ID de serveur de collecte de données incorrect {#section_1726CEB1ABEC408492569B06664410C8}

Les fichiers [!DNL s_code.js] génériques qui n’ont pas été générés à partir du gestionnaire de code d’Adobe sont parfois envoyés à ceux qui implémentent le code sur votre site. L’ID de serveur de collecte de données incorrect (comme illustré dans la variable [!UICONTROL s.dc]) du compte est ainsi utilisé. Il est conseillé de générer le nouveau code directement à partir du [!UICONTROL gestionnaire de code] pour une suite de rapports spécifique plutôt que de réutiliser le code d’une autre suite de rapports. Il s’agit de la meilleure méthode pour s’assurer que la variable [!UICONTROL s.dc] est correctement renseignée.

## Modules externes {#section_53650E52D6A54A4795F95E491E7548D1}

Certains clients implémentent des modules externes pour améliorer leur expérience Adobe. Lorsque vous remplacez votre code, n’oubliez pas que les modules externes en font partie. Le code créé dans le [!UICONTROL gestionnaire de code] ne comporte pas le code des modules externes. Tous les modules externes doivent donc être migrés manuellement vers la nouvelle base de code. Effectuez une copie du code existant en cas de problème éventuel. Vous pourrez ainsi le restaurer si besoin.
