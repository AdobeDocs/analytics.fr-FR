---
description: Questions fréquentes sur le suivi des liens dans Activity Map.
title: Questions fréquentes sur le suivi des liens
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 2a20ce50f773c82856da59154bb212f1fca2b7ea
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 44%

---

# Questions fréquentes sur le suivi des liens

Questions fréquentes sur le suivi des liens dans Activity Map.

>[!CAUTION]
>
>En activant le suivi Activity Map, **vous pouvez collecter des données d’informations d’identification personnelle (PII).** Ces données peuvent être utilisées seules ou avec d’autres informations pour identifier, contacter ou localiser une seule personne, ou pour identifier une personne dans son contexte.

Vous trouverez ci-dessous certains cas connus de collecte des données relatives aux informations d’identification personnelles à l’aide du suivi Activity Map :

* Liens `Mailto`. Un lien mailto est un type de lien HTML qui active le client de messagerie par défaut sur l’ordinateur afin d’envoyer un message électronique.
* Liens `User ID` qui peuvent s’afficher dans l’en-tête ou le pied de page d’un site web une fois l’utilisateur connecté.
* Dans le cas des établissements financiers, le numéro de compte peut s’afficher sous la forme d’un lien. Le fait de cliquer dessus collecte le texte du lien.
* Les sites web du secteur des soins de santé peuvent également afficher des données relatives aux informations d’identification personnelles sous la forme de liens. Le fait de cliquer sur ces liens collecte le texte du lien, et donc les données relatives aux informations d’identification personnelles.

## Quand le suivi des liens se produit-il ?

L’identification des liens et des régions de Activity Map se produit lorsque l’utilisateur clique sur une page.

## Qu’est-ce qui est suivi par défaut ?

Si un événement de clic se produit sur un élément, l’élément doit réussir certaines vérifications pour déterminer si AppMeasurement le traitera comme un lien. Ces vérifications sont les suivantes :

* Est-ce que c&#39;est `A` ou `AREA` avec une balise `href` propriété ?
* Y a-t-il un `onclick` qui définit un attribut `s_objectID` variable ?
* Est-ce que c&#39;est `INPUT` ou `SUBMIT` avec une valeur ou un texte enfant ?
* Est-ce que c&#39;est `INPUT` balise avec type `IMAGE` et un `src` propriété ?
* S&#39;agit-il d&#39;un `BUTTON`?

Si la réponse à l’une des questions ci-dessus est Oui, l’élément est considéré comme un lien et sera suivi.

>[!IMPORTANT]
>
>Les balises de bouton avec l’attribut type=&quot;button&quot; ne sont pas considérées comme des liens par AppMeasurement. Envisagez de supprimer type=&quot;button&quot; sur les balises de bouton et d’ajouter role=&quot;button&quot; ou encore send=&quot;button&quot; à la place.

>[!IMPORTANT]
>
>Une balise d&#39;ancrage avec un &quot;href&quot; commençant par &quot;#&quot; est considérée comme un emplacement cible interne par AppMeasurement, et non comme un lien (puisque vous ne quittez pas la page). Par défaut, Activity Map ne suit pas ces emplacements cibles internes. Il effectue uniquement le suivi des liens qui permettent à l’utilisateur d’accéder à une nouvelle page.

## Comment le Activity Map suit-il les autres éléments de HTML visuel ?

a. Via le `s.tl()` fonction.

Si le clic s’est produit via un `s.tl()` invocation, le Activity Map recevra également cet événement de clic et déterminera si un `linkName` variable de chaîne trouvée. Pendant `s.tl()` , ce linkName sera défini comme ID de lien Activity Map. L’élément sur lequel l’utilisateur a cliqué à l’origine de la `s.tl()` sera utilisé pour déterminer la région. Exemple :

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Via le `s_objectID` variable. Exemple :

    &quot; 
    
    &lt;img onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot; src=&quot;someimageurl.png&quot; />
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot;>
    Lier le texte ici
    &lt;/a>
    
    &quot;

>[!IMPORTANT]
>
>Un point-virgule de fin (;) est requis lors de l’utilisation `s_objectID` en Activity Map.

## Pouvez-vous me donner des exemples de liens qui seront suivis ?

### Exemple 1

```
  <a hef="/home?lang=en>Home</a>
```

### Exemple 2

```
 <input type="submit" value="Submit"/>
```

### Exemple 3

```
  <input type="image" src="submit-button.png"/>
```

### Exemple 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### Exemple 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Pouvez-vous me donner quelques exemples de liens qui ne seront PAS suivis ?

1. Raison : la balise d’ancrage ne possède pas de valide `href`:
   `<a name="innerAnchor">Section header</a>`

1. Motif : Ni `s_ObjectID` ni `s.tl()` présent :

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Motif : Ni `s_ObjectID` ni `s.tl()` présent :

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Motif : La propriété &quot;src&quot; ne comporte pas d’élément d’entrée de formulaire :

   `<input type="image"/>`

