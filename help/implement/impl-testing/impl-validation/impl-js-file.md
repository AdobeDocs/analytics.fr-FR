---
description: Vérifiez que le fichier .JS est référencé correctement à partir de la page. Le chemin peut être spécifié soit sous une forme relative vers le document en cours, soit sous la forme d’un nom de chemin absolu.
keywords: Mise en œuvre d’Analytics
seo-description: Vérifiez que le fichier .JS est référencé correctement à partir de la page. Le chemin peut être spécifié soit sous une forme relative vers le document en cours, soit sous la forme d’un nom de chemin absolu.
seo-title: Fichier JS JavaScript
solution: Analytics
title: Fichier JS JavaScript
topic: Développeur et mise en œuvre
uuid: 6e83223f-2127-41d3-9806-bd085fa2a747
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Fichier JS JavaScript

Vérifiez que le fichier .JS est référencé correctement à partir de la page. Le chemin peut être spécifié soit sous une forme relative vers le document en cours, soit sous la forme d’un nom de chemin absolu.

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

Si certaines pages du site sont chargées dans un protocole sécurisé (https:) et font référence au fichier [!DNL AppMeasurement] pour JavaScript, assurez-vous que la référence au fichier est sécurisée (via https:) ou codez la référence comme illustré ci-dessous. Cet exemple adopte le protocole de la page en cours et évite l’affichage de l’avertissement « certains éléments ne sont pas sécurisés ».

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Assurez-vous que les autorisations du fichier [!DNL .JS] situé sur les serveurs web sont définies correctement, de sorte que le fichier puisse être téléchargé et exécuté par les visiteurs du site web. Si un fichier [!DNL .JS] différent est utilisé sur les serveurs de développement, définissez l’attribut « Lecture seule » pour le fichier [!DNL .JS] situé sur les serveurs de production afin d’éviter tout écrasement. En cas d’altération, assurez-vous que les paramètres suivants sont définis correctement dans la partie supérieure du fichier [!DNL .JS] :

```js
/************************** CONFIG SECTION **************************/
/* You may add or alter any code config here.                       */
/* Link Tracking Config */
s.trackDownloadLinks=false /* true for download tracking */
s.trackExternalLinks=false /* true for exit link tracking */
s.trackInlineStats=false /* true for ClickMap support */
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls"
s.linkInternalFilters="javascript:"
s.linkLeaveQueryString=false
s.linkTrackVars="None" 
s.linkTrackEvents="None"
```

Si « *`s_account`* » reçoit une valeur dans la partie supérieure du fichier [!DNL .JS], assurez-vous que l’ID de la suite de rapports (renseigné dans la variable [!UICONTROL s_account]) est correct. Veillez également à ce que le code de la page ne définisse pas l’[!UICONTROL ID de suite de rapports (variable ]*`s_account`*).

Examinez les variables et la demande d’image pour vous assurer que la « méthode de secours » (troisième partie du code « split » dans l’exemple ci-dessus) ne crée pas la demande d’image au lieu du fichier [!DNL .JS]. Vous pouvez le déterminer, dans la mesure où cette méthode crée uniquement une demande d’image contenant un minimum d’informations.
