---
description: L’option FTP (SAINT) des classifications offre davantage de flexibilité quant au chargement de jeux de données de classification volumineux, notamment la capacité de charger des données dans plusieurs suites de rapports et de charger des jeux de données de plus de 50 000 lignes.
keywords: ftp;sftp
title: Classifications
feature: FTP Export
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 89%

---

# Classifications

L’option FTP des classifications offre davantage de flexibilité quant au chargement de jeux de données de classification volumineux, notamment la capacité de charger des données dans plusieurs suites de rapports et de charger des jeux de données de plus de 50 000 lignes.

Le temps requis par le système pour importer ces fichiers varie, selon un certain nombre de facteurs. Si, après plus de trois jours, un fichier chargé est présent sur le serveur FTP, demandez aux personnes habilitées à le faire de contacter lʼassistance clientèle dʼAdobe.

Si l’importation est réussie, les modifications appropriées sont immédiatement répercutées dans une exportation, tandis qu’avec une importation de navigateur, il peut s’écouler jusqu’à quatre heures avant que les modifications de données dans Analytics ne soient répercutées et jusqu’à 24 heures avec une importation FTP.

Pour plus d’informations sur les limites FTP et la conservation des données, voir [Limites FTP et conservation des données](/help/export/ftp-and-sftp/ftp-limits.md).

## À propos du fichier `.fin` pour les chargements de classifications et de sources de données {#section_1484719F8A134EAE91212DBD8F15174F}

Lorsque vous chargez un fichier de classification ou de Source de données (`.tab` ou `.txt`), vous devez également transférer un fichier vide portant le même nom que le fichier de données importé, mais avec un .Extension `.fin`. Ce fichier `.fin` est un fichier de finition. Il indique au système que le fichier de données a été entièrement chargé sur le compte FTP. Ce fichier `.fin` permet à Adobe de reconnaître quand l’importation est terminée.

Après avoir envoyé le fichier source et le fichier `.fin`, il est important de se déconnecter du site FTP. En effet Adobe Analytics utilise les événements de déconnexion comme déclencheur pour indiquer que les fichiers sont prêts à être traités. Une fois lʼimportation terminée, Adobe supprime les deux fichiers de lʼemplacement FTP.

Fichier de fin : [!DNL Classifications.fin]

Si vous chargez un fichier de sources de données ou de classification sans y joindre le fichier `.fin`, il ne sera pas ajouté à la file dʼattente de traitement par Adobe. Le fichier reste sur le FTP et n’est pas appliqué à vos données dans [!UICONTROL Experience Cloud]. Vous en êtes informé seulement si vous avez spécifié votre adresse e-mail comme [!UICONTROL Destinataire de la notification] dans la fenêtre [!UICONTROL Créer un compte FTP] d’Analytics. Si ce champ ne contient aucune adresse e-mail, aucune notification n’est envoyée.

Si vous chargez votre fichier avec un fichier `.fin`, mais qu’il contient une erreur, il est envoyé pour traitement, mais l’erreur interrompt le traitement et place le fichier à envoyer dans un dossier d’erreur. Si cette erreur survient, une notification est envoyée à l’adresse e-mail indiquée dans le champ [!UICONTROL Destinataire de la notification] dans la fenêtre [!UICONTROL Créer un compte FTP]. Si ce champ ne contenait aucune adresse e-mail, aucune notification nʼest envoyée.
