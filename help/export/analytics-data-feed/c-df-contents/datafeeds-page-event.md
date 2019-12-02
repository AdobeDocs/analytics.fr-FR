---
description: Table de recherche permettant de déterminer le type d’un accès d’après la valeur page_event.
keywords: Data Feed;page;event;page_event;post_page_event
solution: Analytics
title: Recherche d’événement de page
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Recherche d’événement de page

Table de recherche permettant de déterminer le type d’un accès d’après la valeur page_event.

| Type d’accès | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Pages vues | 0 : Tous les appels et `trackState` appels de pages vues depuis les kits SDK mobiles | Même valeur que `post_page_event` |
| Suivi des liens  | 10 : Liens et `trackAction` appels personnalisés dans les<br>11 du kit SDK mobile : Liens<br>de téléchargement 12 : Liens de sortie | 100 : Liens et `trackAction` appels personnalisés dans le SDK mobile<br>101 : Liens<br>de téléchargement 102 : Liens de sortie |
| Vidéo Jalon | 31 : Media start<br>32 : Mises à jour des médias (aucun autre traitement de variable)<br>33 : Mises à jour des médias (avec d’autres variables) | 76 : Début<br>du média 77 : Mises à jour des médias (aucun autre traitement de variable)<br>78 : Mises à jour des médias (avec d’autres variables) |
| Vidéo – Pulsation | 50 : Démarrage du flux média (non Primetime)<br>51 : Fermeture du flux média (non Primetime)<br>52 : Balayage du flux média (non Primetime)<br>53 : Le flux média reste en vie (non Primetime)<br>54 : Démarrage de publicité dans le flux média (non Primetime)<br>55 : Flux média - fermeture de publicité (non Primetime)<br>56 : Balayage publicitaire dans les flux média (non Primetime)<br>60 : Début<br>61 du flux média Primetime : Le flux média Primetime ferme<br>62 : Balayage<br>du flux média Primetime 63 : Le flux média Primetime reste en vie<br>64 : Début<br>65 du flux publicitaire média Primetime : Fin<br>66 du flux publicitaire média Primetime : Balayage publicitaire en temps réel | Même valeur que `post_page_event` |
| Enquête | 40 : Tout appel généré par Survey | 80 : Tout appel généré par Survey |
| Analytics pour Target | 70 : Accès incluant les données d’activité Target | Même valeur que `post_page_event` |
