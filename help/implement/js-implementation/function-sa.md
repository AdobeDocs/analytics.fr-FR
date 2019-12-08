---
description: La fonction s.sa() vous permet de modifier, à tout moment, une suite de rapports de manière dynamique et ce, avant ou après le déclenchement de la demande d’image.
keywords: Analytics Implementation
subtopic: Functions
title: Fonction s.sa()
topic: Developer and implementation
uuid: a6aacd10-2a5b-448b-b3b7-bed5590b71d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fonction s.sa()

La fonction s.sa() vous permet de modifier, à tout moment, une suite de rapports de manière dynamique et ce, avant ou après le déclenchement de la demande d’image.

Si votre entreprise souhaite envoyer des données à différentes suites de rapport sans rechargement de page, il est vivement conseillé d’utiliser cette fonction.

Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.

## Propriétés d’une fonction {#section_E10CB41A0CF749F4A24C8377958E3671}

Cette fonction applique toutes les variables définies précédemment et permet de les utiliser dans une autre suite de rapports.

## Exemples de mise en œuvre {#section_14B0B8C853244D5F82B08B995773640C}

Envoi des données vidéo à une suite de rapports tout en envoyant les autres données à une autre suite :

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

Utilisation de la fonction s.sa() et du balisage multi-suite :

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

