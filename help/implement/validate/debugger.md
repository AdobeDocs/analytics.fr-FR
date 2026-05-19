---
title: Débogueur hérité
description: Installez l’ancien débogueur. Ce débogueur examine les balises pour Analytics, Target, Advertising, Identity Service et la collecte de données.
feature: Implementation Basics
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/igbKBwN0NmXCPRi9Rc1UtG7Ty1ffpd0rwyWEOTWPWdk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 681
ht-degree: 75%

---

# Débogueur hérité

>[!IMPORTANT]
>
>Cet outil de débogage n’est plus pris en charge. Adobe recommande plutôt d’utiliser l’extension Chrome [Adobe CX Enterprise Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr).

Le débogueur [!UICONTROL hérité] inspecte les balises pour la plupart des services Adobe CX Enterprise. L’utilisation du débogueur vous permet de voir quelles données sont envoyées à Adobe sur une page donnée de votre site. Vous pouvez utiliser ces informations pour dépanner ou valider la mise en œuvre de votre entreprise.

## Installation du débogueur hérité

Créez un signet d’applet JavaScript pour installer le débogueur.

### Étape 1 : copier le code du signet d’applet

Copiez le code suivant dans votre Presse-papiers :

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Étape 2 : coller le code du signet d’applet dans un signet

Chaque navigateur gère les signets de différentes manières, mais le concept est le même. Un signet est créé avec le nom souhaité et le code du signet d’applet comme URL.

#### Chrome

Si vous êtes sûr de ne pas vouloir utiliser l’[extension Chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr), le signet d’applet du débogueur hérité peut être utilisé à la place.

1. Cliquez sur les trois points en haut à droite, puis sélectionnez Signets > Gestionnaire de signets. Vous pouvez également appuyer sur `Ctrl` + `Shift` + `O` (Windows) ou `Cmd` + `Shift` + `O` (Mac).
2. Dans le coin supérieur droit du gestionnaire de signets, cliquez sur les trois points, puis cliquez sur Ajouter un nouveau signet.
3. Dans le champ Nom, libellez-le « Débogueur hérité », puis collez le fragment de code dans le champ URL.
4. Utilisez le gestionnaire de signets pour placer votre nouveau signet d’applet à l’emplacement souhaité.

#### Firefox

1. Cliquez sur les trois lignes en haut à droite, puis sélectionnez Bibliothèque > Signets > Afficher tous les signets. Vous pouvez également appuyer sur `Ctrl` + `Shift` + `B` (Windows) ou `Cmd` + `Shift` + `B` (Mac).
2. Cliquez sur Organiser > Nouveau signet.
3. Dans le champ Nom, libellez-le « Débogueur hérité », puis collez le fragment de code dans le champ Emplacement . Les champs Balises et Mot-clé ne sont pas obligatoires.
4. Utilisez la fenêtre de la bibliothèque pour placer votre nouveau signet d’applet à l’emplacement souhaité.

#### Edge

Edge ne permet pas de créer manuellement un signet d’applet, mais une URL de signet peut être modifiée dans un signet d’applet.

1. Cliquez sur l’icône en forme d’étoile sur le côté droit du champ URL pour mettre en signet la page active.
2. Nommez le signet « Débogueur hérité » et enregistrez-le à l’emplacement souhaité.
3. Cliquez sur l’icône en forme d’étoile avec des lignes pour ouvrir la barre Favoris.
4. Cliquez avec le bouton droit sur le signet que vous venez de créer, puis sélectionnez « Modifier l’URL ».
5. Collez le fragment de code dans le champ de texte, puis appuyez sur Entrée.

#### Safari

Safari ne peut pas créer manuellement un signet d’applet, mais une URL de signet peut être modifiée dans un signet d’applet.

1. Cliquez sur l’icône Partager dans le coin supérieur droit, ce qui ouvre une fenêtre modale de signet.
2. Nommez le signet « Débogueur hérité » et enregistrez-le à l’emplacement souhaité.
3. Cliquez sur Signets > Modifier les signets, puis recherchez le signet nouvellement créé.
4. Cliquez avec le bouton droit de la souris > Modifier l’adresse, puis collez le fragment de code dans le champ de texte.

## Utilisation du débogueur hérité

Accédez à la page de votre site, puis cliquez sur le signet d’applet. Une fenêtre pop-up s’affiche avec les données envoyées à Adobe.

>[!NOTE]
>
>Certains plug-ins de blocage des publicités et bloqueurs de pop-ups peuvent interférer avec le chargement de la fenêtre du débogueur. Recherchez les pop-ups bloqués dans votre navigateur et autorisez-les à fonctionner correctement pour le débogueur.

Le débogueur dispose de plusieurs options, qui personnalisent toutes le mode d’affichage des données. Aucune de ces options n’affecte la collecte de données.

* **[!UICONTROL Produits Experience Cloud affichés]** : affiche ou masque les demandes d’image pour chaque produit CX Enterprise correspondant.
* **[!UICONTROL Décodage d’URL]** : l’URL décode la demande d’image pour qu’elle corresponde à ce qui est affiché dans les rapports. Adobe recommande de laisser cette case cochée.
* **[!UICONTROL Actualisation automatique]** : actualise automatiquement le pop-up toutes les quelques secondes pour vérifier si d’autres demandes d’image apparaissent sur la page. Si vous devez copier/coller du contenu dans le débogueur, désactivez l’actualisation automatique afin que votre sélection se maintienne.
* **[!UICONTROL Format convivial]** : permet d’activer ou de désactiver le format d’affichage des libellés utiles et des chaînes de requête brutes dans une demande d’image. Voir [Paramètres de requête de la collecte de données](query-parameters.md) pour plus d’informations.

Pour enregistrer les options d’affichage par défaut du débogueur, cliquez avec le bouton droit sur le lien « Adobe Debugger » dans le coin supérieur droit, puis copiez l’adresse du lien. Modifiez le signet d’applet du débogueur actuel et collez le fragment de code mis à jour dans le champ URL.
