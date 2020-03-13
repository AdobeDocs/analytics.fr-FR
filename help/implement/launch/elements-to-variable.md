---
description: valeur nulle
title: Mappage des éléments de données aux variables Analytics
uuid: null
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# Mise en correspondance des éléments de données de lancement avec les variables Analytics


Après avoir [mappé les objets de couche de données sur Lancer les éléments](https://docs.adobe.com/content/help/en/analytics/implementation/layer-to-elements.md)de données, vous pouvez mapper les éléments de données sur les variables [](https://docs.adobe.com/content/help/en/analytics/implementation/vars/overview.html)Analytics.

Pour mapper les éléments de données de lancement aux variables Analytics :

1. Le cas échéant, affectez l’élément de données à une variable globale. Certains éléments de données, tels que le nom *de* page, s’appliquent à chaque page d’une propriété. Dans de tels cas, vous pouvez définir la variable globalement en procédant comme suit :

2. Dans Lancer, faites défiler l’écran vers le bas et cliquez sur Catalogue **des extensions**.

   ![Catalogue d’extensions](assets/extensions.png)

3. Cliquez sur **Configurer** sous Analytics.

   ![Extension Analytics](assets/configure.png)


4. Sous **eVars** dans les variables **** globales, sélectionnez l’ [eVar que vous avez configurée](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) pour être associée à la variable. Sélectionnez **Définir comme**, puis cliquez sur l’icône en forme de baril dans le champ le plus à droite pour spécifier l’élément de données.

   ![Spécifier une eVar](assets/evars.png)

5. Dans la fenêtre contextuelle **Sélectionner un élément** de données, sélectionnez l’élément de données à appliquer à la variable.

6. Cliquez sur **Enregistrer**.


Si l’élément de données n’est pas associé à une variable globale, vous pouvez également [créer une règle](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) qui affecte les éléments de données aux props ou aux evars.
