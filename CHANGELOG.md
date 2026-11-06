# Changelog Ombrage

## v1.0.0 — Novembre 2026 — Première version publique

Outil web de calcul de la course du soleil et de simulation de l'ombre
portée d'un brise-soleil à lames sur une fenêtre.

### Calcul
- Position du soleil (azimut, hauteur) selon les formules NOAA / Meeus,
  avec correction de réfraction atmosphérique
- Rayonnement direct par ciel clair (modèle de Meinel, masse d'air de
  Kasten-Young)
- Ombre sur le vitrage par lancer de rayons : lames, consoles et
  embrasure de la menuiserie
- Pourcentage de vitrage au soleil, à l'instant et sur la journée
- Indice d'efficacité été / hiver avec curseur de priorité

### Site
- Recherche par adresse avec suggestions et géocodage inverse
  (API Géocodage IGN Géoplateforme)
- Champ « coller GPS » et saisie manuelle latitude / longitude
- Photo aérienne IGN (BD ORTHO, WMTS) avec repli automatique sur la
  pyramide `PM_0_19`
- **Tracé du mur sur la photo** : remplissage automatique de
  l'orientation de la façade, bouton « Inverser l'extérieur »
- Repositionnement du site d'un clic sur la photo

### Géométrie
- Fenêtre : largeur, hauteur / allège / linteau liés, retrait de la
  menuiserie
- Support : accroche / bandeau liés, inclinaison, longueur, débords
  gauche et droite, largeur et hauteur des consoles
- Lames : nombre, largeur, épaisseur, inclinaison sur le support

### Visualisation
- Vue 3D (Three.js r128) avec ombres portées, vues Perspective / Face /
  Côté / Vue du soleil
- Défilement par heures ou par jours, vitesse réglable
- Coupe verticale cotée avec rayons solaires selon l'angle de profil
- Profil de la journée et carte annuelle cliquable

### Optimisation
- Inclinaison des lames, inclinaison du support, longueur du support,
  ou réglage combiné
- Courbe de l'indice selon la valeur testée, retour aux valeurs
  précédentes

### Confort
- Charte graphique commune avec Alti-Vent (cartes numérotées par étape)
- Guide de démarrage en 8 écrans au premier lancement
- Réglages gardés dans le navigateur, copier / coller entre postes
- Licence Creative Commons BY-NC-ND 4.0 et disclaimer intégrés
