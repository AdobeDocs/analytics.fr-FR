---
title: Débogueur Adobe Experience Cloud hérité
description: Installez le débogueur hérité Adobe Experience Cloud. Ce débogueur examine les balises pour Analytics, Target, Advertising Cloud, Identity Service, DTM et Launch.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Débogueur Adobe Experience Cloud hérité

> [!IMPORTANT] Cet outil de débogage n’est plus pris en charge. Adobe recommande plutôt d’utiliser l’extension [Chrome du débogueur Adobe Experience Cloud](https://docs.adobe.com/content/help/fr-FR/debugger/using/experience-cloud-debugger.html).

Le [!UICONTROL débogueur hérité] examine les balises pour la plupart des services Adobe Experience Cloud. L’utilisation du débogueur vous permet de voir quelles données sont envoyées à Adobe sur une page donnée de votre site. Vous pouvez utiliser ces informations pour dépanner ou valider la mise en œuvre de votre entreprise.

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

Si vous êtes sûr de ne pas vouloir utiliser l’[extension Chrome](https://docs.adobe.com/content/help/fr-FR/debugger/using/experience-cloud-debugger.html), le signet d’applet du débogueur hérité peut être utilisé à la place.

1. Cliquez sur les trois points en haut à droite, puis sélectionnez Signets > Gestionnaire de signets. Vous pouvez également appuyer sur `Ctrl` + `Shift` + `O` (Windows) ou `Cmd` + `Shift` + `O` (Mac).
2. Dans le coin supérieur droit du gestionnaire de signets, cliquez sur les trois points, puis cliquez sur Ajouter un nouveau signet.
3. Dans le champ Nom, étiquetez-le comme « Débogueur Adobe Experience Cloud », puis collez le fragment de code dans le champ URL.
4. Utilisez le gestionnaire de signets pour placer votre nouveau signet d’applet à l’emplacement souhaité.

#### Firefox

1. Cliquez sur les trois lignes en haut à droite, puis sélectionnez Bibliothèque > Signets > Afficher tous les signets. Vous pouvez également appuyer sur `Ctrl` + `Shift` + `B` (Windows) ou `Cmd` + `Shift` + `B` (Mac).
2. Cliquez sur Organiser > Nouveau signet.
3. Dans le champ Nom, étiquetez-le comme « Débogueur Adobe Experience Cloud », puis collez le fragment de code dans le champ Emplacement. Les champs Balises et Mot-clé ne sont pas obligatoires.
4. Utilisez la fenêtre de la bibliothèque pour placer votre nouveau signet d’applet à l’emplacement souhaité.

#### Edge

Edge ne permet pas de créer manuellement un signet d’applet, mais une URL de signet peut être modifiée dans un signet d’applet.

1. Cliquez sur l’icône en forme d’étoile sur le côté droit du champ URL pour mettre en signet la page active.
2. Nommez le signet « Adobe Experience Cloud Debugger », puis enregistrez-le à l’emplacement souhaité.
3. Cliquez sur l’icône en forme d’étoile avec des lignes pour ouvrir la barre Favoris.
4. Cliquez avec le bouton droit sur le signet que vous venez de créer, puis sélectionnez « Modifier l’URL ».
5. Collez le fragment de code dans le champ de texte, puis appuyez sur Entrée.

#### Safari

Safari ne peut pas créer manuellement un signet d’applet, mais une URL de signet peut être modifiée dans un signet d’applet.

1. Cliquez sur l’icône Partager dans le coin supérieur droit, ce qui ouvre une fenêtre modale de signet.
2. Nommez le signet « Adobe Experience Cloud Debugger », puis enregistrez-le à l’emplacement souhaité.
3. Cliquez sur Signets > Modifier les signets, puis recherchez le signet nouvellement créé.
4. Cliquez avec le bouton droit de la souris > Modifier l’adresse, puis collez le fragment de code dans le champ de texte.

## Utilisation du débogueur hérité

Accédez à la page de votre site, puis cliquez sur le signet d’applet. Une fenêtre contextuelle s’affiche avec les données envoyées à Adobe.

> [!NOTE] Certains plug-ins de blocage des publicités et bloqueurs de fenêtres contextuelles peuvent interférer avec le chargement de la fenêtre du débogueur. Recherchez les fenêtres contextuelles bloquées dans votre navigateur et autorisez-les à fonctionner correctement pour le débogueur.

Le débogueur dispose de plusieurs options, qui personnalisent toutes le mode d’affichage des données. Aucune de ces options n’affecte la collecte de données.

* **Produits Experience Cloud affichés :** affiche ou masque les demandes d’image pour chaque produit Experience Cloud correspondant.
* **Décodage d’URL :** l’URL décode la demande d’image afin de correspondre à ce qui est affiché dans les rapports. Adobe recommande de laisser cette case cochée.
* **Actualisation automatique :** actualise automatiquement la fenêtre contextuelle toutes les quelques secondes pour rechercher d’autres demandes d’image sur la page. Si vous devez copier/coller du contenu dans le débogueur, désactivez l’actualisation automatique afin que votre sélection se maintienne.
* **Format convivial :** active/désactive le format d’affichage entre les libellés utiles et les chaînes de requête brutes dans une demande d’image. Voir [Paramètres de requête de la collecte de données](query-parameters.md) pour plus d’informations.

Pour enregistrer les options d’affichage par défaut du débogueur, cliquez avec le bouton droit sur le lien « Adobe Debugger » dans le coin supérieur droit, puis copiez l’adresse du lien. Modifiez le signet d’applet du débogueur actuel et collez le fragment de code mis à jour dans le champ URL.
