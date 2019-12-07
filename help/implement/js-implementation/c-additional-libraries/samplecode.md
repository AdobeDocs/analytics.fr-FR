---
description: Ces exemples illustrent l’utilisation d’une balise d’image générée par un serveur dans un exemple de page HTML.
keywords: Analytics Implementation;variables
title: Exemple de code
topic: Developer and implementation
uuid: 47e5e82c-cfb2-4912-919b-720b2ee852ba
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Exemple de code

Ces exemples illustrent l’utilisation d’une balise d’image générée par un serveur dans un exemple de page HTML.

Le tableau ci-dessous présente les valeurs utilisées dans l’exemple.

| Variable | Valeur |
|---|---|
| pageName | Order Confirmation (Confirmation de commande) |
| UTL active | https://www.somesite.com/cart/confirmation.asp |
| events | purchase,event1 |
| c1 | Registered |
| purchaseID | 0123456 |
| products | Books;Book Name;1;19.95 |
| state | CA |
| zip | 90210 |
| nombre aléatoire | 123456 |

## Exemple 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

L’exemple ci-dessous illustre une balise d’image côté serveur. Le nombre aléatoire mis en surbrillance empêche la mise en mémoire cache de l’image.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456.
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## Exemple 2 {#section_726D12029583428BA853043F988ED1B8}

L’exemple ci-dessous illustre une balise d’image JavaScript minimale.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456.
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 
```

