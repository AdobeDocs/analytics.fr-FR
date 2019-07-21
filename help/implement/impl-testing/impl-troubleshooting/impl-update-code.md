---
description: Adobe fournit quelques bonnes pratiques pour la mise à jour de votre code Analytics.
keywords: Mise en œuvre d’Analytics
seo-description: Adobe fournit quelques bonnes pratiques pour la mise à jour de votre code Analytics.
seo-title: Remplacement du code Analytics
solution: Analytics
subtopic: Résolution des problèmes
title: Remplacement du code Analytics
topic: Développeur et mise en œuvre
uuid: d 3 ea 6585-199 f -4 dbe -9 ee 8-15 b 204689 f 2 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Remplacement du code Analytics

Adobe fournit quelques bonnes pratiques pour la mise à jour de votre code Analytics.

Les clients utilisent fréquemment le [!UICONTROL gestionnaire de code] d’Adobe pour remplacer leur code par la version la plus récente. Cette méthode est conseillée si vous tenez compte de certains points.

## Utilisation de l’ID de serveur de collecte de données incorrect {#section_1726CEB1ABEC408492569B06664410C8}

Les fichiers [!DNL s_code.js] génériques qui n’ont pas été générés à partir du gestionnaire de code d’Adobe sont parfois envoyés à ceux qui implémentent le code sur votre site. L’ID de serveur de collecte de données incorrect (comme illustré dans la variable [!UICONTROL s.dc]) du compte est ainsi utilisé. Il est conseillé de générer le nouveau code directement à partir du [!UICONTROL gestionnaire de code] pour une suite de rapports spécifique plutôt que de réutiliser le code d’une autre suite de rapports. Il s’agit de la meilleure méthode pour s’assurer que la variable [!UICONTROL s.dc] est correctement renseignée.

## Modules externes {#section_53650E52D6A54A4795F95E491E7548D1}

Certains clients implémentent des modules externes pour améliorer leur expérience Adobe. Lorsque vous remplacez votre code, n’oubliez pas que les modules externes en font partie. Le code créé dans le [!UICONTROL gestionnaire de code] ne comporte pas le code des modules externes. Tous les modules externes doivent donc être migrés manuellement vers la nouvelle base de code. Effectuez une copie du code existant en cas de problème éventuel. Vous pourrez ainsi le restaurer si besoin.
