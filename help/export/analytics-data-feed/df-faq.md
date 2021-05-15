---
description: Questions fréquentes sur les flux de données
keywords: Flux de données ; tâche ; colonne "Pré" ; colonne "Post" ; respect de la casse
title: FAQ sur les flux de données
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 7312b61b8d73f45afa3eb9aac73cc4d5fd39bc82
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 49%

---

# FAQ sur les flux de données

Questions fréquentes sur les flux de données.

## Les noms de flux doivent-ils être uniques ?{#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Les noms de fichiers des flux de données se composent de l’identifiant de la suite de rapports et de la date. Si deux flux sont configurés avec le même identifiant de suite de rapports et la ou les mêmes dates, ils auront le même nom de fichier. Si ces deux flux sont diffusés au même endroit, un fichier remplacera l’autre. Pour éviter que cela ne se produise, vous ne pouvez pas créer de flux qui puisse potentiellement remplacer un flux existant situé au même endroit.

Lorsque vous essayez de créer un flux alors qu’un autre flux doté du même nom de fichier existe déjà, le message suivant s’affiche :

Si cette erreur survient, considérez les solutions suivantes :

* Modifier le chemin de diffusion
* Si possible, modifiez les dates
* Si possible, modifiez la suite de rapports

## Quand les données sont-elles traitées ? {#section_6346328F8D8848A7B81474229481D404}

Avant de traiter des données horaires ou quotidiennes, les flux de données attendent que tous les accès concernés par la collecte de données au cours de la période (jour ou heure) aient été écrits dans un entrepôt de données. Ensuite, les flux de données collectent les données avec horodatages compris dans cette tranche horaire, les compressent et les envoient via FTP. Dans le cas des flux horaires, les fichiers sont généralement écrits dans Data Warehouse dans un délai de 15 à 30 minutes, mais aucune période horaire n’est définie. En l’absence de données avec horodatages compris dans cette tranche horaire, le processus fait une nouvelle tentative avec la période suivante. Le processus de flux de données en cours utilise le champ `date_time` pour déterminer les accès qui appartiennent à la période d’une heure. Ce champ est basé sur le fuseau horaire de la suite de rapports.

## Quelle est la différence entre les colonnes comportant un préfixe `post_` et celle ne comportant pas de préfixe `post_` ?

Les colonnes sans préfixe `post_` contiennent des données exactement comme elles ont été envoyées à la collecte de données. Les colonnes avec un préfixe `post_` contiennent la valeur après traitement. La persistance de la variable, les règles de traitement, les règles VISTA, la conversion de la devise ou une autre logique côté serveur sont des exemples pouvant modifier une valeur appliqués par Adobe. Adobe recommande d’utiliser la version `post_` d’une colonne dans la mesure du possible.

Si une colonne ne contient pas de version `post_` (par exemple, `visit_num`), alors la colonne peut être considérée comme une colonne « Post ».

## Comment les flux de données gèrent-ils le respect de la casse ?

Dans Adobe Analytics, la plupart des variables sont considérées comme ne respectant pas la casse à des fins de création de rapports. Par exemple, les valeurs « neige », « Neige », « NEIGE » et « nEige » sont toutes considérées comme étant la même valeur. Le respect de la casse est préservé dans les flux de données.

Si vous observez différentes variations de la casse entre des colonnes « Post » et non « Post » (par exemple, « neige » dans la colonne « Pré » et « Neige » dans la colonne « Post »), cela signifie que votre implémentation utilise des valeurs à la fois en majuscules et en minuscules sur votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports.

## Les robots sont-ils filtrés par les règles de robots d’Admin Console incluses dans les flux de données ?

Les flux de données n’incluent pas les robots filtrés par les [règles de robots d’Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Pourquoi vois-je plusieurs valeurs `000` dans la colonne de flux de données `event_list` ou `post_event_list` ?

Certains éditeurs de feuilles de calcul, en particulier Microsoft Excel, arrondissent automatiquement les nombres importants. La colonne `event_list` contient de nombreux nombres délimités par des virgules, ce qui peut parfois entraîner un traitement par Excel en nombre important. Il arrondit les derniers chiffres à `000`.

Adobe recommande de ne pas ouvrir automatiquement les fichiers `hit_data.tsv` dans Microsoft Excel. Utilisez plutôt la boîte de dialogue Importer des données d’Excel et assurez-vous que tous les champs sont traités comme du texte.

## Pourquoi les informations manquantes dans la colonne de domaine pour certains opérateurs sont-elles absentes ? {#section_B7508D65370442C7A314EAED711A2C75}

Certains opérateurs mobiles (tels que T-Mobile et O1) ne fournissent plus d’informations sur les domaines pour les recherches DNS inversées. Par conséquent, ces données ne sont pas disponibles dans les rapports sur les domaines.

## Pourquoi ne puis-je pas extraire des fichiers &quot;horaires&quot; à partir de données qui datent de plus de 7 jours ?

Pour les données de plus de 7 jours, les fichiers &quot;Horaire&quot; d’une journée sont combinés dans un seul fichier &quot;Quotidien&quot;.

Exemple : Un nouveau flux de données est créé le 9 mars 2021 et les données du 1er janvier 2021 au 9 mars sont fournies sous la forme &quot;Horaire&quot;. Cependant, les fichiers &quot;Horaire&quot; antérieurs au 2 mars 2021 sont combinés en un seul fichier &quot;Quotidien&quot;. Vous pouvez extraire des fichiers &quot;Horaire&quot; uniquement à partir de données qui datent de moins de 7 jours à compter de la date de création. Dans ce cas, du 2 mars au 9 mars.

## Quel est l’impact de l’économie d’heure sur les flux de données horaires ? {#section_70E867D942054DD09048E027A9474FFD}

Pour certains fuseaux horaires, l’heure change deux fois par an en raison des définitions de l’heure d’été (heure d’été). Les flux de données respectent le fuseau horaire pour lequel la suite de rapports est configurée. Si le fuseau horaire de la suite de rapports n’utilise pas l’heure d’été, la diffusion de fichiers se poursuit normalement comme tout autre jour. Si le fuseau horaire de la suite de rapports est un fuseau qui utilise l’heure d’été, la diffusion de fichiers est modifiée pour l’heure au cours de laquelle le changement d’heure se produit (généralement 02h00).

Lors de la création de transitions d&#39;heure STD -> DST (&quot;En avant du printemps&quot;), le client ne reçoit que 23 fichiers. L’heure qui est ignorée dans la transition DST est ignorée. Par exemple, si la transition se produit à 2h00, un fichier est obtenu pour 1 h00 et un autre pour 3 h00. Il n&#39;y a pas de fichier de 2h00, car à 2h00 STD, il devient 3h00 DST.

Lors de la création de transitions DST -> STD (&quot;Retourner&quot;), le client reçoit 24 fichiers. Cependant, l&#39;heure de transition inclut en fait deux heures de données. Par exemple, si la transition se produit à 2h00, le fichier de 1h00 est retardé d’une heure, mais il contient des données pendant deux heures. Il contient des données de 1:00 DST à 2:00 STD (qui aurait été 3:00 DST). Le fichier suivant commence à 02h00 STD.

## Comment Analytics gère-t-il les échecs de transfert FTP ? {#section_4BD44E9167F0494FB2B379D2BA132AD8}

Dans le événement d&#39;un échec de transfert FTP (connexion refusée, perte de connexion, quota dépassé, etc.), l&#39;Adobe tente de se connecter automatiquement et d&#39;envoyer les données jusqu&#39;à trois fois différentes. Si le problème persiste, le flux est marqué comme ayant échoué et un message de notification est envoyé.

Si un transfert échoue, vous pouvez réexécuter une tâche jusqu’à ce qu’elle réussisse.

Si vous rencontrez des problèmes pour afficher un flux de données sur votre site FTP, consultez [Résolution des problèmes liés aux tâches](jobs-troubleshooting.md).

## Comment puis-je renvoyer un travail ? {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Une fois que vous avez vérifié ou corrigé le problème de diffusion, réexécutez la tâche pour obtenir les fichiers.

## Quel est le paramètre BucketOwnerFullControl pour les flux de données Amazon S3 ? {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Cas d’utilisation type d’Amazon S3 : le titulaire du compte AWS (Amazon Web Services) crée un compartiment, puis crée un utilisateur qui est autorisé à créer des objets dans ce compartiment, puis spécifie les informations d’identification pour cet utilisateur. Dans ce cas, les objets d’un utilisateur appartiennent au même compte et le propriétaire du compte a implicitement le contrôle total de l’objet (lecture, suppression, etc.). Ce processus est similaire au fonctionnement de la diffusion FTP.

AWS permet également à un utilisateur de créer des objets dans un compartiment appartenant à un autre compte utilisateur. Par exemple, deux utilisateurs AWS (utilisateurA et utilisateurB) n’appartiennent pas au même compte AWS, mais souhaitent créer des objets dans d’autres compartiments. Si l’utilisateurA crée un compartiment (le compartimentA), il peut créer une règle de compartiment qui autorise explicitement l’utilisateurB à créer des objets dans le compartimentA, même si l’utilisateur n’est pas titulaire du compartiment. Cette stratégie peut s’avérer avantageuse car elle n’exige pas que l’utilisateurA et l’utilisateurB échangent des informations d’identification. Au lieu de cela, l’utilisateurB fournit à l’utilisateurA son numéro de compte, puis l’utilisateurA crée une règle de compartiment qui autorise l’utilisateurB à créer des objets dans le compartimentA.

**BucketOwnerFullControl** spécifie des droits entre comptes pour créer des objets dans d’autres compartiments. Si l’utilisateurB télécharge un objet dans le compartiment de l’utilisateurA, l’utilisateurB &quot;possède&quot; toujours cet objet et, par défaut, l’utilisateurA n’a aucune autorisation pour cet objet, même si l’utilisateurA possède le compartiment. En effet, les objets n’héritent pas des autorisations du compartiment parent. L’utilisateurB doit explicitement octroyer les droits à l’utilisateurA car il reste le propriétaire de l’objet. Pour accorder cette autorisation, l’utilisateurB doit télécharger l’objet avec une ACL BucketOwnerFullControl, qui spécifie que le propriétaire du compartiment (utilisateurA) se voit accorder des autorisations complètes sur l’objet (lecture, écriture, suppression, etc.), même si l’objet est &quot;détenu&quot; par l’utilisateurB.

>[!MORELIKETHIS]
>
>* [Résolution des problèmes liés aux tâches](jobs-troubleshooting.md)

