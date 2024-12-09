---
description: Obtenez des réponses aux questions fréquentes sur les flux de données dans Adobe Analytics.
keywords: Flux de données;tâche; colonne « Pré »;colonne « Post »;sensible à la casse
title: FAQ sur les flux de données
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 0eef1b1269dcfbc7648127602bdfe24d4789f4b7
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 98%

---

# FAQ sur les flux de données

Questions fréquentes sur les flux de données.

## Les noms de flux doivent-ils être uniques ? {#unique}

Les noms de fichiers des flux de données se composent de l’identifiant de la suite de rapports et de la date. Si deux flux sont configurés avec le même identifiant de suite de rapports et la ou les mêmes dates, ils auront le même nom de fichier. Si ces deux flux sont diffusés au même endroit, un fichier remplacera l’autre. Pour éviter que cela ne se produise, vous ne pouvez pas créer de flux qui puisse potentiellement remplacer un flux existant situé au même endroit.

Lorsque vous essayez de créer un flux alors qu’un autre flux doté du même nom de fichier existe déjà, un message d’erreur s’affiche. Prenons les exemples de solution suivants :

* Modifier le chemin de diffusion
* Si possible, modifiez les dates
* Si possible, modifiez la suite de rapports

## Quand les données sont-elles traitées ? {#processed}

Avant de traiter des données horaires ou quotidiennes, les flux de données attendent que tous les accès concernés par la collecte de données au cours de la période (jour ou heure) aient été écrits dans un entrepôt de données. Ensuite, les flux de données collectent les données avec horodatages compris dans cette tranche horaire, les compressent et les envoient via FTP. Dans le cas des flux horaires, les fichiers sont généralement écrits dans Data Warehouse dans un délai de 15 à 30 minutes, mais aucune période horaire n’est définie. En l’absence de données avec horodatages compris dans cette tranche horaire, le processus fait une nouvelle tentative avec la période suivante. Le processus de flux de données en cours utilise le champ `date_time` pour déterminer les accès qui appartiennent à la période d’une heure. Ce champ est basé sur le fuseau horaire de la suite de rapports.

## Quelle est la différence entre les colonnes comportant un préfixe `post_` et celle ne comportant pas de préfixe `post_` ? {#post}

Les colonnes sans le préfixe `post_` contiennent les données telles qu’elles ont été envoyées lors de la collecte de données. Les colonnes comportant le préfixe `post_` contiennent la valeur après traitement. La persistance de la variable, les règles de traitement, les règles VISTA, la conversion de la devise ou une autre logique côté serveur sont des exemples pouvant modifier une valeur appliqués par Adobe. Adobe recommande d’utiliser la version `post_` d’une colonne dans la mesure du possible.

Si une colonne ne contient pas de version `post_` (par exemple, `visit_num`), alors la colonne peut être considérée comme une colonne « Post ».

## Comment les flux de données gèrent-ils le respect de la casse ? {#case}

Dans Adobe Analytics, la plupart des variables sont considérées comme ne respectant pas la casse à des fins de création de rapports. Par exemple, les valeurs « neige », « Neige », « NEIGE » et « nEige » sont toutes considérées comme étant la même valeur. Le respect de la casse est préservé dans les flux de données.

Si vous observez différentes variations de la casse entre des colonnes « Post » et non « Post » (par exemple, « neige » dans la colonne « Pré » et « Neige » dans la colonne « Post »), cela signifie que votre implémentation utilise des valeurs à la fois en majuscules et en minuscules sur votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports.

## Les robots sont-ils filtrés par les règles de robots d’Admin Console incluses dans les flux de données ? {#bots}

Les flux de données n’incluent pas les robots filtrés par les [règles de robots d’Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html?lang=fr).

## Pourquoi est-ce que je vois plusieurs valeurs `000` dans la colonne de flux de données `event_list` ou `post_event_list` ? {#values}

Certains éditeurs de feuilles de calcul, en particulier Microsoft Excel, arrondissent automatiquement les grands nombres. La colonne `event_list` contient de nombreux nombres délimités par des virgules, ce qui peut parfois entraîner Excel à la traiter comme un grand nombre. Il arrondit les derniers chiffres à `000`.

Adobe recommande de ne pas ouvrir automatiquement les fichiers `hit_data.tsv` dans Microsoft Excel. Utilisez plutôt la boîte de dialogue Importer les données dʼExcel et assurez-vous que tous les champs sont traités comme du texte.

## Les colonnes telles que `hitid_high`, `hitid_low`, `visid_high` et `visid_low` sont-elles garanties comme étant uniques à lʼaccès ou à la visite ? {#hitid}

Dans la plupart des cas, la concaténation de `hitid_high` et `hitid_low` identifie de manière unique un accès. Le même concept sʼapplique à la concaténation de `visid_high` et `visid_low` pour les visites. Cependant, les anomalies de traitement peuvent rarement faire en sorte que deux accès partagent le même identifiant dʼaccès. Adobe recommande de ne pas créer de workflows de flux de données qui supposent de manière inflexible que chaque accès soit unique.

## Pourquoi des informations manquent-elles dans la colonne domaine pour certains opérateurs ? {#domain}

Certains opérateurs mobiles (tels que T-Mobile et O1) ne fournissent plus d’informations sur les domaines pour les recherches DNS inversées. Par conséquent, ces données ne sont pas disponibles dans les rapports sur les domaines.

## Pourquoi ne puis-je pas extraire des fichiers « Par heure » à partir de données qui ont plus de sept jours ? {#hourly}

Pour les données de plus de sept jours, les fichiers « Par heure » d’une journée sont combinés en un seul fichier « Quotidien ».

Exemple : un nouveau flux de données est créé le 9 mars 2021 et les données du 1er janvier 2021 au 9 mars sont diffusées « Par heure ». Cependant, les fichiers « Par heure » antérieurs au 2 mars 2021 sont combinés en un seul fichier « Quotidien ». Vous ne pouvez extraire des fichiers « Par heure » qu’à partir de données qui ont moins de sept jours à compter de la date de création. Dans ce cas-ci, du 2 au 9 mars.

## Quel est l’impact du passage à l’heure d’été sur les flux de données par heure ? {#dst}

Dans certains fuseaux horaires, l’heure change deux fois par an. Les flux de données respectent le fuseau horaire pour lequel la suite de rapports est configurée. Si le fuseau horaire configuré pour la suite de rapports n’applique pas l’heure d’été, la remise des fichiers se poursuit normalement. Si, en revanche, le passage à l’heure d’été est appliqué, la remise des fichiers est modifiée pour l’heure à laquelle le changement d’heure se produit (généralement à 02 h 00).

Lors d’un changement d’heure STD (heure standard) > DST (heure d’été) (« Bond en avant »), le client ne reçoit que 23 fichiers. L’heure qui est « sautée » au cours du changement d’heure est ignorée. Par exemple, si le changement d’heure est effectué à 02 h 00, le client reçoit un fichier pour 01 h 00 et un autre pour 03 h 00. Il n’y aura pas de fichier pour 02 h 00, étant donné qu’à 02 h 00 STD, il sera 03 h 00 DST.

Lors d’une transition DST > STD, (« Retour en arrière »), le client reçoit 24 fichiers. Cependant, l’heure de transition contient l’équivalent de 2 heures de données. Par exemple, si le changement d’heure a lieu à 02 h 00, le fichier correspondant à 01 h 00 est retardé d’une heure, mais il contient l’équivalent de 2 heures de données. Il contient les données entre 01 h 00 DST et 02 h 00 STD, qui aurait normalement été 03 h 00 DST. Le fichier suivant commence à 02 h 00 STD.

## Comment Analytics gère-t-il les erreurs de transfert FTP ? {#ftp-failure}

En cas d’échec d’un transfert FTP (en raison d’un refus de connexion, d’une perte de connexion, d’une erreur de quota ou d’un autre problème), Adobe tente de se connecter automatiquement et d’envoyer les données jusqu’à trois fois. Si le problème persiste, le flux est marqué comme ayant échoué et un message de notification est envoyé.

Si un transfert échoue, vous pouvez réexécuter une tâche jusqu’à ce qu’elle réussisse.

Si vous rencontrez des problèmes lors de l’affichage d’un flux de données sur votre site FTP, voir [Résolution des problèmes liés aux flux de données](troubleshooting.md).

## Comment puis-je renvoyer une tâche ? {#resend}

Une fois que vous avez vérifié ou corrigé le problème de diffusion, exécutez à nouveau la tâche pour obtenir les fichiers.

## Qu’est-ce que le paramètre BucketOwnerFullControl pour les flux de données Amazon S3 ? {#BucketOwnerFullControl}

**BucketOwnerFullControl** spécifie des droits entre comptes pour créer des objets dans d’autres compartiments.

Cas d’utilisation type d’Amazon S3 : le titulaire du compte AWS (Amazon Web Services) crée un compartiment, puis crée un utilisateur qui est autorisé à créer des objets dans ce compartiment, puis spécifie les informations d’identification pour cet utilisateur. Dans ce cas, les objets de l’utilisateur appartiennent au même compte et le titulaire du compte bénéficie implicitement du contrôle total de l’objet (lecture, suppression, etc). Ce processus fonctionne de la même manière que les remises par FTP.

AWS permet aussi de créer des objets dans un compartiment appartenant à un autre compte d’utilisateur. Par exemple, deux utilisateurs AWS (utilisateurA et utilisateurB) n’appartiennent pas au même compte AWS, mais souhaitent créer des objets dans d’autres compartiments. Si l’utilisateurA crée un compartiment (le compartimentA), il peut créer une politique de compartiment qui autorise explicitement l’utilisateurB à créer des objets dans le compartimentA, même si l’utilisateur n’est pas propriétaire du compartiment. Cette politique peut s’avérer avantageuse, car l’utilisateurA et l’utilisateurB n’ont pas à échanger d’informations d’identification. Au lieu de cela, l’utilisateurB fournit à l’utilisateurA son numéro de compte, puis l’utilisateurA crée une politique de compartiment qui autorise l’utilisateurB à créer des objets dans le compartimentA.

Cependant, les objets n’héritent pas des autorisations du compartiment parent. Si l’utilisateurB charge un objet dans le compartiment de l’utilisateurA, l’utilisateurB « détient » toujours cet objet et, par défaut, l’utilisateurA n’a aucune autorisation quant à cet objet, même si l’utilisateurA possède le compartiment. L’utilisateurB doit explicitement octroyer les droits à l’utilisateurA, car il reste le propriétaire de l’objet. Pour accorder cette autorisation, l’utilisateurB doit charger l’objet avec une liste de contrôle d’accès BucketOwnerFullControl, qui spécifie que le propriétaire du compartiment (utilisateurA) bénéficie de tous les droits sur l’objet (lecture, écriture, suppression, etc.), même si l’objet est « détenu » par l’utilisateurB.

>[!NOTE]
>
>Adobe Analytics ne détermine pas si le compartiment a une politique qui oblige à donner au propriétaire du compartiment le contrôle total des nouveaux objets, ou même si le propriétaire se trouve sur un compte différent de celui de l’utilisateur qui écrit les données. Au lieu de cela, Analytics ajoute automatiquement le propriétaire du compartiment à la liste de contrôle d’accès `BucketOwnerFullControl` avec chaque téléchargement de flux.

