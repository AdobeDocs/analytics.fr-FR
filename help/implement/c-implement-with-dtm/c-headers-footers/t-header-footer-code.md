---
description: Utilisez Dynamic Tag Management pour ajouter du code d’en-tête et de pied de page qui détermine le chargement de code JavaScript et de contenu de page sur votre site. Vous devez placer le code d’en-tête et de pied de page dans chaque page de votre site, quelle que soit l’option d’hébergement utilisée.
keywords: Implémentation d'Analytics ; implementation method ; gestion dynamique des balises ; dtm ; code ; code de page ; code d'en-tête ; code de pied de page ; code incorporé ; embed, panneau ; embed
seo-description: Utilisez Dynamic Tag Management pour ajouter du code d’en-tête et de pied de page qui détermine le chargement de code JavaScript et de contenu de page sur votre site. Vous devez placer le code d’en-tête et de pied de page dans chaque page de votre site, quelle que soit l’option d’hébergement utilisée.
seo-title: Ajout de code d’en-tête et de pied de page
solution: Analytics
title: Ajout de code d’en-tête et de pied de page
topic: Développeur et mise en œuvre
uuid: 23 d 89 ae 0-340 a -4 b 12-91 d 1-953 b 4613 c 98 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ajout de code d’en-tête et de pied de page

Utilisez Dynamic Tag Management pour ajouter du code d’en-tête et de pied de page qui détermine le chargement de code JavaScript et de contenu de page sur votre site. Vous devez placer le code d’en-tête et de pied de page dans chaque page de votre site, quelle que soit l’option d’hébergement utilisée.

Comme Dynamic Tag Management inclut un fragment de code dans l’en-tête et le pied de page, vous pouvez exécuter des règles au début ou à la fin d’une page. Vous pouvez ainsi mettre en œuvre des outils de test et d’autres technologies, tout en conservant un contrôle total sur le suivi de vos pages.

Dynamic Tag Management crée du code incorporé d’évaluation et de production afin que vous puissiez tester vos modifications dans votre environnement d’évaluation avant de les appliquer dans votre environnement de production.

>[!IMPORTANT]
>
>Pour une implémentation réussie, il est essentiel de suivre ces instructions telles qu'elles apparaissent dans l'aide d'Adobe. Specifically, you must place the header code in the `<head>` section of your document templates. Also, you must place the footer code just before the closing `</body>` tag. Le placement de ce code incorporé à un autre emplacement de vos balises, l’utilisation de méthodes asynchrones pour modifier le code incorporé, ou l’encapsulation du code incorporé *ne constitue pas* une mise en œuvre prise en charge par Dynamic Tag Management. Le code incorporé doit être implémenté exactement tel qu’il a été fourni.
>
>Une mise en œuvre non prise en charge provoquera des résultats inattendus et empêchera le service à la clientèle et l’ingénierie de vous aider.

1. Dans l’interface de Dynamic Tag Management, ouvrez l’onglet [!UICONTROL Incorporer], sélectionnez votre option d’hébergement (telle qu’Akamai), puis activez le sélecteur.

   Résultat 1. Copiez le code d’en-tête de production fourni dans l’onglet Incorporer de Dynamic Tag Management et placez-le au sein de la section [!DNL HEAD] de votre site HTML.

   ![](assets/dtm-embed.png)

   Place the code as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] d’ouverture. Ce fragment de code doit être ajouté à chaque page de votre site de production actif.

   >[!NOTE]
   >
   >Production embed code reflects only the published items in that [property](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123). Néanmoins, le code incorporé pour l’évaluation reflète tous les éléments de la propriété associée, que l’état soit Publié ou Annuler la publication. Pour tester les éléments Annuler la publication sur votre site de production, activez localement l’évaluation dans la console en suivant les instructions du [Test des règles Annuler la publication pour l’hébergement Akamai](../../../implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md#task_B397167F9E9B4487957AD6CE2AD47259).

1. Copiez le code de pied de page de production et collez-le dans la section [!DNL BODY] du code HTML de votre site.

   Place the code as close to the [!DNL </body>] d’ouverture.
1. Copiez le code d’en-tête et de pied de page d’évaluation, puis répétez les étapes précédentes pour votre site d’évaluation.

   >[!NOTE]
   >
   >The difference between production and staging code snippets is the addition of [!DNL -staging] to the filename in the staging version. Le code de pied de page est identique dans les versions d’évaluation et de production. 

