---
description: Questions fréquentes sur les flux de données
keywords: Flux de données;tâche; colonne « Pré »;colonne « Post »;sensible à la casse
title: FAQ sur les flux de données
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 46ba345247c6a2553cd30b446d87eeb7b15ee94b
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 41%

---

# FAQ sur les flux de données

Questions fréquentes sur les flux de données.

## Les noms de flux doivent-ils être uniques ?{#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Les noms de fichiers des flux de données se composent de l’identifiant de la suite de rapports et de la date. Si deux flux sont configurés pour le même identifiant de suite de rapports et la ou les mêmes dates, ils portent le même nom de fichier. Si ces flux sont diffusés au même emplacement, un fichier remplace l’autre. Pour éviter que cela ne se produise, vous ne pouvez pas créer de flux qui puisse potentiellement remplacer un flux existant situé au même endroit.

Lorsque vous essayez de créer un flux alors qu’un autre flux doté du même nom de fichier existe déjà, le message suivant s’affiche :

Si cette erreur survient, considérez les solutions suivantes :

* Modifier le chemin de diffusion
* Si possible, modifiez les dates
* Si possible, modifiez la suite de rapports

## Quand les données sont-elles traitées ? {#section_6346328F8D8848A7B81474229481D404}

Avant de traiter des données horaires ou quotidiennes, les flux de données attendent que tous les accès concernés par la collecte de données au cours de la période (jour ou heure) aient été écrits dans un entrepôt de données. Ensuite, les flux de données collectent les données avec horodatages compris dans cette période, les compressent et les envoient par FTP. Dans le cas des flux horaires, les fichiers sont généralement écrits dans Data Warehouse dans un délai de 15 à 30 minutes, mais aucune période horaire n’est définie. En l’absence de données avec horodatages compris dans cette tranche horaire, le processus fait une nouvelle tentative avec la période suivante. Le processus de flux de données en cours utilise le champ `date_time` pour déterminer les accès qui appartiennent à la période d’une heure. Ce champ est basé sur le fuseau horaire de la suite de rapports.

## Quelle est la différence entre les colonnes comportant un préfixe `post_` et celle ne comportant pas de préfixe `post_` ?

Les colonnes sans préfixe `post_` contiennent les données telles qu’elles ont été envoyées à la collecte de données. Les colonnes comportant un préfixe `post_` contiennent la valeur après traitement. La persistance de la variable, les règles de traitement, les règles VISTA, la conversion de la devise ou une autre logique côté serveur sont des exemples pouvant modifier une valeur appliqués par Adobe. Adobe recommande d’utiliser la version `post_` d’une colonne dans la mesure du possible.

Si une colonne ne contient pas de version `post_` (par exemple, `visit_num`), alors la colonne peut être considérée comme une colonne « Post ».

## Comment les flux de données gèrent-ils le respect de la casse ?

Dans Adobe Analytics, la plupart des variables sont considérées comme ne respectant pas la casse à des fins de création de rapports. Par exemple, les valeurs « neige », « Neige », « NEIGE » et « nEige » sont toutes considérées comme étant la même valeur. Le respect de la casse est préservé dans les flux de données.

Si vous observez différentes variations de la casse entre les colonnes &quot;Post&quot; et &quot;Post&quot; (par exemple, &quot;neige&quot; dans la colonne &quot;Pré&quot; et &quot;Neige&quot; dans la colonne &quot;Post&quot;), votre mise en oeuvre utilise des valeurs en majuscules et en minuscules sur l’ensemble de votre site. Les différences de casse dans la colonne « Post » étaient précédemment transmises puis stockées dans un cookie virtuel ou étaient traitées à peu près en même temps pour cette suite de rapports.

## Les robots sont-ils filtrés par les règles de robots d’Admin Console incluses dans les flux de données ?

Les flux de données n’incluent pas les robots filtrés par les [règles de robots d’Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Pourquoi est-ce que je vois plusieurs valeurs `000` dans la colonne de flux de données `event_list` ou `post_event_list` ?

Certains éditeurs de feuille de calcul, notamment Microsoft Excel, arrondissent automatiquement les nombres les plus élevés. La colonne `event_list` contient de nombreux nombres délimités par des virgules, ce qui peut parfois entraîner Excel à la traiter comme un grand nombre. Il arrondit les derniers chiffres à `000`.

Adobe recommande de ne pas ouvrir automatiquement les fichiers `hit_data.tsv` dans Microsoft Excel. Utilisez plutôt la boîte de dialogue Importer les données dʼExcel et assurez-vous que tous les champs sont traités comme du texte.

## Pourquoi des informations manquent-elles dans la colonne de domaine pour certains opérateurs ? {#section_B7508D65370442C7A314EAED711A2C75}

Certains opérateurs mobiles (tels que T-Mobile et O1) ne fournissent plus d’informations sur les domaines pour les recherches DNS inversées. Par conséquent, ces données ne sont pas disponibles dans les rapports sur les domaines.

## Pourquoi ne puis-je pas extraire des fichiers &quot;horaires&quot; à partir de données qui ont plus de 7 jours ?

Pour les données de plus de 7 jours, les fichiers &quot;Horaire&quot; d’une journée sont combinés en un seul fichier &quot;Quotidien&quot;.

Exemple : Un nouveau flux de données est créé le 9 mars 2021 et les données du 1er janvier 2021 au 9 mars sont diffusées &quot;toutes les heures&quot;. Toutefois, les fichiers &quot;Horaire&quot; d’avant le 2 mars 2021 sont combinés en un seul fichier &quot;Quotidien&quot;. Vous ne pouvez extraire des fichiers &quot;Horaire&quot; qu’à partir de données qui ont moins de 7 jours à compter de la date de création. Dans ce cas, du 2 au 9 mars.

## Quel est l’impact de l’Économie d’été sur les flux de données horaires ? {#section_70E867D942054DD09048E027A9474FFD}

Pour certains fuseaux horaires, l’heure change deux fois par an en raison des définitions de l’heure d’été. Les flux de données respectent le fuseau horaire pour lequel la suite de rapports est configurée. Si le fuseau horaire de la suite de rapports n’utilise pas l’heure d’été, la remise se poursuit normalement. Si le fuseau horaire de la suite de rapports est défini sur un fuseau horaire qui utilise l’heure d’été, la remise des fichiers est modifiée pour l’heure au cours de laquelle le changement d’heure se produit (généralement 02h00).

Lors d’un changement d’heure STD -> DST (&quot;En avant printemps&quot;), le client ne reçoit que 23 fichiers. L’heure qui est sautée dans la transition DST est omise. Par exemple, si la transition a lieu à 02h00, ils reçoivent un fichier pour 01h00 et un autre pour 03h00. Il n’y a pas de fichier pour 02h00, car à 02h00 STD, il passe à 03h00 DST.

Lors d’une transition DST -> STD (&quot;Retour en arrière&quot;), le client reçoit 24 fichiers. Cependant, l’heure de transition inclut en fait deux heures de données. Par exemple, si la transition a lieu à 02h00, le fichier de 01h00 est retardé d’une heure, mais il contient des données pendant deux heures. Il contient des données allant de 01h00 DST à 02h00 STD (qui auraient normalement été 03h00 DST). Le fichier suivant commence à 02h00 STD.

## Comment Analytics gère-t-il les échecs de transfert FTP ? {#section_4BD44E9167F0494FB2B379D2BA132AD8}

En cas d’échec d’un transfert FTP (en raison d’un refus de connexion, d’une perte de connexion, d’une erreur de quota ou d’un autre problème), Adobe tente de se connecter automatiquement et d’envoyer les données jusqu’à trois fois différentes. Si le problème persiste, le flux est marqué comme ayant échoué et un message de notification est envoyé.

Si un transfert échoue, vous pouvez réexécuter une tâche jusqu’à ce qu’elle réussisse.

Si vous rencontrez des problèmes lors de l’affichage d’un flux de données sur votre site FTP, voir [Résolution des problèmes liés aux tâches](jobs-troubleshooting.md).

## Comment puis-je renvoyer un travail ? {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Une fois que vous avez vérifié ou corrigé le problème de diffusion, réexécutez la tâche pour obtenir les fichiers.

## Qu’est-ce que le paramètre BucketOwnerFullControl pour les flux de données Amazon S3 ? {#BucketOwnerFullControl}

**BucketOwnerFullControl** spécifie des droits entre comptes pour créer des objets dans d’autres compartiments.

Cas d’utilisation type d’Amazon S3 : le titulaire du compte AWS (Amazon Web Services) crée un compartiment, puis crée un utilisateur qui est autorisé à créer des objets dans ce compartiment, puis spécifie les informations d’identification pour cet utilisateur. Dans ce cas, les objets d’un utilisateur appartiennent au même compte et le propriétaire du compte dispose implicitement d’un contrôle total sur l’objet (lecture, suppression, etc.). Ce processus est similaire au fonctionnement de la diffusion FTP.

AWS permet également à un utilisateur de créer des objets dans un compartiment qui appartient à un autre compte utilisateur. Par exemple, deux utilisateurs AWS, utilisateurA et utilisateurB, n’appartiennent pas au même compte AWS, mais souhaitent créer des objets dans d’autres compartiments. Si l’utilisateurA crée un compartiment appelé &quot;compartimentA&quot;, il peut créer une stratégie de compartiment qui permet explicitement à l’utilisateurB de créer des objets dans le compartimentA même si l’utilisateur ne possède pas le compartiment. Cette stratégie peut s’avérer avantageuse, car il n’est pas nécessaire que l’utilisateurA et l’utilisateurB échangent des informations d’identification. Au lieu de cela, l’utilisateurB fournit à l’utilisateurA son numéro de compte, puis l’utilisateurA crée une règle de compartiment qui autorise l’utilisateurB à créer des objets dans le compartimentA.

Cependant, les objets n’héritent pas des autorisations du compartiment parent. Par conséquent, si l’utilisateurB charge un objet dans le compartiment de l’utilisateurA, l’utilisateurB &quot;possède&quot; toujours cet objet et, par défaut, l’utilisateurA n’a aucune autorisation sur cet objet même si l’utilisateurA possède le compartiment. L’utilisateurB doit explicitement octroyer les droits à l’utilisateurA car il reste le propriétaire de l’objet. Pour accorder cette autorisation, l’utilisateurB doit charger l’objet avec une ACL BucketOwnerFullControl , qui spécifie que le propriétaire du compartiment (utilisateurA) se voit accorder des autorisations complètes sur l’objet (lecture, écriture, suppression, etc.), même si l’objet est &quot;détenu&quot; par l’utilisateurB.

>[!NOTE]
>
>[!DNL Analytics] ne détermine pas si le compartiment a une stratégie qui nécessite de donner au propriétaire du compartiment le contrôle total des nouveaux objets, ou même si le propriétaire du compartiment est dans un compte différent de celui de l’utilisateur qui écrit les données. À la place, [!DNL Analytics] ajoute automatiquement le propriétaire du compartiment à la liste de contrôle d’accès BucketOwnerFullControl avec chaque chargement de flux.

>[!MORELIKETHIS]
>
>* [Résolution des problèmes liés aux tâches](jobs-troubleshooting.md)

