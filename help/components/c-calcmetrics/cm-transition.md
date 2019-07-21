---
description: Les modifications suivantes apportées à la manière dont les mesures calculées fonctionnent dans Analytics peuvent avoir un impact sur vous.
seo-description: Les modifications suivantes apportées à la manière dont les mesures calculées fonctionnent dans Analytics peuvent avoir un impact sur vous.
seo-title: Questions fréquentes
title: Questions fréquentes
uuid: 9 b 7 f 1 cd 1-b 969-4 b 15-8 af 1-969 d 816 b 65 b 8
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# Questions fréquentes

These changes to the way calculated metrics work in [!DNL Analytics] may impact you.

[Comment puis-je accéder au créateur de mesures calculées ?](../../components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[Comment puis-je accéder au Gestionnaire de mesures calculées ?](../../components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[Pourquoi vois-je de nombreuses mesures calculées avec le même nom ?](../../components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[Qu’est-il advenu de mes mesures calculées globales ?](../../components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[Qu’est-il advenu des mesures calculées globales qui étaient partagées au sein des sociétés de connexion ?](../../components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[Qu’est-il advenu des mesures calculées avec une classification numérique ou numérique2 ?](../../components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[Qu’est-il advenu des mesures de durée de vie ?](../../components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[Qu’ai-je besoin de savoir sur les mesures calculées selon les mesures Visiteur unique quotidiennes/hebdomadaires/mensuelles/annuelles ?](../../components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[Qu’en est-il des mesures calculées créées ou gérées avec les méthodes de l’ancienne API de suite de rapports ?](../../components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[Les données actives prennent-elles en charge tous les types de mesures calculées ?](../../components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[Que signifie « Aucun nom fourni » en association avec des mesures calculées migrées ?](../../components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[Qu’advient-il des mesures calculées d’un utilisateur si cet utilisateur a été supprimé ?](../../components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[Pourquoi vois-je des mesures calculées « inconnues » qui ne sont pas valides pour d’autres suites de rapport même si elles peuvent être créées et appliquées à ces suites de rapports ?](../../components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[Pourquoi des modifications que j’ai apportées à mes mesures calculées héritées n’ont-t-elles pas été enregistrées ?](../../components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[Pourquoi mes mesures calculées ne s’affichent-elles pas dans le rapport Canaux marketing ?](../../components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[Pourquoi certaines des mesures calculées affichent-elles des formules sans les parenthèses que j’ai ajoutées ?](../../components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[(Ad Hoc Analysis uniquement) Les mesures calculées avec des définitions de segment incorporées ou insérées sont-elles toujours prises en charge ?](../../components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[(Report Builder uniquement) Pourquoi les mesures calculées ont-elles disparu de mes demandes ?](../../components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[Comment fonctionnent les totaux des mesures calculées ?](../../components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## Comment puis-je accéder au créateur de mesures calculées ?{#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Cliquez sur **[!UICONTROL + Ajouter]dans la partie supérieure du créateur de mesures calculée, ou**
* Dans n’importe quel rapport Analytics, cliquez sur l’icône Mesures ![](assets/metrics_icon.png) située à gauche d’un rapport pour afficher le rail Mesures, puis cliquez sur **[!UICONTROL Ajouter]**.

## Comment puis-je accéder au Gestionnaire de mesures calculées ?{#section_DD0BD13E9EC940268EBE8BC88241A152}

* Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** in the left navigation. Puis, cliquez sur **[!UICONTROL Mesures calculées]**.

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## Why do I see so many Calculated Metrics with the same name? {#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(Antérieurement, les mesures calculées globales n’étaient pas possédées par un utilisateur administrateur spécifique et n’étaient pas visibles par tous les utilisateurs de cette suite de rapports. Les mesures étaient séparées par suite de rapports. Si une mesure d’une suite de rapports possède le même nom qu’une mesure d’une suite de rapports différente, elle apparaît simplement aux utilisateurs comme la même mesure lorsqu’ils changent de suites de rapports.)

Désormais, les mesures ne sont plus séparées par suites de rapports. Si une mesure d’une suite de rapport porte le même nom qu’une mesure d’une suite de rapport différente, elles sont toutes les deux visibles dans le créateur de mesures calculées ainsi que dans le sélecteur de mesures et peuvent apparaître comme mesures en double même si elles ont ou n’ont pas la même définition.

You would see a number of calculated metrics with the same name (but created in different report suites) only if you unchecked the (Only `<report suite>`) checkbox as shown here:

![](assets/report_suite.png)

**Ce que vous devez faire**

Envisagez la consolidation des mesures calculées avec des noms et définitions similaires mais soyez prudent lors de cette opération. Vous pouvez vérifier la suite de rapports pour une mesure calculée dans le Gestionnaire de mesures calculées afin de vérifier sa suite de rapports d’origine. Vous devez également vérifier les définitions des mesures lors de la suppression des doublons potentiels pour garantir que vous consolidez correctement les mesures.

> [!NOTE] Bien que les mesures calculées ne soient plus liées à une suite de rapports spécifique et puissent être utilisées dans toute suite de rapports visible pour la société de connexion, la suite de rapports sous laquelle la mesure calculée a été créée ou enregistrée en dernier est toujours visible dans le Gestionnaire de mesures calculées.

> [!NOTE] Même si une mesure calculée est supprimée, tous les rapports de signets ou de tableaux de bord qui font référence à cette mesure fonctionneront toujours.

## Qu’est-il advenu de mes mesures calculées globales ?{#section_7351D4C7361F4ABAA1B43F8E89AAD211}

(Antérieurement, un administrateur pouvait créer des mesures calculées, connues sous le nom de « mesures calculées globales » ou « mesures calculées de la suite de rapports », dans une suite de rapports par l’intermédiaire des outils d’administration.

Les mesures calculées globales sont désormais possédées par le premier utilisateur administrateur de la liste d’utilisateurs administrateur de la société de connexion. Elles sont, par défaut, partagées avec « Tout le monde ». Ce modèle suit le même modèle de partage et les mêmes plans de migration que les segments.

**Ce que vous devez faire**

Rien. Néanmoins, le nouveau propriétaire administrateur doit être prudent lors de la modification ou de la suppression de ces mesures calculées : elles peuvent être utilisées dans plusieurs rapports ou tableaux de bord marqués.

> [!NOTE] Même si une mesure calculée est supprimée, tous les rapports de signets ou de tableaux de bord qui font référence à cette mesure fonctionneront toujours.

## Qu’est-il advenu des mesures calculées globales qui étaient partagées au sein des sociétés de connexion ?{#section_59E5CD948ED643AE9AD3D2E4277647F8}

(Antérieurement, un administrateur pouvait créer des mesures calculées, connues sous le nom de « mesures calculées globales » ou « mesures calculées de la suite de rapports », dans une suite de rapports par l’intermédiaire des outils d’administration. Ces mesures pouvaient alors être « partagées » sur des sociétés de connexion en ajoutant la suite de rapports à plusieurs sociétés de connexion.)

Les mesures calculées globales ne peuvent plus être partagées au sein des sociétés de connexion. Elles ne sont plus liées ou associées à une suite de rapports spécifique mais, à la place, liées à une société de connexion spécifique. Les mesures calculées qui étaient partagées au sein des sociétés de connexion

* Ont été migrés vers toutes les sociétés de connexion avec accès à cette suite de rapports.
* Valeur par défaut « partagée avec tout le monde ».
* Seront des copies indépendantes de toutes les autres sociétés de connexion.

>[!NOTE]
>
>Si la mesure calculée a été utilisée dans un signet, un tableau de bord, une alerte ou un rapport planifié, la modification de la nouvelle copie n'affecte PAS l'ancienne mesure calculée conservée.

## Qu’est-il advenu des mesures calculées avec une classification numérique ou numérique2 ?{#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports &amp; Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports &amp; Analytics], [!UICONTROL Report Builder], and the APIs. Néanmoins, elles ne seront pas prises en charge dans un rapport avec un segment appliqué.

In addition, calculated metrics with a Numeric or Numeric2 classification will not be supported in the following components: [!UICONTROL Ad Hoc Analysis], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] reports, [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis]. Lorsque vous créez ou modifiez une mesure calculée avec une classification numérique ou numérique2, un avertissement de compatibilité s’affiche indiquant que la mesure calculée n’est pas compatible avec certaines zones du produit.

**Ce que vous devez faire**

Evitez de créer des mesures calculées avec la classification numérique ou numérique2 si vous avez l’intention d’utiliser la mesure avec un segment ou avec des composants non compatibles.

## Qu’est-il advenu des mesures de durée de vie ?{#section_AEDB02EF24584DAD8731BED9DDCE4F48}

Life-Time metrics (a.k.a. all-time metrics) are no longer supported and no longer visible in the [!UICONTROL Reports &amp; Analytics] UI or any other UI. L’API Rapport ne peut pas les interroger.

Tout signet, tableau de bord, rapport planifié ou alerte qui contenait une mesure de durée de vie continue à s’exécuter sans cette mesure tant qu’au moins une autre mesure valide figure également dans le rapport. Si la seule mesure du signet, du tableau de bord, du rapport planifié ou de l’alerte est une mesure de durée, le rapport ne s’exécute plus.

## Qu’ai-je besoin de savoir sur les mesures calculées selon les mesures Visiteur unique quotidiennes/hebdomadaires/mensuelles/annuelles ?{#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports &amp; Analytics], [!UICONTROL Report Builder], and Reporting API.

However, these metrics will not be supported in the following components: [!UICONTROL Segments], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] reports, [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis]. Lorsque vous créez ou modifiez une mesure calculée basée sur des mesures Visiteurs uniques, un avertissement de compatibilité s’affiche indiquant que la mesure n’est pas compatible avec certaines zones du produit.

Vous utilisez une mesure Visiteur unique de base sur un rapport avec un segment. Vous pouvez créer une mesure calculée basée sur une mesure Visiteur unique. Néanmoins, cette mesure calculée ne peut pas être appliquée à un rapport avec un segment. Elle ne peut pas non plus comporter un segment incorporé.

## What happens to Calculated Metrics created or managed with the old report suite API methods? {#section_13ED1BAD02634674BDAEB479B060A4B6}

Antérieurement, l’enregistrement d’une mesure calculée avec la méthode API (1.3 ou 1.4) ReportSuite.SaveCalculatedMetrics était identique à la création ou la mise à jour d’une mesure calculée dans la Admin Console. Idem pour ReportSuite.DeleteCalculatedMetrics. Egalement, la liste des mesures calculées affichée dans la Admin Console ou lors de l’appel de ReportSuite.GetCalculatedMetrics était la même.

Désormais, les méthodes API reportsuite calculatedmetrics (1.3 ou 1.4) continueront à enregistrer, supprimer et récupérer les mesures calculées à l'aide de l'ancienne boutique. Les mesures calculées existantes seront migrées et seront visibles dans le nouveau créateur de mesures calculées. **Les nouvelles mesures calculées créées avec les méthodes API seront visibles uniquement dans l’API. Elles seront toujours utilisables dans l’API de création de rapports.**

**Ce que vous devez faire**

Si vous devez utiliser à la fois l’API et le créateur de mesures calculées, vous devez arrêter d’utiliser les méthodes API ReportSuite CalculatedMetrics et, à la place, utiliser les nouvelles méthodes API CalculatedMetrics (Get, Save, Delete et GetFunctions).

## Does Current Data support all types of Calculated Metrics? {#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

Les données actives ne prennent pas en charge les mesures calculées qui comportent des segments ou des fonctions statistiques. Les seules fonctions prises en charge sont les fonctions mathématiques de base telles que l’addition, la soustraction, la multiplication et la négation (-x).

## Que signifie « Aucun nom fourni » en association avec des mesures calculées migrées ?{#section_C90CBB72A67644F38D583301981F8D03}

« Aucun nom fourni » signifie qu’aucun nom de mesure n’est associé à cette mesure migrée (juste une formule sans nom explicite).

## Qu’advient-il des mesures calculées d’un utilisateur si cet utilisateur a été supprimé ?{#section_42ED4C15830540879C4A161423690E5A}

Toutes les mesures calculées que cet utilisateur a créées sont également supprimées. Néanmoins, les mesures calculées supprimées continueront à fonctionner dans le cadre des signets, tableaux de bord ou rapports planifiées enregistrés.

## Pourquoi vois-je des mesures calculées « inconnues » qui ne sont pas valides pour d’autres suites de rapport même si elles peuvent être créées et appliquées à ces suites de rapports ?{#section_6772818EFDED46E9B7095D64C3B77211}

L’interface utilisateur affiche « inconnu » si la mesure calculée contient des mesures ou des dimensions de base qui n’existent pas pour la suite de rapports sélectionnée.

## Pourquoi des modifications que j’ai apportées à mes mesures calculées héritées n’ont-t-elles pas été enregistrées ?{#section_81CDEFCA1FD542579AF183DA1494EAF0}

Cela peut être dû à la date de la migration de la nouvelle base de données des mesures calculées, qui a eu lieu entre le 15 et le 18 juin 2015.

**Ce que vous devez faire**

Vous devez apporter à nouveau les modifications que vous avez apportées à vos mesures héritées.

## Pourquoi mes mesures calculées ne s’affichent-elles pas dans le rapport Canaux marketing ?{#section_FC350359A775433AB5F43C7CAB304D62}

(Antérieurement, toutes les mesures calculées étaient répertoriées dans le sélecteur de mesures des rapports Canaux marketing avec des options de première touche et de dernière touche.)

Désormais, seules les mesures calculées dont le type d’allocation est spécifiquement défini sur Première touche ou Dernière touche dans le créateur de mesures calculées sont disponibles dans le sélecteur de mesures des rapports Canaux marketing. Notez que toute mesure calculée déjà appliquée aux rapports Canal marketing continuera d’être appliquée et fonctionnera comme auparavant. Pour créer une mesure calculée pour les canaux marketing, cliquez sur l’icône de configuration dans le créateur de mesures et sélectionnez Première touche ou Dernière touche comme type d’allocation. Gardez à l’esprit qu’une telle opération rend la mesure calculée compatible uniquement avec les rapports Canal marketing et elle ne pourra pas être utilisée pour d’autres rapports.

## Pourquoi certaines des mesures calculées affichent-elles des formules sans les parenthèses que j’ai ajoutées ?{#section_AC0D1E9714AD487F9A1C73359F518B5E}

Au cours de la migration, Adobe a éliminé les parenthèses superflues de certaines formules. Seules les parenthèses qui n’affectent pas la manière dont la mesure est calculée ont été supprimées. Cela ne modifie pas les données - cela simplifie juste la formule.

## (Ad Hoc Analysis only) Are Calculated Metrics with embedded or inline segment definitions still supported? {#section_B25C924A282F49388AB604E3D826F44C}

Les mesures calculées créées dans les Ad Hoc Analysis pouvaient antérieurement comporter des définitions de segment insérées. Cela n’est plus possible.

**Ce que vous devez faire**

Vous devez enregistrer explicitement le segment. Les mesures calculées existantes avec des définitions de segment insérées continuent à s’exécuter correctement et peuvent être visualisées dans les Ad Hoc Analysis mais elles ne peuvent pas être enregistrées sans enregistrer explicitement le segment.

## (Report Builder uniquement) Pourquoi les mesures calculées ont-elles disparu de mes demandes ?{#section_DA4792FE5D7945218CD5E6328DE08E82}

Si la requête a été créée dans la version 5.2 et qu'elle contient des mesures calculées, ces mesures ne sont pas visibles dans la version 5.1 (ou versions antérieures). car les mesures calculées utilisent désormais des identifiants globaux (identifiants non spécifiques à une suite de rapports).

**Ce que vous devez faire**

Vous devez mettre à jour vers la version 5.2 pour pouvoir consulter ces mesures.

## Comment fonctionnent les totaux des mesures calculées ?{#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports &amp; Analytics] shows a calculated metrics total in [!UICONTROL Reports &amp; Analytics], it's just applying the formula to the total. Par exemple, le total de la mesure calculée Commandes/visite prend le total des commandes et le divise par le total des visites. Dans certains cas, le total de la mesure calculée ne correspond toutefois pas à la somme des éléments de ligne. Il peut s’agir d’un total pour le site.

Exemple 1 : visiteurs d’un terme de recherche : un même visiteur peut avoir recherché plusieurs termes. Dans ce cas, le nombre total de visiteurs n’est donc pas égal à la somme des éléments de ligne.

Exemple 2 : pages vues sur les produits : comme le panier comporte plusieurs produits, il existe plusieurs pages vues pour le panier. Pour plus d’informations sur la comparaison de la somme des éléments de ligne aux totaux des rapports, consultez [cet article de la base de connaissances](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html).
