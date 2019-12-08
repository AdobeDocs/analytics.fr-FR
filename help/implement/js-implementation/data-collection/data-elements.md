---
description: Vous pouvez capturer les valeurs d’éléments de formulaire, comme des cases d’option et des éléments de case à cocher, dans des rapports. Vous pouvez ainsi analyser les choix les plus populaires effectués dans vos formulaires en ligne.
keywords: Analytics Implementation
title: Collecte de données à partir d’éléments de formulaire
topic: Developer and implementation
uuid: e0c13b96-e1ca-4744-a912-60ca2b8f25c3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Collecte de données à partir d’éléments de formulaire

Vous pouvez capturer les valeurs d’éléments de formulaire, comme des cases d’option et des éléments de case à cocher, dans des rapports. Vous pouvez ainsi analyser les choix les plus populaires effectués dans vos formulaires en ligne.

Par exemple, dans le cas d’une case d’option permettant à un utilisateur d’indiquer son genre musical préféré (rock, rap, classique, jazz), vous pouvez capturer cette réponse dans une variable afin de déterminer les préférences musicales globales de votre base d’utilisateurs.

Pour capturer ces données, la meilleure méthode dépend du mode de traitement des formulaires. Elle varie également selon que les sélections de formulaire que vous souhaitez capturer sont disponibles ou non dans la chaîne de requête sur la page qui suit l’envoi du formulaire. Les exemples de cet article sont en langage PHP. Vous pouvez toutefois adapter ces concepts à un autre langage, en fonction de votre environnement serveur.

Ces informations s’adressent aux utilisateurs expérimentés qui maîtrisent à la fois les opérations de création de rapports et d’implémentation. N’apportez des modifications à votre implémentation que si vous êtes parfaitement conscient des conséquences. Si des changements d’implémentation s’avèrent nécessaires, contactez le responsable de compte de votre entreprise.

## Méthode GET {#section_7A2B35822BFF4F6EB57940B31AE6303A}

Si votre formulaire utilise une méthode [!UICONTROL GET] pour envoyer des données, vous avez accès aux données de votre choix dans la chaîne de requête de l’URL sur la page qui suit l’envoi du formulaire. Vous pouvez utiliser le module externe  [!UICONTROL getQueryParam] pour extraire automatiquement ces données de la chaîne de requête et les placer dans la variable de votre choix.

## Méthode POST {#section_56715C30EF374BA7AA12B946B50E4A9A}

Si votre formulaire utilise une méthode [!UICONTROL POST] pour envoyer des données (méthode la plus courante), les résultats de chaque élément de formulaire spécifique sont mis à votre disposition dans [!UICONTROL $_POST superglobal]. Pour capturer ces données dans une variable, vous devez déterminer le nom de l’élément de formulaire en question. En reprenant l’exemple de genre musical mentionné ci-dessus, une partie de l’élément de formulaire en question se présente comme suit :

```
<input type="radio" name="music_genre" value="rock">
```

Cette case d’option appartient à l’élément de formulaire "music_genre". Vous avez ensuite accès à la valeur sélectionnée par l’utilisateur en utilisant $_POST['music_genre']. Celle-ci peut être écrite dans une variable sur la page qui suit l’envoi du formulaire :

```js
s.eVar1="<?=$_POST['music_genre'];?>"
```

La variable [!UICONTROL eVar1] reçoit une copie de toute valeur qui a été envoyée à votre serveur par le biais du formulaire, ainsi qu’il est spécifié dans la propriété value=.

Si vous avez besoin d’informations supplémentaires sur cette méthode d’implémentation personnalisée, contactez le responsable de compte de votre société. Il peut prendre rendez-vous avec l’un de nos consultants en implémentation pour vous aider.
