---
description: Vous pouvez déployer Dynamic Tag Management en utilisant une ou plusieurs des options d’hébergement disponibles.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;hosting;hosting options;akamai;self hosting;self-hosting;ftp delivery;ftp hosting;library download
title: Configuration des options d’hébergement
topic: Developer and implementation
uuid: 04268f2d-e76f-4fe4-8fcc-f0db3a016502
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Configuration des options d’hébergement

Vous pouvez déployer [!UICONTROL Dynamic Tag Management] en utilisant une ou plusieurs des options d’hébergement disponibles.

[!UICONTROL Dynamic Tag Management] propose plusieurs options pour héberger les fichiers JavaScript requis.

Pour plus d’informations sur l’hébergement, voir [Code incorporé et options d’hébergement](https://marketing.adobe.com/resources/help/fr_FR/dtm/deployment.html) dans la documentation du produit [!UICONTROL Dynamic Tag Management].

Sous l’onglet Incorporer, sélectionnez une option d’hébergement.

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option d’hébergement </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Mise en œuvre </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> Option d’hébergement la plus simple à implémenter. </p> <p>Réseau de distribution mondialement distribué. </p> <p>Ajoute des dépendances d’infrastructure tierces (recherche DNS, disponibilité d’Akamai). </p> <p>Pour des informations plus détaillées, voir <a href="https://marketing.adobe.com/resources/help/fr_FR/dtm/akamai.html">Akamai</a> dans la documentation du produit Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Dynamic Tag Management génère des bibliothèques JavaScript personnalisées. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Dynamic Tag Management exporte les bibliothèques JavaScript personnalisées vers Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">Le site web référence les bibliothèques de Dynamic Tag Management hébergées par Akamai directement au niveau de la page. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auto-hébergement : distribution FTP </td> 
   <td colname="col2"> <p>Une méthode <span class="term">push</span> dans laquelle Dynamic Tag Management exporte directement les bibliothèques JavaScript personnalisées vers l’hôte du serveur de contenu web via le protocole FTP. </p> <p>Cette solution requiert un serveur FTP et des informations d’identification qui doivent être disponibles sur le serveur de contenu web pour publier les modifications apportées aux bibliothèques de Dynamic Tag Management. </p> <p>Pour des informations plus détaillées, voir <a href="https://marketing.adobe.com/resources/help/fr_FR/dtm/deployment_ftp.html">FTP</a> dans la documentation du produit Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Dynamic Tag Management génère des bibliothèques JavaScript personnalisées. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Dynamic Tag Management exporte les bibliothèques JavaScript personnalisées vers le serveur hôte via FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">Le site web cible référence localement les bibliothèques personnalisées de Dynamic Tag Management. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auto-hébergement : téléchargement de bibliothèque </td> 
   <td colname="col2"> <p>Une méthode <span class="term"> pull</span> dans laquelle l’application exporte les bibliothèques JavaScript personnalisées
     <!-- to Amazon S3-->. Les bibliothèques sont ensuite accessibles par un processus hébergé côté serveur. </p> <p>Elles sont en outre disponibles par le biais d’un téléchargement web à partir de l’interface de Dynamic Tag Management. </p> <p>Cette solution requiert une extraction et une publication manuelles des bibliothèques de Dynamic Tag Management ou la création d’un processus automatisé qui extrait les bibliothèques Akamai vers le serveur de contenu web. </p> <p>Bien que cette option soit celle qui prenne le plus de temps à configurer, c’est la plus sûre et la plus flexible. </p> <p>Pour vérifier si la version la plus récente de votre fichier de bibliothèque est référencée, utilisez la commande. </p> <p>Pour des informations plus détaillées, voir <a href="https://marketing.adobe.com/resources/help/fr_FR/dtm/deployment_download.html">Téléchargement de bibliothèque</a> dans la documentation du produit Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Dynamic Tag Management génère des bibliothèques JavaScript personnalisées. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Dynamic Tag Management exporte les bibliothèques JavaScript personnalisées vers Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">Les bibliothèques personnalisées de Dynamic Tag Management sont déplacées manuellement ou par programme vers le serveur de contenu web. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">Le site web cible référence localement les bibliothèques personnalisées de Dynamic Tag Management. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

Vous pouvez utiliser plusieurs options d’hébergement. Par exemple, vous pouvez héberger vos fichiers intermédiaires à l’aide d’Akamai, mais auto-héberger votre site de production. Notez que chaque type d’hébergement dispose de son propre code intégré et qu’un seul code intégré peut être ajouté à une page.
