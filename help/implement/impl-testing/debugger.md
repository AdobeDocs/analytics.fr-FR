---
description: Installez l’ancien débogueur Adobe Experience Cloud. Ce débogueur examine les balises pour Analytics, Target, Advertising Cloud, Identity Service, DTM et Launch.
seo-description: Installez l’ancien débogueur Adobe Experience Cloud. Ce débogueur examine les balises pour Analytics, Target, Advertising Cloud, Identity Service, DTM et Launch.
seo-title: Débogueur hérité d’Adobe Experience Cloud
title: Débogueur hérité d’Adobe Experience Cloud
translation-type: tm+mt
source-git-commit: 2ea071c4d4f675c74770396610219d405a07a0e1

---


# Débogueur hérité d’Adobe Experience Cloud

> [!IMPORTANT] Cet outil de débogage n’est plus conservé. Adobe recommande plutôt d’utiliser l’extension [Chrome du débogueur](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)Adobe Experience Cloud.

Le débogueur [!UICONTROL hérité] examine les balises pour la plupart des services Adobe Experience Cloud. L’utilisation du débogueur vous permet de voir quelles données sont envoyées à Adobe sur une page donnée de votre site. Vous pouvez utiliser ces informations pour dépanner ou valider l’implémentation de votre entreprise.

## Installation du débogueur hérité

Créez un signet d’applet JavaScript pour installer le débogueur.

### Étape 1 : Copie du code du signet d’applet

Copiez le code suivant dans le Presse-papiers :

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Étape 2 : Coller le code du signet d’applet dans un signet

Chaque navigateur gère les signets de différentes manières, mais le concept est le même. Un signet est créé avec le nom souhaité et le code du signet d’applet comme URL.

#### Chrome

Si vous insistez pour ne pas utiliser l’extension [](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)chrome, le signet d’applet du débogueur hérité peut être utilisé à la place.

1. Cliquez sur les trois points en haut à droite, puis sélectionnez Signets &gt; Gestionnaire de signets. Vous pouvez également appuyer sur `Ctrl` + `Shift` + `O` (Windows) ou `Cmd` + `Shift` + `O` (Mac).
2. Dans le coin supérieur droit du gestionnaire de signets, cliquez sur les trois points, puis cliquez sur Ajouter un nouveau signet.
3. Dans le champ Nom, étiquetez-le comme "Débogueur Adobe Experience Cloud", puis collez le fragment de code dans le champ URL.
4. Utilisez le gestionnaire de signets pour placer votre nouveau signet d’applet à l’emplacement souhaité.

#### Firefox

1. Cliquez sur les trois lignes en haut à droite, puis sélectionnez Bibliothèque &gt; Signets &gt; Afficher tous les signets. Vous pouvez également appuyer sur `Ctrl` + `Shift` + `B` (Windows) ou `Cmd` + `Shift` + `B` (Mac).
2. Cliquez sur Organiser &gt; Nouveau signet.
3. Dans le champ Nom, étiquetez-le comme "Débogueur Adobe Experience Cloud", puis collez le fragment de code dans le champ Emplacement. Les champs Balises et Mot-clé ne sont pas obligatoires.
4. Utilisez la fenêtre de la bibliothèque pour placer votre nouveau signet d’applet à l’emplacement souhaité.

#### Edge

Edge ne permet pas de créer manuellement un signet d’applet, mais il est possible de modifier une URL de signet.

1. Cliquez sur l’icône en forme d’étoile sur le côté droit du champ URL pour mettre en signet la page active.
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. Click the star icon with lines to open the Favorites bar.
4. Right click the newly created bookmark, the select 'Edit URL'.
5. Paste the code snippet in the text field, then hit Enter.

#### Safari

Safari does not have the ability to manually create a bookmarklet, but a bookmark URL can be edited.

1. Click the Share icon in the top right, which opens a bookmark modal window.
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. Click Bookmarks &gt; Edit Bookmarks, and locate the newly created bookmark.
4. Right click &gt; Edit Address, then paste the code snippet into text field.

## Using the legacy debugger

To use the debugger, navigate to the desired page on your site, then click the bookmarklet. A pop-up window appears, showing data sent to Adobe.

> [!NOTE] Certain ad-blocking plug-ins and pop-up blockers can interfere with the loading of the debugger window. Check for blocked pop-ups in your browser, and allow them so the debugger can work correctly.

Le débogueur dispose de plusieurs options, qui personnalisent toutes le mode d’affichage des données. Aucune de ces options n’affecte la collecte de données.

* **** Displayed Experience Cloud products: Shows or hides image requests for each respective Experience Cloud product.
* **** Décodage d’URL : L’URL décode la demande d’image afin de correspondre à ce qui est affiché dans les rapports. Adobe recommande de laisser cette case cochée.
* **** Actualisation automatique : Actualise automatiquement la fenêtre contextuelle toutes les quelques secondes pour rechercher d’autres demandes d’image sur la page. Si vous devez copier/coller du contenu dans le débogueur, désactivez l’actualisation automatique afin que votre sélection reste.
* **** Format convivial : Active/désactive le format d’affichage entre les libellés utiles et les chaînes de requête brutes dans une demande d’image. Voir Paramètres [de requête de collecte de](../js-implementation/data-collection/query-parameters.md) données pour plus d’informations.

Pour enregistrer les options d’affichage par défaut du débogueur, cliquez avec le bouton droit sur le lien "Adobe Debugger" dans le coin supérieur droit, puis copiez l’adresse du lien. Modifiez le signet d’applet du débogueur actuel et collez le fragment de code mis à jour dans le champ URL.
