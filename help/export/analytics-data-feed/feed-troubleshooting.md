---
description: Cette section comprend des informations sur les problèmes courants.
keywords: Data Feed;troubleshooting
solution: Analytics
title: Résolution des problèmes liés aux flux de données
uuid: 4be981ab-3a61-4099-9b0d-785d2ac2492a
translation-type: tm+mt
source-git-commit: c9b3471b138c2e056a5abadb4ace6bb4eccd1d72

---


# Résolution des problèmes liés aux flux de données

Cette section comprend des informations sur les problèmes courants.

## Erreur lors de l’enregistrement d’un flux {#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Les noms de fichiers des flux de données se composent de l’identifiant de la suite de rapports et de la date. Si deux flux sont configurés avec le même identifiant de suite de rapports et la ou les mêmes dates, ils auront le même nom de fichier. Si ces deux flux sont diffusés au même endroit, un fichier remplacera l’autre. Pour éviter que cela ne se produise, vous ne pouvez pas créer de flux qui puisse potentiellement remplacer un flux existant situé au même endroit.

Lorsque vous essayez de créer un flux alors qu’un autre flux doté du même nom de fichier existe déjà, le message suivant s’affiche :

Si cette erreur survient, considérez les solutions suivantes :

* Modifier le chemin de diffusion
* Si possible, modifier les dates
* Si possible, modifier la suite de rapports

## Paramètre BucketOwnerFullControl pour les flux de données Amazon S3 {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Cas d’utilisation type d’Amazon S3 : le titulaire du compte AWS (Amazon Web Services) crée un compartiment, puis crée un utilisateur qui est autorisé à créer des objets dans ce compartiment, puis spécifie les informations d’identification pour cet utilisateur. Dans ce cas, les objets de l’utilisateur appartiennent au même compte et le titulaire du compte bénéficie implicitement du contrôle total de l’objet (lecture, suppression, etc.). Ceci fonctionne de la même manière que les remises par FTP.

AWS permet aussi à un utilisateur de créer des objets dans un compartiment qui appartient à un autre compte utilisateur. Par exemple, deux utilisateurs AWS (utilisateurA et utilisateurB) n’appartiennent pas au même compte AWS mais souhaitent créer des objets dans d’autres compartiments. Si l’utilisateurA crée un compartiment (le compartimentA), il peut créer une règle de compartiment qui autorise explicitement l’utilisateurB à créer des objets dans le compartimentA, même si l’utilisateur n’est pas titulaire du compartiment. Ceci peut s’avérer avantageux car l’utilisateurA et l’utilisateurB n’ont pas à échanger d’informations d’identification. Au lieu de cela, l’utilisateurB fournit à l’utilisateurA son numéro de compte, puis l’utilisateurA crée une règle de compartiment qui autorise l’utilisateurB à créer des objets dans le compartimentA.

**BucketOwnerFullControl** spécifie des droits entre comptes pour créer des objets dans d’autres compartiments. Si l’utilisateurB charge un objet dans le compartiment de l’utilisateurA, l’utilisateurB « détient » toujours cet objet et, par défaut, l’utilisateurA n’a aucune autorisation quant à cet objet, même si l’utilisateurA possède le compartiment. Les objets n’héritent pas des autorisations du compartiment parent. L’utilisateurB doit explicitement octroyer les droits à l’utilisateurA car il reste le propriétaire de l’objet. Pour ce chargement entre comptes, AWS fournit une liste de contrôle d’accès BucketOwnerFullControl en spécifiant que l’utilisation de cette liste de contrôle d’accès revient au propriétaire du compartiment (utilisateurA) et qu’il bénéficie de tous les droits sur l’objet (lecture, écriture, suppression, etc.), même si l’objet est « détenu » par l’utilisateurB.

## Erreurs de transfert {#section_4BD44E9167F0494FB2B379D2BA132AD8}

En cas d’erreur de transfert FTP (connexion refusée, perte de connexion, quota épuisé, etc.), Adobe tente, à trois reprises, d’établir une connexion automatique et d’envoyer les données. Si le problème persiste, le flux est marqué comme ayant échoué et un message de notification est envoyé.

En cas d’erreur de transfert, vous pouvez réexécuter une tâche jusqu’à ce qu’elle aboutisse.

## Options de renvoi {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Une fois que vous avez vérifié/corrigé le problème de remise, réexécutez la tâche pour obtenir les fichiers.

## Le passage à l’heure d’été (DST) a une incidence sur les flux de données horaires {#section_70E867D942054DD09048E027A9474FFD}

Dans certains fuseaux horaires, l’heure change deux fois par an. Les flux de données respectent le fuseau horaire pour lequel la suite de rapports est configurée. Si le fuseau horaire configuré pour la suite de rapports n’applique pas l’heure d’été (DST), la remise se poursuivra normalement. Si, en revanche, le passage à l’heure d’été est appliqué, la remise des fichiers sera modifiée pour l’heure à laquelle le changement d’heure se produit (généralement à 02h00).

Lors des transitions STD -&gt; DST ("Spring Forward"), le client n’obtient que 23 fichiers. L’heure qui est « sautée » au cours du changement d’heure est simplement ignorée. Si, par exemple, la transition a lieu à 2 heures du matin, un fichier sera généré pour 1 heure et un fichier pour 3 heures. Il n’y aura pas de fichier pour 02h00, étant donné qu’à 02h00 STD, il sera 03h00 DST.

Lors des transitions DST -&gt; STD, ("Retour en arrière"), le client recevra 24 fichiers. Cependant, l'heure de transition comprendra en fait deux heures de données. Par exemple, si le changement d’heure a lieu à 02h00, le fichier correspondant à 01h00 sera retardé d’une heure, mais il contiendra l’équivalent de deux heures de données ; entre 01h00 DST et 02h00 STD, qui aurait normalement été 03h00 DST. Le fichier suivant commencera à 02h00 STD.

## Aucune donnée pour une tranche horaire {#section_72510794694D42A9A75C966B812AEB0F}

Vous pouvez éventuellement configurer un fichier de données pour qu’il distribue un fichier de manifeste si aucune donnée n’est collectée pour une période spécifique. Si vous activez cette option, vous recevrez un fichier de manifeste semblable à ceci :

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## Aucune information de domaine pour le rapport sur les domaines {#section_B7508D65370442C7A314EAED711A2C75}

Certains opérateurs mobiles (tels que T-Mobile et O1) ne fournissent plus d’informations sur les domaines pour les recherches DNS inversées. Par conséquent, ces données ne sont pas disponibles dans les rapports sur les domaines.

## Aperçu du traitement de données {#section_6346328F8D8848A7B81474229481D404}

Avant de traiter des données horaires ou quotidiennes, les flux de données attendent que tous les accès concernés par la collecte de données au cours de la période (jour ou heure) aient été écrits dans un entrepôt de données. Ensuite, les flux de données collectent les données avec horodatages compris dans cette tranche horaire, les compresse et les envoie via FTP. Dans le cas des flux horaires, les fichiers sont généralement écrits dans Data Warehouse dans un délai de 15 à 30 minutes, mais aucune période horaire n’est définie. En l’absence de données avec horodatages compris dans cette tranche horaire, le processus fait une nouvelle tentative avec la période suivante. Le processus de flux de données en cours utilise le champ `date_time` pour déterminer les accès qui appartiennent à la période d’une heure. Ce champ est basé sur le fuseau horaire de la suite de rapports.
