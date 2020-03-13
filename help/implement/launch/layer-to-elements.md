---
description: valeur nulle
title: Mapper les objets de couche de données aux éléments de données
uuid: null
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Mapper les objets de couche de données aux éléments de données


Après avoir [créé une couche](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) de données pour votre implémentation, vous pouvez mapper des objets dans cette couche avec des éléments de [données dans Lancement](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element). Les éléments de données sont des blocs de création de votre carte de données qui peuvent être utilisés de plusieurs manières. Vous pouvez utiliser des éléments de données pour collecter, organiser et diffuser des données dans les solutions Adobe Platform, y compris vos rapports Analytics.

Pour mapper des objets de couche de données à des éléments de données de lancement :

1. Dans Lancer, cliquez sur le nom de la propriété à laquelle vous souhaitez ajouter l’élément de données. Si vous n’avez pas encore configuré de propriété, reportez-vous aux instructions de [création d’une propriété](https://docs.adobe.com/content/help/en/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch.html)de lancement.

2. Click **Data Elements** and then click **Create New Data Element**.

   ![créer un élément de données](assets/createelement.png)


3. Entrez un nom pour votre élément de données. Ce nom doit être une étiquette simple qui correspond à une variable JavaScript dans la couche de données dont vous souhaitez effectuer le suivi.

4. Pour Extension, sélectionnez **Core.** Cette extension comprend toutes les variables dont vous aurez besoin.

5. For **Data Element Type**, select **JavaScript Variable**. Entrez le nom **de la variable** JavaScript dans le champ approprié. Cela doit correspondre au nom exact de l’objet dans la couche de données JavaScript.

6. Dans le champ Valeur **** par défaut, entrez la valeur que vous souhaitez définir par défaut ou laissez-la vide, le cas échéant.

7. Selon vos pratiques, vous pouvez sélectionner les options pour forcer les valeurs en minuscules et appliquer du texte propre (le lancement applique l’espacement conventionnel).

8. Spécifiez la durée pendant laquelle vous souhaitez que les valeurs de magasin de lancement soient stockées pour le nouvel élément de données.

9. Cliquez sur **Enregistrer**.

L’exemple suivant montre un élément de données Nom de page dans Lancement créé pour la variable JavaScript ``pageName`` dans la couche de données :

![Spécifier un élément](assets/new_element.png)


Les objets de couche de données associés à des éléments de données vous permettent de les exploiter pour renseigner les variables Analytics. Pour plus d’informations, voir [Mappage des éléments de données aux variables](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)Analytics.
