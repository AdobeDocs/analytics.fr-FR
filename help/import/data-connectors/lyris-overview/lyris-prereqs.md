---
description: Décrit les conditions préalables à une intégration réussie.
seo-description: Décrit les conditions préalables à une intégration réussie.
seo-title: Conditions préalables à l'intégration
solution: Analytics
title: Conditions préalables à l'intégration
uuid: ac 93 bf 4 d-a 071-4 fac -9 d 42-c 4856463 cbb 6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Conditions préalables à l'intégration{#integration-prerequisites}

Décrit les conditions préalables à une intégration réussie.

Avant d'activer cette intégration, passez en revue les éléments suivants par rapport à vos déploiements d'Adobe Analytics et de votre logiciel de messagerie.

Cela garantit que les bonnes pratiques et les prérequis appropriés sont en place avant l'activation, ce qui entraîne une intégration optimale et réussie.

## Conditions préalables pour Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Spécifique à la suite de rapports**: Soyez prudent lorsque cette intégration est spécifique à la suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports souhaitée avant d'activer l'intégration.
* **Variables Analytics disponibles et configurées**: Cette intégration requiert des événements personnalisés et des evars personnalisées, ainsi que des événements supplémentaires et des evars supplémentaires.

   Voir [Configuration des variables Analytics pour Lyris](../lyris-overview/lyris-analytics-variables.md#task-e70a62dc096d4f548d5070a67822f5e7)

* **Représentant autorisé**: Soyez prudent lorsque l'activation de cette intégration peut conduire votre entreprise à encourir des frais conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l'un des partenaires approuvés d'Adobe, le cas échéant. En activant cette intégration, vous déclarez par les présentes que vous êtes un représentant autorisé de votre société ; De ce fait, votre entreprise accepte de payer les frais, le cas échéant, définis dans l'accord de service décrit ci-dessus.
* **Entrepôt de données Adobe Analytics**: Cette intégration nécessite l'activation de l'entrepôt de données Adobe Analytics pour générer des segments de remarketing. Si vous n'avez pas activé l'entrepôt de données, contactez Adobe pour plus de détails.
* **ID de destinataire**: L'intégration requiert que nous capturions et stockions un « identifiant visiteur » dans une variable Analytics (evar). L'identifiant visiteur (souvent appelé « ID de destinataire ») est une représentation codée ou numérique d'une adresse électronique du système Lyris. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur le site (abandon de panier, achats, etc.) extrait dans le système Lyris et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une evar à cet effet lorsque vous y êtes invité.
* **Suivi externe**: Si vous ne suivez pas actuellement la meilleure pratique d'activation du suivi externe pour chaque campagne par courriel envoyée, vous devez le faire pour garantir une intégration réussie. Pour plus d'informations, reportez-vous à la section Lyris ci-dessous.
* **Respect de la vie privée**: Vous devez comprendre qu'en activant le suivi des identifiants visiteur ou visiteur, cette fonction peut suivre les informations personnellement identifiables des visiteurs de votre site. Ceci a des implications en matière de confidentialité, exigeant l'implémentation des procédures appropriées par votre organisation, comme l'avis et le consentement des visiteurs de votre site.

## Conditions préalables pour Lyris emaillabs {#section-84abae9401224a3699fed861f715ebde}

* **Compte Lyris valide**: Pour utiliser cette intégration de Connecteur de données, vous devez disposer d'un compte Lyplastique valide.
* **Informations du compte**: Vous aurez besoin des informations suivantes sur votre compte Lyris au cours de cette configuration de l'intégration :

   * *Clé API Lyris*: Utilisé pour la population de données
   * *Paramètres de chaîne de requête*: Elles sont ajoutées dans l'URL de la page d'entrée pour l'ID de message et l'ID de destinataire (identifiant visiteur).
   * *Lyris Server/URL*: Valeur du serveur que vous utilisez dans le système Lyris
   * *Lyris Site ID*: Il s'agit également de « ID client ». Il s'agit de la valeur unique de votre instance de Lyris HQ. Il se trouve sous « Informations client » dans la section « Page d'accueil du compte » de emaillabs.

