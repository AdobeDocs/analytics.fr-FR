---
description: Avant de créer des suites de rapports virtuelles, vous devez tenir compte des quelques points suivants.
keywords: Suite de rapports virtuelle
title: Création des suites de rapports virtuelles
feature: Reports & Analytics Basics & Analytics Basics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 98%

---

# Création des suites de rapports virtuelles

Avant de créer des suites de rapports virtuelles, vous devez tenir compte des quelques points suivants.

* Les utilisateurs qui ne sont pas administrateurs ne peuvent pas visualiser le Gestionnaire de suites de rapports virtuelles.
* Les suites de rapports virtuelles ne peuvent pas être partagées. Le « partage » est effectué par le biais de groupes/autorisations.
* Dans le Gestionnaire de suites de rapports virtuelles, vous ne pouvez afficher que vos propres suites de rapports virtuelles. Vous devez cliquer sur « Tout afficher » pour afficher les suites de rapports virtuelles des autres utilisateurs.

1. Accédez à **[!UICONTROL Composants]** > **[!UICONTROL Suites de rapports virtuelles]**.
1. Cliquez sur **[!UICONTROL Ajouter +]**.

   ![](assets/new_vrs.png)

1. Renseignez les champs suivants :

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> <p>Le nom de la suite de rapports virtuelle n’est pas hérité de la suite de rapports parente et doit être distinct. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Description </td> 
   <td colname="col2"> <p>Ajoutez une description précise pour les utilisateurs d’entreprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Balises </td> 
   <td colname="col2"> <p>Vous pouvez ajouter des balises pour organiser vos suites de rapports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupes </td> 
   <td colname="col2"> <p>Sélectionnez les groupes d’autorisations qui doivent avoir accès à une suite de rapports virtuelle donnée. (Vous pouvez également gérer les autorisations de groupe sous <span class="ignoretag"><span class="uicontrol">Administration</span> &gt; <span class="uicontrol">Gestion utilisateur</span> &gt; <span class="uicontrol">Groupes</span></span>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suite de rapports parente </td> 
   <td colname="col2"> <p>Suite de rapports à partir de laquelle cette suite de rapports virtuelle hérite des paramètres suivants. La plupart des niveaux de service et des fonctionnalités (par exemple, les paramètres eVar, les règles de traitement, les classifications, etc.) sont hérités. Pour apporter des modifications à ces paramètres hérités sur une suite de rapports virtuelle, vous devez modifier la suite de rapports parente (<span class="ignoretag"><span class="uicontrol">Administration</span> &gt; <span class="uicontrol">Suites de rapports</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuseau horaire </td> 
   <td colname="col2"> <p>Le choix d’un fuseau horaire est facultatif. </p> <p>Si vous choisissez un fuseau horaire, il est enregistré avec la suite de rapports virtuelle. Si aucun fuseau horaire n’est choisi, celui de la suite de rapports parente est utilisé. </p> <p>Lors de la modification d’une suite de rapports virtuelle, le fuseau horaire enregistré avec la suite de rapports virtuelle apparaît dans le sélecteur déroulant. Si la suite de rapports virtuelle a été créée avant l’ajout de la prise en charge du fuseau horaire, le fuseau horaire de la suite de rapports parente s’affiche dans la liste de sélection déroulante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segments </td> 
   <td colname="col2"> <p>Vous pouvez ajouter un seul segment ou <a href="https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-build.html"  >empiler des segments</a>. </p> <p> <p>Remarque : Lors de l’empilement de deux segments, ils sont associés par une instruction AND, qui ne peut pas être changée en instruction OR. </p> </p> <p>Lorsque vous essayez de supprimer ou de modifier un segment qui est actuellement utilisé dans une suite de rapports virtuelle, un avertissement s’affiche. </p> </td> 
  </tr> 
 </tbody> 
</table>
