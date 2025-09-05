---
description: Options de calendrier autres que le modèle grégorien. Les options incluent les modèles de calendrier 4-4-5, 4-5-4 et 5-4-4, qui sont tous des normes du secteur de la vente au détail. Les rapports proposent également un calendrier entièrement personnalisable que vous pouvez configurer vous-même.
title: Personnalisation du calendrier
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 91%

---

# Personnalisation du calendrier

Options de calendrier autres que le modèle grégorien. Les options incluent les modèles de calendrier 4-4-5, 4-5-4 et 5-4-4, qui sont tous des normes du secteur de la vente au détail. En outre, la création de rapports offre une option de personnalisation complète du calendrier.

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionnez la suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Personnaliser le calendrier]**

>[!CAUTION]
>
>Lorsque vous changez de calendrier, le mode de traitement des données est également modifié (c’est-à-dire la définition des visiteurs uniques par mois et par semaine). Les données historiques ne sont pas altérées quand la définition des semaines et des mois d’un calendrier est modifiée. Ce paramètre affecte également les segments basés sur des périodes.

Vous pouvez utiliser le calendrier pour définir le premier jour de la semaine et de l’année, ou un style de calendrier de vente au détail différent. Chaque format a son utilité, notamment pour la comparaison des ventes et la normalisation des prévisions, l’analyse des coûts salariaux ou encore la régulation de l’inventaire matériel. Par exemple, dans le domaine de la vente au détail, on utilise un calendrier comptable de type 4-5-4 pour tenir compte des saisons de vente spécifiques à ce secteur d’activités. Vous trouverez, ci-dessous, la description de chacun des formats calendaires.

## Descriptions de la personnalisation des calendriers {#section_B0D224DACB914A378902A4E0E1234889}

| Calendrier | Description |
|--- |--- |
| Calendrier grégorien | Utilise le format de calendrier traditionnel (de janvier à décembre avec des mois de 30 et 31 jours et un nombre de semaines variable pour chaque mois). |
| Calendrier grégorien modifié | Utilise le calendrier grégorien traditionnel, mais vous permet de choisir le premier mois de l’année et le premier jour de la semaine. |
| Calendrier de vente au détail 4-5-4 | Décompose chaque mois selon le nombre de semaines qu’il comporte. En d’autres termes, janvier compte 4 semaines, etc. La National Retail Federation (États-Unis) utilise le format de calendrier en 4-5-4. |
| Calendrier personnalisé | Offre trois formats selon le nombre de semaines de chaque mois. Le nombre de semaines dans le mois dépend du premier jour de l’année choisi.  Une année comporte 52 semaines. Divisez ce chiffre en 4 trimestres et vous obtenez 13 semaines par trimestre. Toutefois, un trimestre comprend 3 mois. 13 n’est pas divisible par trois. De ce fait, vous placez la semaine supplémentaire dans l’un des mois pour garantir la cohérence.<ul><li>5-4-4 signifie que la semaine supplémentaire a été ajoutée au premier mois. 4-5-4 signifie que la semaine supplémentaire a été ajoutée au deuxième mois, etc. Dans le calendrier 5-4-4, la 53e semaine est ajoutée au dernier trimestre de l’année.</li><li>4-5-4:January a quatre semaines, février a cinq semaines, mars a quatre semaines, etc.</li><li>4-4-5 : janvier comporte quatre semaines, février quatre, mars cinq, etc.</li><li>5-4-4 : janvier comporte cinq semaines, février quatre, mars quatre, etc.</li></ul> |

>[!NOTE]
>Ces options de calendrier sont prises en charge dans tous les outils Adobe Analytics (Analysis Workspace, Report Builder, Activity Map), à l’exception de Data Warehouse. Data Warehouse ne prend entièrement en charge que le calendrier grégorien. Lors du choix d’un calendrier non grégorien, Data Warehouse utilise la période prévue du calendrier non grégorien. Toutefois, les répartitions jour/semaine/mois dans les lignes du rapport peuvent ne pas correspondre aux attentes d’un calendrier non grégorien.
