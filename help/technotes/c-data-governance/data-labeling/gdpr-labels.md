---
description: Exemples de libellés relatifs à la confidentialité des données pour les variables Adobe Analytics
title: Étiquettes relatives à la confidentialité des données pour les variables Analytics
feature: Data Governance
exl-id: b8c2143a-6e8e-465a-979b-aa8176e8d4e8
source-git-commit: 1ca7040156f7f2105a9625f921de3d90b4175056
workflow-type: tm+mt
source-wordcount: '3585'
ht-degree: 78%

---

# Étiquettes relatives à la confidentialité des données pour les variables Analytics

## Pourquoi étiqueter vos données ? {#why-label}

Les clients d’Adobe, en tant que contrôleurs des données, sont chargés de se conformer aux lois applicables sur la Confidentialité des données, telles que le RGPD et le CCPA. Les clients doivent consulter leurs propres équipes juridiques pour déterminer comment leurs données doivent être traitées conformément aux lois sur la confidentialité des données. Adobe sait que chacun de ses clients a des besoins uniques en matière de confidentialité, raison pour laquelle Adobe permet à ses clients de personnaliser les paramètres souhaités pour le traitement des données en vertu de la Confidentialité des données. Cela permet à chaque client unique de traiter les demandes relatives à la Confidentialité des données de la façon qui convient le mieux à sa marque et à son ensemble de données unique.

Adobe Analytics offre des outils d’étiquetage des données en fonction de leur confidentialité et des restrictions contractuelles. Les libellés constituent une étape importante pour : (1) l’identification des sujets des données, (2) la détermination des données à renvoyer dans le cadre d’une demande d’accès et (3) l’identification des champs de données qui doivent être supprimés dans le cadre d’une demande de suppression.

Avant de pouvoir déterminer quelles étiquettes doivent être appliquées à tel ou tel champ/variable, vous devez [comprendre les ID](/help/technotes/c-data-governance/data-labeling/gdpr-analytics-ids.md) que vous capturez dans vos données Analytics et définir ceux qui seront utilisés pour les demandes relatives à la Confidentialité des données.

La mise en œuvre de la Confidentialité des données pour Adobe Analytics prend en charge les étiquettes suivantes pour les données d’identification, les données sensibles et la gouvernance des données.

## Étiquettes de données d’identification {#identity-data-labels}

Les étiquettes « I » pour les données d’identification sont utilisées pour classer les données qui peuvent servir à identifier ou à contacter une personne spécifique.

| Étiquette | Définition | Autres exigences |
| --- | --- | --- |
| I1 | Directement identifiables : données qui peuvent spécifiquement identifier ou permettre un contact direct avec un individu, comme un nom ou une adresse e-mail. | <ul><li>Ne peut pas être défini sur des événements</li><li>Ne peut pas être défini sur des eVars de marchandisage</li></ul> |
| I2 | Indirectement identifiables : données qui peuvent être utilisées en combinaison avec d’autres données pour identifier ou permettre un contact direct avec un individu ou un appareil. Ne permettent pas l’identification d’un individu en soi, mais peuvent être combinées avec d’autres informations (qui peuvent être ou non en votre possession), pour identifier une personne. Parmi les exemples on retrouve les numéros de fidélité des clients, ou les ID uniques à chaque client utilisés par le système de gestion de la relation client d’une entreprise. | <ul><li>Ne peut pas être défini sur des événements</li><li>Ne peut pas être défini sur des eVars de marchandisage</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Étiquettes de données sensibles {#sensitive-data-labels}

Les étiquettes « S » pour les données sensibles sont utilisées pour classer les données sensibles telles que les données géographiques. D’autres étiquettes de données sensibles seront introduites à l’avenir pour identifier d’autres types d’informations sensibles.

| Étiquette | Définition |
| --- | --- |
| S1 | Données de géolocalisation précises liées à la latitude et à la longitude pouvant être utilisées pour déterminer la position exacte d’un appareil (à moins de 100 m). |
| S2 | Données de géolocalisation pouvant être utilisées pour déterminer une zone géographie délimitée définie plus largement. |

{style=&quot;table-layout:auto&quot;}

## Étiquettes de gouvernance des données (Confidentialité des données) {#data-governance-labels}

Les étiquettes de gouvernance des données permettent aux utilisateurs de classer les données en fonction des considérations liées à la confidentialité et des conditions contractuelles afin d’aider les clients d’Adobe à rester conformes aux réglementations et aux politiques d’entreprise.

### Libellés d’accès à la confidentialité des données

| Étiquette | Définition | Autres exigences |
| --- | --- | --- |
| Aucun | Sélectionnez cette option si cette variable ne contient pas de données qui doivent être incluses dans les données renvoyées au titulaire de données dans le cadre d’une demande d’accès relative à la Confidentialité des données. |  |
| ACC-ALL | Les valeurs dans ce champ doivent être incluses dans toutes les demandes d’accès relatives à la Confidentialité des données. Si cet accès provient d’un appareil partagé par plusieurs individus, en appliquant cette étiquette, vous indiquez, en tant que contrôleur de données, qu’il est acceptable de partager les données dans ce champ avec tout individu ayant accès à l’appareil partagé. | Les champs ayant cette étiquette seront renvoyés pour toutes les demandes relatives à la Confidentialité des données. |
| ACC-PERSON | Les valeurs de ce champ ne doivent être incluses que pour les demandes d’accès relatives à la Confidentialité des données lorsque vous êtes raisonnablement certain que l’accès provient du titulaire de données, tel que déterminé par un ID de demande relative à la Confidentialité des données correspondant à la valeur d’un champ ID-PERSON. | Vous devez également définir une étiquette ID-PERSON sur certaines variables de cette suite de rapports et soumettre les demandes utilisant cet ID, ou cette étiquette ne sera jamais appliquée. |

{style=&quot;table-layout:auto&quot;}

Peu de variables recevront d’autres étiquettes, vous devez donc vous attendre à ce que les étiquettes d’accès soient appliquées à la plupart de vos variables. Cependant, c’est à vous, en consultation avec votre équipe juridique, de décider quelles données vous avez collectées doivent être partagées avec les titulaires de données.

### Étiquettes de suppression de la confidentialité des données

Contrairement aux autres étiquettes, les étiquettes de suppression ne sont pas mutuellement exclusives. Vous pouvez sélectionner l’une ou l’autre, les deux ou aucune. L’étiquette [!UICONTROL Aucune] n’est pas nécessaire, car le simple fait de ne pas cocher d’option de suppression indique qu’il n’y en a [!UICONTROL Aucune].

Une étiquette de suppression n’est requise que pour les champs qui contiennent une valeur permettant d’associer un accès au titulaire de données (c.-à-d. qui permettrait d’identifier le titulaire de données). Les autres informations personnelles (favoris, historique de navigation/d’achat, états de santé, etc.) ne doit pas être supprimé, car l&#39;association avec le titulaire de données sera rompue.

| Étiquette | Définition | Autres exigences |
| --- | --- | --- |
| DEL-DEVICE | Pour les requêtes de suppression relatives à la Confidentialité des données, les valeurs de ce champ ne doivent être rendues anonymes que pour les requêtes où l’accès présente un ID-DEVICE spécifié. Si la même valeur apparaît sur d’autres accès qui ne sont pas supprimés, alors ces autres instances ne seront pas modifiées. Cela aura pour effet de modifier les chiffres pour les rapports qui calculent des chiffres uniques dans ce champ. Sur les appareils partagés, cela peut supprimer les identifiants d’autres individus, au-delà du sujet des données.  Les chiffres ne changent pas si ce champ détient également une étiquette ID-DEVICE et si la valeur de ce champ a été utilisée comme ID pour la demande relative à la Confidentialité des données. | <ul><li>Nécessite également une étiquette I1, I2 ou S1</li><li>Ne peut pas être défini sur des événements</li><li>Ne peut pas être défini sur des eVars de marchandisage</li></li><li>Ne peut pas être défini sur des classifications</li><li>Vous devez soumettre les demandes utilisant une étiquette ID-DEVICE ou dont la valeur expandIDs est définie sur « true », ou cette étiquette ne sera jamais appliquée.</li></ul> |
| DEL-PERSON | Pour les requêtes de suppression relatives à la Confidentialité des données, les valeurs de ce champ ne doivent être rendues anonymes que pour les requêtes où l’accès présente un ID-PERSON spécifié. Si la même valeur apparaît sur d’autres accès qui ne sont pas supprimés, alors ces autres valeurs ne seront pas modifiées. Les chiffres seront alors modifiés pour les rapports qui calculent des comptes uniques sur ce champ. Les chiffres ne changeront pas si ce champ détient également une étiquette ID-PERSON et si la valeur de ce champ a été utilisée comme ID pour la demande relative à la Confidentialité des données. | <ul><li>Nécessite également une étiquette I1, I2 ou S1</li><li>Ne peut pas être défini sur des événements</li><li>Ne peut pas être défini sur des eVars de marchandisage</li></li><li>Ne peut pas être défini sur des classifications</li><li>Vous devez également soumettre des requêtes utilisant une étiquette ID-PERSON sur certaines variables de cette suite de rapports et soumettre les requêtes utilisant cet ID, ou cette étiquette ne sera jamais appliquée.</li></ul> |

{style=&quot;table-layout:auto&quot;}

### Étiquettes Identité relative à la confidentialité des données

| Étiquette | Définition | Autres exigences |
| --- | --- | --- |
| Aucun | Cette variable ne contient pas d’identifiant pouvant servir dans le cadre des demandes d’accès relatives à la Confidentialité des données. | Vous ne devez définir une de ces autres étiquettes que si ce champ contient un ID que vous utiliserez pour soumettre des demandes d’accès ou de suppression via l’[API Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=fr) ou l’interface utilisateur. |
| ID-DEVICE | Ce champ contient un ID qui peut être utilisé afin d’identifier un appareil pour une demande relative à la Confidentialité des données, mais ne peut pas distinguer les différents utilisateurs d’un appareil partagé. Vous ne devez pas spécifier cette étiquette pour toutes les variables contenant des identifiants (les étiquettes I1/I2 servent à cela). Utilisez cette étiquette si vous soumettez des demandes relatives à la Confidentialité des données qui utilisent des identifiants stockés dans cette variable et que vous voulez rechercher cette variable pour l’identifiant spécifié. | Nécessite également une étiquette I1 ou I2.<ul><li>Ne peut pas être défini sur des événements</li><li>Ne peut pas être défini sur des eVars de marchandisage</li><li>Ne peut pas être défini sur des classifications</li></ul> |
| ID-PERSON | Ce champ contient un ID qui peut être utilisé pour identifier un utilisateur authentifié (une personne spécifique) pour une demande relative à la Confidentialité des données. Vous ne devez pas spécifier cette étiquette pour toutes les variables contenant des identifiants (les étiquettes I1/I2 servent à cela). Utilisez cette étiquette si vous soumettez des demandes relatives à la Confidentialité des données qui utilisent des identifiants stockés dans cette variable et que vous voulez rechercher cette variable pour l’identifiant spécifié. | <ul><li>Nécessite également une étiquette I1 ou I2.</li><li>Ne peut pas être défini sur des événements</li><li>Ne peut pas être défini sur des eVars de marchandisage</li><li>Ne peut pas être défini sur des classifications</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Fournir un espace de noms lors de l’étiquetage d’une variable en tant qu’ID-DEVICE ou ID-PERSON {#provide-namespace}

Lorsque vous étiquetez une variable comme ID-DEVICE ou ID-PERSON, vous êtes invité à fournir un espace de noms. Vous pouvez utiliser un espace de noms défini précédemment ou en définir un nouveau.

### Utiliser un espace de noms défini précédemment

Si vous aviez précédemment défini une étiquette d’identification pour d’autres variables dans des suites de rapports de votre société de connexion, vous pouvez sélectionner un espace de noms existant. Vous devez réutiliser l’espace de noms si cette variable contient le même type d’ID que les autres variables déjà étiquetées avec cet espace de noms et que vous souhaitez toutes les rechercher lorsque vous soumettez une demande.

1. Cliquez sur **[!UICONTROL Sélectionner un espace de noms]**, puis sélectionnez un espace de noms existant.
1. Cliquez sur **[!UICONTROL Appliquer]**.

![](assets/namespace.png)

### Définir un nouvel espace de noms

Vous pouvez également définir un nouvel espace de noms. Nous vous recommandons de limiter les chaînes d’espace de noms à des caractères alphanumériques, plus le trait de soulignement, la barre oblique et l’espace. Ceux-ci seront tous convertis en minuscules.

1. Cliquez sur **[!UICONTROL Sélectionner un espace de noms]**, puis tapez le titre de l’espace de noms.

   ![](assets/namespace2.png)

1. Appuyez sur **[!UICONTROL Entrée]** pour ajouter cet espace de noms. Le bouton Appliquer devient alors actif.
1. Cliquez sur **[!UICONTROL Appliquer]**.

La chaîne que vous spécifiez comme espace de noms est la même que celle que vous devez utiliser pour soumettre des demandes via l’API relative à la Confidentialité des données comme valeur du paramètre « espace de noms ». La requête entraîne ensuite Adobe Analytics à rechercher toutes les variables de toutes vos suites de rapports qui partagent cet espace de noms pour l’identifiant que vous avez spécifié avec la requête.

Vous ne devez pas spécifier l’étiquette ID-DEVICE ou ID-PERSON sur toutes les variables contenant des ID (les étiquettes I1/I2 servent à cela). Utilisez cette étiquette si vous allez soumettre des demandes relatives à la Confidentialité des données qui utilisent des identifiants stockés dans cette variable et que vous voulez rechercher cette variable pour l’identifiant spécifié. Par exemple, si eVar1 peut contenir une adresse e-mail, et eVar2 un nom d’utilisateur de connexion, mais que vous soumettrez uniquement des demandes avec le nom d’utilisateur, vous pouvez alors étiqueter eVar1 comme I1, ACC-PERSON, DEL-PERSON, et eVar2 comme I2, ACC-PERSON, DEL-PERSON, ID-PERSON avec l’espace de noms « nom d’utilisateur ». Vous pouvez ensuite soumettre une demande avec un bloc JSON de section utilisateur comme suit :

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

Le même espace de noms peut être utilisé pour différentes variables d’une même suite de rapports. Par exemple, certaines implémentations personnalisées stockent un ID de gestion de la relation client dans une prop et une eVar. Si l’identifiant CRM apparaît toujours dans l’un d’eux (comme l’eVar) et seulement occasionnellement dans l’autre (la prop), et jamais dans la prop lorsque ce n’est pas également le cas en eVar, alors seul l’eVar a besoin d’un libellé d’identifiant et d’un espace de noms car l’Adobe ne peut rechercher l’identifiant que dans cet eVar. Toutefois, si l’ID de gestion de la relation client apparaît tantôt dans une variable, tantôt dans l’autre, les deux doivent alors avoir le même espace de noms. Adobe recherchera dans les deux variables les occurrences de l’ID spécifié dans une demande relative à la Confidentialité des données avec cet espace de noms. Vous devez toujours attribuer des étiquettes DEL à toutes ces variables pour que la valeur soit rendue anonyme quel que soit son emplacement.

Autre exemple, vous pouvez avoir un ID de gestion de la relation client qui est parfois envoyé via eVar1, parfois via prop7. Vous avez ensuite une règle de traitement qui copie la valeur d’eVar1, le cas échéant, dans eVar3. Sinon, il copie la valeur de prop7 en eVar3. Dans ce scénario, eVar3 contiendra toujours l’ID de gestion de la relation client s’il est connu. Dès lors, seule eVar3 nécessite une étiquette ID-PERSON.

>[!CAUTION]
>
>Les espaces de noms « visitorId » et « customVisitorId » sont réservés à l’identification du cookie de suivi hérité d’Analytics et de l’identifiant visiteur du client Analytics. N’utilisez pas ces espaces de noms pour les variables de trafic ou de conversion personnalisées.

## Les types de variables et les étiquettes de Confidentialité des données pris en charge {#variable-types}

L’étiquetage relatif à la confidentialité des données affecte quatre grandes catégories de variables Analytics. Toutes les variables ne prennent pas en charge toutes les étiquettes. Ce tableau indique les variables qui prennent en charge ou ne prennent pas en charge les étiquettes.

| Type de variable | Étiquettes prises en charge | Étiquettes non prises en charge |
|--- |--- |--- |
| <ul><li>Succès personnalisées</li><li>eVars de marchandisage</li><li>Variables à plusieurs valeurs (mvVars)</li><li>Variables de hiérarchie</li></ul> | <ul><li>S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>I1/I2</li>  <li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| Classifications | <ul><li>I1/I2, S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| <ul><li>Variables de trafic (props)</li><li>Variables de commerce (eVars de non-marchandisage)</li></ul> | Toutes les étiquettes | - |
| La plupart des autres variables    (*Voir le tableau ci-dessous pour les exceptions*) | ACC-ALL, ACC-PERSON | <ul><li>I1/I2, S1/S2</li><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON)</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Variables auxquelles des étiquettes autres que ACC-ALL/ACC-PERSON peuvent être attribuées/modifiées {#variables}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Groupe </th> 
   <th colname="col2" class="entry"> Variables </th> 
   <th colname="col3" class="entry"> Étiquettes modifiables </th> 
   <th colname="col4" class="entry"> Commenter </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">Dimensions de conversion </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">Dimensions de trafic personnalisées </li> 
    </ul> </td> 
   <td colname="col2"> <p>Toutes, sauf les classifications </p> </td> 
   <td colname="col3"> <p>Toutes </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Classifications </p> </td> 
   <td colname="col3"> <p>Aucune/I1/I2 </p> <p>Aucune/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Événements de conversion </p> </td> 
   <td colname="col2"> <p>Tous </p> </td> 
   <td colname="col3"> <p>Aucune/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensions et événements relatifs aux solutions </p> </td> 
   <td colname="col2"> <p>Lien d’Activity Map, </p> <p>Activity Map   Page </p> </td> 
   <td colname="col3"> <p>Aucune/I1/I2 </p> <p>Aucune/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Les variables peuvent contenir des paramètres d’URL, qui peuvent inclure des données directement ou indirectement identifiables. Si votre mise en oeuvre ne collecte pas de données directement ou indirectement identifiables dans ces variables, elles n’ont pas besoin d’étiquettes d’identité ou de suppression. </p> <p>Notez que la suppression efface les paramètres d’URL, mais conserve l’URL de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensions de traitement des données </p> </td> 
   <td colname="col2"> <p>Identifiant visiteur personnalisé </p> </td> 
   <td colname="col3"> <p>ID-DEVICE/ID-PERSON </p> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Vous ne pouvez pas supprimer les étiquettes d’ID ou DEL (définies sur Aucune), mais vous pouvez les modifier en variantes DEVICE ou PERSON en fonction de votre implémentation d’identification personnalisée. </p> <p>Si vous n’utilisez pas l’identifiant visiteur personnalisé, le paramètre n’a pas d’importance. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">Dimensions standard </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">Dimensions de traitement des données </li> 
    </ul> </td> 
   <td colname="col2"> <p>Adresse IP </p> <p>Adresse IP 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Vous ne pouvez pas supprimer l’étiquette DEL, mais vous pouvez la modifier en DEL-DEVICE ou DEL-PERSON, ou les deux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Action ClickMap (héritée), </p> <p>Contexte ClickMap (hérité), </p> <p>Page, </p> <p>URL de la page, </p> <p>URL de la page d’accès originale, </p> <p>Référent, </p> <p>URL de la page de début de la visite </p> </td> 
   <td colname="col3"> <p>Aucune/I1/I2 </p> <p>Aucune/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Les variables peuvent contenir des paramètres d’URL, qui peuvent inclure des données directement ou indirectement identifiables. Si votre mise en oeuvre ne collecte pas de données directement ou indirectement identifiables dans ces variables, elles n’ont pas besoin d’étiquettes d’identité ou de suppression. </p> <p>Notez que la suppression efface les paramètres d’URL, mais conserve l’URL de base. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gestion des suppressions {#deletion}

La prise en charge par Adobe Analytics des demandes de suppression relatives à la Confidentialité des données est conçue pour minimiser l’impact sur la génération de rapports. Dans la plupart des cas, les mesures qui apparaissent dans les rapports ne devraient pas changer. Ainsi, un rapport antérieur exécuté avant la suppression relative à la Confidentialité des données restera le même une fois la suppression effectuée. Pour ce faire, dissociez complètement les données supprimées du titulaire de données, tout en laissant en place des données non identifiables afin que les valeurs rapportées restent cohérentes.

Le tableau suivant décrit comment différentes variables sont « supprimées ». Il ne s’agit pas d’une liste exhaustive.

| Variables | Méthode de suppression |
| --- | --- |
| <ul><li>Variables de trafic (props)</li><li>Variables de commerce (eVars)</li></ul> | La valeur existante est remplacée par une nouvelle valeur du formulaire « Data Privacy-356396D55C4F9C7AB3FBB2F2FA223482 », dans laquelle la valeur hexadécimale de 32 chiffres suivant le préfixe « Data Privacy » est un nombre pseudo-aléatoire de 128 octets au chiffrement fort.<p>Puisqu’elle est remplacée par une chaîne aléatoire, la valeur d’origine ne peut pas être retrouvée à partir de cette nouvelle valeur, tout comme il n’est pas possible d’obtenir la nouvelle valeur en connaissant la valeur d’origine. Pour une variable donnée, si la valeur identique à la valeur remplacée apparaît dans d’autres accès qui sont également supprimés dans le cadre de la même demande relative à la Confidentialité des données, toutes les instances de cette valeur sont remplacées par la même nouvelle valeur.<p>Si certaines instances d’une valeur sont remplacées par une demande de suppression et qu’une demande ultérieure supprime d’autres (nouvelles) instances de la valeur d’origine, la nouvelle valeur de remplacement sera différente de la valeur de remplacement d’origine. |
| Identifiant d’achat | La valeur existante est remplacée par une nouvelle valeur du formulaire « G-7588FCD8642718EC50 », dans laquelle les 18 caractères hexadécimaux suivant le préfixe « G- » sont les 18 caractères qui composent un nombre pseudo-aléatoire de 128 octets au chiffrement fort. Tous les commentaires qui s’appliquent à la suppression de variables de trafic et de commerce s’appliquent également ici.<p>L’identifiant d’achat est un identifiant de transaction dont le principal objectif est de s’assurer qu’un achat n’est pas crédité deux fois, par exemple quand quelqu’un rafraîchit la page de confirmation d’achat. L’identifiant en lui-même peut associer l’achat à une ligne de votre propre base de données, où l’achat est enregistré. Dans la plupart des cas, il n’est pas nécessaire de supprimer cet identifiant, il n’est donc pas supprimé par défaut.<p>Si vous êtes toujours en mesure de lier un achat à un utilisateur après la demande de suppression relative à la Confidentialité des données de vos propres données, vous pourriez avoir à supprimer ce champ pour que les données Analytics concernant ce visiteur ne puissent pas être reliées à l’acheteur. |
| Identifiant visiteur | La valeur est un entier relatif de 128 octets et est remplacée par une valeur pseudo-aléatoire de 128 octets au chiffrement fort. |
| <ul><li>MCID</li><li>Identifiant visiteur personnalisé</li><li>Adresse IP</li><li>Adresse IP 2 | La valeur est effacée (définie sur une chaîne vide ou sur 0 selon le type de variable). |
| <ul><li>Action ClickMap (héritée)</li><li>Contexte ClickMap (hérité)</li><li>Page</li><li>URL de la page</li><li>URL de la page d’accès originale</li><li>Référent</li><li>URL de la page de début de la visite</li></ul> | Les paramètres d’URL sont effacés/supprimés. Si la valeur ne ressemble pas à une URL, elle est effacée (définie sur une chaîne vide). |
| <ul><li>Latitude</li><li>Longitude</li></ul> | La précision est réduite au mieux à 1 km. |

{style=&quot;table-layout:auto&quot;}

## Variables qui peuvent ne pas prendre en charge les étiquettes de suppression prévues {#no-delete-support}

Cette section vise à clarifier les informations concernant les variables Analytics qui peuvent ne pas prendre en charge la suppression. Parfois, ces variables sont supprimées par des utilisateurs non-Analytics (tels que l’équipe juridique) qui ne comprennent pas le type de données contenu dans la variable et font des hypothèses basées sur le nom de la variable.

Il est important de comprendre le type de données contenu dans chaque variable avant de prendre une décision concernant l’étiquetage ou la suppression, et de ne pas s’appuyer uniquement sur le nom de la variable. Voici une liste de certaines de ces variables et des raisons pour lesquelles elles peuvent ne pas nécessiter de suppression, ou pourquoi elles peuvent ne pas nécessiter une étiquette de suppression spécifique :

| Variable | Commentaires |
| --- | --- |
| [!UICONTROL Nouvel identifiant visiteur] | Le nouvel identifiant visiteur est une valeur booléenne qui est vraie la première fois qu’un identifiant visiteur donné est détecté. Il n’est pas nécessaire de le supprimer une fois que l’identifiant visiteur est rendu anonyme. Après l’anonymisation, il correspond à la première fois que l’ID anonyme est détecté. |
| [!UICONTROL Code postal]<p>[!UICONTROL Code postal géo] | Les codes postaux ne sont définis que pour les accès provenant des États-Unis. Ils ne sont pas définis pour les accès provenant de l’UE. Même lorsqu&#39;ils sont définis, ils ne fournissent qu&#39;une vaste zone géographique qui rend difficile la ré-identification du titulaire de données. |
| [!UICONTROL Latitude géo]<p>[!UICONTROL Longitude géo] | Elles fournissent une localisation approximative dérivée de l’adresse IP. La précision est généralement similaire à celle du code postal, à une douzaine de kilomètres près de la localisation réelle. |
| [!UICONTROL Agent utilisateur] | L’agent utilisateur identifie la version du navigateur utilisé. |
| [!UICONTROL Identifiant utilisateur] | Spécifie la suite de rapports Analytics (sous forme de nombre) contenant les données. |
| [!UICONTROL Identifiant de suite de rapports] | Spécifie le nom de la suite de rapports Analytics contenant les données. |
| [!UICONTROL Identifiant visiteur]<p>[!UICONTROL MCID] / [!UICONTROL ECID] | Ces ID possèdent une étiquette DEL-DEVICE mais l’ajout de l’étiquette DEL-PERSON est impossible. Si vous définissez [!UICONTROL l’extension d’ID] pour chaque requête, ces ID sont automatiquement supprimés pour toutes les requêtes de suppression, y compris ceux utilisant une étiquette ID-PERSON.<p>Si vous n’utilisez pas l’extension d’ID, mais souhaitez que ces ID de cookies soient rendus anonymes sur les accès contenant un ID correspondant dans une prop ou une eVar, vous pouvez contourner cette limite d’étiquetage en étiquetant la prop ou l’eVar avec une étiquette ID-DEVICE, même si elle identifie en réalité une personne (toutes les étiquettes DEL-PERSON doivent également être changées en étiquettes DEL-DEVICE). Dans ce cas, dans la mesure où seules certaines instances de l’identifiant visiteur ou de l’ECID sont rendues anonymes, le nombre de visiteurs uniques change dans les rapports historiques. |
| [!UICONTROL ID AMO] | L’identifiant Adobe Advertising Cloud est une variable de solution qui possède une étiquette [!UICONTROL DEL-DEVICE] non modifiable. Il est renseigné à partir d’un cookie, comme le sont l’identifiant visiteur et le MCID. Il doit être supprimé des accès dès que ces autres identifiants sont supprimés. Consultez la description de ces variables pour de plus amples détails. |

{style=&quot;table-layout:auto&quot;}

## Champs de date pour les demandes d’accès {#access-requests}

Il existe cinq variables standard qui contiennent des horodatages :

| Horodatage | Définition |
| --- | --- |
| Heure d’accès UTC | Heure à laquelle Adobe Analytics a reçu l’accès. |
| Heure d’accès personnalisée UTC | Heure à laquelle l’accès s’est produit, qui peut être antérieure à celle à laquelle l’accès a été reçu pour certaines applications mobiles et autres implémentations. Par exemple, si aucune connexion réseau n’était disponible au moment où elle s’est produite, l’application peut retenir l’accès et l’envoyer dès qu’une connexion est disponible. |
| Date Heure | Même valeur que l’heure d’accès personnalisée UTC, mais dans le fuseau horaire de la suite de rapports, non GMT. |
| Heure du premier accès GMT | Heure d’accès personnalisée UTC du premier accès reçu pour la valeur identifiant visiteur de cet accès. |
| Heure de début de visite UTC | Heure d’accès personnalisée UTC du premier accès reçu pour la visite actuelle de cet identifiant visiteur. |

{style=&quot;table-layout:auto&quot;}

Le code permettant de générer les fichiers renvoyés lors des demandes d’accès relatives à la Confidentialité des données nécessite qu’au moins l’une des trois premières variables d’horodatage soit incluse dans la demande d’accès (et dispose d’une étiquette ACC s’appliquant au type de demande). Si aucune d’elles n’est incluse, l’heure d’accès personnalisée UTC sera traitée comme si elle possédait une étiquette ACC-ALL.

Le fichier CSV d’accès renvoyé lors des demandes d’accès relatives à la Confidentialité des données convertira les valeurs de ces champs pour passer d’horodatages au format Unix en champs date/heure au format AAAA-MM-JJ HH:MM:SS (par exemple, 2018-05-01 13:49:22). Dans le fichier de résumé HTML, ces valeurs d’horodatage seront tronquées pour n’inclure que la date (AAAA-MM-JJ), afin de réduire le nombre de valeurs uniques possibles pour ces champs.
