---
description: valeur nulle
title: ID de transaction et profils du visiteur
topic: Developer and implementation
uuid: 7a72779c-7f67-4872-ad5e-edf298d53cac
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ID de transaction et profils du visiteur

Cette section contient des informations importantes au sujet des données issues du profil du visiteur utilisées lors du transfert des données à l’aide d’un ID de transaction.

## ID de transaction {#section_B248FA93ECC84F6290D237EB83618070}

Lorsqu’un ID de transaction est enregistré, un « instantané » du profil du visiteur actif est enregistré et associé à l’ID de transaction. Cet « instantané » contient toutes les valeurs de variables actuellement définies pour le visiteur, y compris les variables persistantes (par exemple les eVars et les campagnes). Les valeurs dans cet instantané reçoivent l’attribution pour les événements de succès, les événements d’achat et les recettes transférés par la suite à l’aide de ce même ID de transaction.

Une fois l’« instantané » du profil du visiteur créé, il n’est pas mis à jour en cas de modifications du profil du visiteur actif (en raison du comportement en ligne) ; il est mis à jour uniquement pour les données transférées à l’aide des sources de données de l’ID de transaction. Si vous définissez la même valeur d’ID de transaction sur plusieurs pages durant la même visite, le transfert de source de données qui prend place plus tard sera lié à l’« instantané » qui a été créé la première fois que l’ID a été défini.

**Transferts multiples**

Plusieurs lignes de données peuvent être transférées vers le même ID de transaction pendant toute la durée d’expiration de l’ID de transaction.

**Expiration des variables**

L’expiration de variable n’est pas considérée à des fins d’ID de transaction, car les données du profil du visiteur associées sont destinées à refléter l’état du visiteur au moment de la transaction. Si, par exemple, l’eVar1 est configurée pour expirer après la visite, la valeur dans l’« instantané » du profil du visiteur est créditée même si la valeur a expiré ou a été remplacée dans le profil du visiteur actif lors du transfert des données de l’ID de transaction.

**Produits**

Les informations sur les produits (issues de `s.products`) ne sont pas contenues dans l’« instantané » du profil du visiteur ; vous devez donc transférer toutes les données associées dans le fichier de source de données, avec l’ID de transaction. Remarque : Vous pouvez préciser uniquement un produit par ligne ; par conséquent, vous devrez peut-être transférer plusieurs lignes avec le même ID de transaction afin d’inclure tous les produits.

**Persistance des eVar transférées**

Les eVars transférées à l’aide des sources de données des ID de transaction sont ajoutées à l’« instantané » du profil du visiteur ; elles ne sont pas ajoutées au profil du visiteur actif ni au cookie virtuel. En d’autres termes, le comportement en ligne qui survient après le transfert n’est pas crédité pour les eVars transférées, puisque ces valeurs ne font pas partie du profil du visiteur actif.

**Intervalle d’expiration de l’ID de transaction**

L’« instantané » du profil du visiteur associé à un ID de transaction peut être supprimé après 90 jours, bien que le calendrier réel de suppression varie. Si nécessaire, vous pouvez contacter le service à la clientèle d’Adobe pour prolonger la fenêtre d’expiration. Si une ligne est transférée après l’intervalle d’expiration de l’ID de transaction, les données dans la ligne sont enregistrées, mais aucune des données de l’« instantané » du profil du visiteur ne sera créditée si le profil a été supprimé.

## Ventilations et segmentation à l’aide des ID de transaction {#section_A4D39291200A42C496122FDB9EF6EF68}

Les eVars transférées à l’aide des sources de données peuvent servir à ventiler les eVars contenues dans l’« instantané » du profil du visiteur. Puisque ces données sont distinctes du profil du visiteur actif, vous ne pouvez pas les ventiler en fonction d’autres eVars qui peuvent avoir été définies avant ou après l’ID de transaction, mais sans faire partie de l’« instantané ».

Il existe plusieurs moyens d’afficher les données de visiteur associées qui ne peuvent pas être disponibles dans une ventilation. Dans les rapports de l’entrepôt de données, vous pouvez afficher les données des ID de transaction avec un ID de visiteur qui correspond aux autres correspondances du visiteur. Bien que ces lignes d’ID de transaction soient exclues lors du dénombrement des visites/visiteurs par jour, elles sont utilisées pour le calcul de la plupart des mesures et dans les segments.

Par conséquent, vous pouvez créer un segment de visiteurs qui accomplissent un certain événement hors ligne qui a été transféré à l’aide des sources de données d’ID de transaction. Ceci renverra tout ce que le visiteur a accompli avant et après l’événement de l’ID de transaction.

De même, la participation des visiteurs vous permet de voir comment les props et les eVars de l’ID de transaction ont précédé un événement en ligne ou comment les props et eVars en ligne ont précédé un événement d’ID de transaction.
