---
description: Vous pouvez utiliser Analytics pour créer et gérer des sources de données basées sur un FTP qui importent des données hors ligne ou historiques dans CX Enterprise par le biais du transfert de fichiers par FTP.
keywords: ftp;sftp
title: Sources de données - Aperçu
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
TQID: 'https://experienceleague.adobe.com/3i-ms9Q49CUmEwXiQLek15S3-Kvvh0IIv19-hm01EN0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: e681610c8238aa4940053a28ee60ea54492cba8b
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 51%

---

# Sources de données basées sur FTP

Vous pouvez utiliser Analytics pour créer et gérer des sources de données basées sur un FTP qui importent des données hors ligne ou historiques dans CX Enterprise par le biais du transfert de fichiers par FTP.

Après avoir créé une instance de sources de données, l’outil fournit un emplacement FTP que vous pouvez utiliser pour charger les fichiers de sources de données. Une fois ces fichiers chargés, ils sont automatiquement localisés et traités. Une fois les fichiers traités, les données sont disponibles pour la création de rapports Analytics.

Dans l’onglet [!UICONTROL Créer] du gestionnaire des sources de données, vous pouvez configurer une nouvelle instance de sources de données pour la suite de rapports sélectionnée. L’assistant Sources de données vous guide tout au long du processus de création d’un modèle de sources de données et crée un emplacement FTP pour le chargement de données.

Dans la fenêtre [!UICONTROL Gérer les sources de données], recherchez votre source de données et cliquez sur le lien Infos FTP. Vos informations de connexion FTP s’affichent dans la fenêtre [!UICONTROL  Activer une Source de données ] de la section [!UICONTROL  Charger/Informations FTP ].

Pour plus d’informations sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](/help/export/ftp-and-sftp/ftp-limits.md).

## Fichier .fin pour les chargements de classifications et de sources de données {#section_1484719F8A134EAE91212DBD8F15174F}

Lorsque vous chargez un fichier de classifications ou de source de données ( `.tab` ou `.txt`), vous devez également charger un fichier vide portant le même nom que le fichier de données importé, mais avec une extension `.fin`. Ce fichier `.fin` est un fichier de finition. Il indique au système que le fichier de données a été entièrement chargé sur le compte FTP. Ce fichier `.fin` permet à Adobe de reconnaître quand l’importation est terminée. Après l’avoir soumis, Adobe supprime les deux fichiers du FTP et commence à traiter l’importation.

Importer un fichier : `Classifications.tab`

Fichier de fin : `Classifications.fin`

Si vous chargez le fichier de sources de données ou SAINT sans y joindre le fichier `.fin`, il ne sera pas ajouté à la file d’attente de traitement par Adobe. Le fichier reste sur le FTP et n’est pas appliqué à vos données dans CX Enterprise. Vous en êtes informé seulement si vous avez spécifié votre adresse e-mail comme [!UICONTROL Destinataire de la notification] dans la fenêtre de création de rapports [!UICONTROL Créer un compte FTP]. Si aucune adresse e-mail n’est saisie dans ce champ, aucune notification n’est envoyée.

Si vous chargez votre fichier avec un fichier `.fin`, mais qu’il contient une erreur, il est envoyé pour traitement, mais l’erreur interrompt le traitement et place le fichier à envoyer dans un dossier d’erreur. Si cette erreur survient, une notification est envoyée à l’adresse e-mail indiquée dans le champ [!UICONTROL Destinataire de la notification] dans la fenêtre [!UICONTROL Créer un compte FTP]. Si aucune adresse e-mail n’est saisie, aucune notification n’est envoyée.
