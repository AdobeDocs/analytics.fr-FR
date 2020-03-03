---
description: Table de recherche permettant de déterminer le type d’un accès d’après la valeur page_event.
keywords: Data Feed;page;event;page_event;post_page_event
title: Recherche d’événement de page
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Recherche d’événement de page

Table de recherche permettant de déterminer le type d’un accès d’après la valeur page_event.

| Type d’accès | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Pages vues | 0 : Tous les appels des pages vues et les appels `trackState` des kits de développement mobile | Même valeur que `post_page_event` |
| Suivi des liens | 10 : Liens personnalisés et appels `trackAction` dans les kits de développement mobile<br>11 : Liens de téléchargement<br>12 : Liens de sortie | 100 : Liens personnalisés et appels `trackAction` dans les kits de développement mobile<br>101 : Liens de téléchargement<br>102 : Liens de sortie |
| Vidéo jalon | 31 : Démarrage du média<br>32 : Mises à jour du média (aucun autre traitement de variable)<br>33 : Mises à jour des médias (avec d’autres variables) | 76 : Démarrage du média<br>77 : Mises à jour du média (aucun traitement de variable)<br>78 : Mises à jour du média (avec d’autres variables) |
| Vidéo – Pulsation | 50 : Démarrage du flux média (hors Primetime)<br>51 : Fermeture du flux média (hors Primetime)<br>52 : Balayage du flux média (hors Primetime)<br>53 : Le flux média reste actif (hors Primetime)<br>54 : Démarrage d’une publicité dans le flux média (hors Primetime)<br>55 : Fermeture d’une publicité dans le flux média (hors Primetime)<br>56 : Balayage publicitaire dans le flux média (hors Primetime)<br>60 : Démarrage du flux média Primetime<br>61 : Fermeture du flux média Primetime<br>62 : Balayage du flux média Primetime<br>63 : Le flux média Primetime reste actif<br>64 : Démarrage d’une publicité dans le flux média Primetime<br>65 : Fermeture d’une publicité dans le flux média Primetime<br>66 : Balayage publicitaire dans le flux média Primetime | Même valeur que `post_page_event` |
| Enquête | 40 : Tout appel généré par un questionnaire | 80 : Tout appel généré par un questionnaire |
| Analytics pour Target | 70 : Accès incluant les données sur l’accès Target | Même valeur que `post_page_event` |
