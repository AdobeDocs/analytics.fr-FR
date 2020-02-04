---
title: Suivi des courriers électroniques externes
description: Utilisez Adobe Analytics pour effectuer le suivi du contenu des courriers électroniques.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Suivi des courriers électroniques externes

Les sociétés utilisent Analytics pour déterminer le succès d’une campagne par courrier électronique.

[!DNL Analytics] peut générer des rapports sur les données d’analyse des campagnes par courrier électronique pour plusieurs mesures clés, parmi lesquelles :

| Mesure | Description |
|---|---|
| Clics publicitaires | Affiche le nombre de clics publicitaires suivis depuis le courrier électronique jusqu’à la page d’entrée. |
| Achats et/ou succès | Affiche le nombre d’achats suite au courrier électronique. |
| Commandes | Affiche le nombre de commandes effectuées suite au courrier électronique. |
| Recettes | Affiche le montant en dollars par visite généré à partir du courrier électronique. |
| Conversion | Affiche le nombre de pistes, d’inscriptions ou de tout autre événement de succès généré à partir du courrier électronique. |

Des modifications dans le corps du courrier électronique HTML et la bibliothèque JavaScript sont nécessaires pour capturer les mesures clés affichées ci-dessus.

## Mise en œuvre {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Plusieurs étapes successives permettent d’afficher les données d’analyse des campagnes par courrier électronique. Ces étapes sont décrites ci-dessous :

1. Créez des codes de suivi uniques.

   Les utilisateurs demandent souvent des recommandations pour le suivi de chaque campagne unique. C’est à eux de les déterminer en fonction de leurs besoins. Chaque utilisateur est différent. Adobe conseille à chaque utilisateur de générer des codes de suivi conviviaux, comme illustré dans l’exemple suivant :

   * sc_cid=A1123A321 > « A » correspond à campagne affiliée
   * sc_cid=EM033007 > « EM » correspond à campagne par courrier électronique
   * sc_cid=GG987123 > « GG » correspond à Google et il s’agit d’une campagne de recherche payante
   Pour obtenir des informations détaillées sur la configuration et l’utilisation des codes de suivi, contactez Adobe [!DNL Customer Care].

1. Ajoutez des paramètres de chaîne de requête à des liens de courriers électroniques HTML.

   Pour suivre les clics publicitaires émanant d’un utilisateur et les événements de succès ultérieurs, un paramètre de chaîne de requête doit être ajouté à chaque lien du courrier électronique HTML. Vous pouvez choisir de suivre chaque lien séparément ou de suivre tous les liens ensemble. Chaque lien peut comporter un code de suivi unique ou bien tous les liens peuvent partager un même code de suivi. Examinez l’hypothèse de l’insertion, dans un courrier électronique, du lien suivant vers un site Web.

   ```js
   <a href="https://www.example.com/index.asp">Visit our home page</a>
   ```

   Les paramètres de chaîne de requête suivants ?sc_cid=112233B doivent être ajoutés au lien ci-dessus :

   ```js
   <a href= "https://www.example.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Mettez à jour la bibliothèque JavaScript.

   La modification du code dans le fichier JavaScript, [!DNL s_code.js], permet de capturer le nombre (et la qualité) des utilisateurs qui ont cliqué sur le lien publicitaire du courrier électronique et ont participé aux événements de succès consécutifs. La mise à jour de la bibliothèque JavaScript comporte deux étapes.

   1. Personnalisez [!DNL s_code.js] en appelant [!UICONTROL getQueryParam].

      Le fichier [!DNL s_code.js] doit être placé à un emplacement du serveur Web accessible par chaque page Web. La fonction *`doPlugins`*de ce fichier doit être modifiée afin de lui permettre de capturer les paramètres de chaîne de requête des liens du courrier électronique. Par exemple :

      ```js
      /* Plugin Config */ 
      s.usePlugins=true 
      function s_doPlugins(s) { 
       /* Add calls to plugins here */ 
       // External Campaigns 
      s.campaign=s.getQueryParam('source') 
      } 
      s.doPlugins=s_doPlugins 
      ```

      Chaque paramètre de chaîne de requête devant être copié dans une variable doit comporter un appel [!UICONTROL getQueryParam]. Dans l’exemple ci-dessus, le paramètre de chaîne de requête [!UICONTROL sc_cid] est copié dans *`campaign`*.

      Seul le premier appel à [!UICONTROL getQueryParam] est nécessaire pour capturer les clics publicitaires. Contactez Adobe [!DNL Customer Care] pour implémenter cette fonction et pour vérifier que votre version du fichier JavaScript contient le plug-in [!UICONTROL getQueryParam].

   1. Vérifiez que les balises JavaScript « Code à coller » figurent sur toutes les pages d’entrée. Ce code à coller doit référencer la version du fichier [!DNL s_code.js] modifié dans la partie A.

      Il est important de garder en mémoire les points ci-après lors de la mise à jour de la bibliothèque JavaScript. Ces points sont énoncés ci-dessous.

      * Le paramètre de chaîne de requête [!UICONTROL sc_cid] doit être visible dans l’URL de la page d’entrée finale ; dans le cas contraire, aucune conversion de clic publicitaire ne sera enregistrée.
      * Le paramètre [!UICONTROL sc_cid] est un exemple de paramètre de chaîne de requête. Tout paramètre de chaîne de requête peut être utilisé et capturé par le module externe [!UICONTROL getQueryParam]. Assurez-vous que les paramètres de chaîne de requête ne sont utilisés que pour le suivi de campagne. Chaque fois que les paramètres figurent dans une chaîne de requête, leurs valeurs sont copiées dans *`campaign`*.

1. Utilisez [!UICONTROL SAINT] pour classifier les codes de suivi de campagne.

   L’[!UICONTROL outil de gestion des campagnes SAINT] peut être utilisé pour convertir les codes de suivi en noms conviviaux. Vous pouvez également l’utiliser pour résumer le taux de succès de chaque campagne par courrier électronique. L’étape 5 ci-dessous décrit le processus requis pour configurer une campagne par courrier électronique.

1. Affichez le cheminement par campagne par courrier électronique (facultatif).

   L’analyse du cheminement par campagne par courrier électronique est réalisée de manière similaire à l’analyse du cheminement par campagne d’un autre type. Vous pouvez utiliser une variable pour montrer le cheminement par campagne, comme l’expliquent les étapes suivantes :

   1. Contactez Adobe [!DNL Customer Care] au sujet de l’activation du cheminement pour une variable de [!UICONTROL trafic personnalisée] (prop).

   1. Sur toutes les pages, copiez le nom de la page dans la [!DNL s.prop] désignée.
   1. Sur la page d’entrée désignée par le courrier électronique, ajoutez le nom de la campagne par courrier électronique à la prop. Le résultat s’affiche sous la forme suivante :

      ```js
      s.prop1="Home Page : 123456"
      ```

      Lorsque le cheminement est activé pour la variable d’[!UICONTROL aperçu personnalisée], vous pouvez utiliser les rapports sur les [!UICONTROL chemins] (rapport [!UICONTROL Flux de page suivante] ou rapport sur les [!UICONTROL abandons], par exemple) pour afficher la navigation des visiteurs à partir de la page d’entrée.

