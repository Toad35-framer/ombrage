# Changelog Ombrage

## v1.2.0 — Novembre 2026 — Réglages dans les exports

### Note de synthèse DOCX / PDF
- Nouvelle case **« Inclure les réglages enregistrés »**, cochée par
  défaut : ajoute une section « Réglages enregistrés » entre
  « Illustrations » et « Méthode et limites »
- Le bloc reprend tous les réglages de l'étude (site, façade, fenêtre,
  support, lames, dates, chantier, indice) en texte à espacement fixe,
  prêt à être copié-collé
- Mode d'emploi rappelé en tête de section

### Réglages enregistrés
- « Charger ces réglages » accepte maintenant un texte copié depuis un
  PDF ou un DOCX : le bloc est retrouvé automatiquement, même si le
  texte collé contient d'autres lignes ou des retours à la ligne en trop

## v1.1.0 — Novembre 2026 — Exports DOCX, PDF et DXF

### Nouveaux champs
- **Nom du chantier** (étape 1) et **indice de la fenêtre** (étape 2,
  repère de menuiserie extérieure, ex. MEX 12), gardés avec les réglages
- Indice affiché en pastille dans l'étape 2 et dans la barre d'état

### Note de synthèse DOCX / PDF
- Document A4 portrait aux couleurs d'Alti-Vent : bandeau bleu avec le
  nom du chantier en titre, l'adresse et les coordonnées GPS en
  sous-titre ; pastilles indice MEX / orientation / date de l'étude
- Tableaux de toutes les données (site, menuiserie, support, lames)
- Résultats : instant simulé, jours de référence été / hiver avec
  appréciation colorée, indice d'efficacité, dernière optimisation
- Illustrations : photo aérienne avec tracé du mur, vue 3D, coupe,
  profil de la journée, carte annuelle
- Méthode, limites, avertissement et licence ; en-tête et pied de page
  numérotés sur chaque page
- DOCX écrit directement au format Office Open XML (JSZip), PDF créé
  avec jsPDF, sans serveur

### Plan DXF
- Vue de face, profil et vue en plan avec flèche du nord, disposés en
  projection
- Dessin en vraie grandeur (1 unité = 1 mm), échelle 1/1 à 1/50 pour la
  taille des textes, cotes et hachures
- Case « Avec les cotes » ; un calque par famille d'éléments ; cartouche
- Format DXF R12 (AC1009) pour la compatibilité la plus large

### Divers
- Tuiles IGN chargées en mode CORS pour pouvoir être reprises dans les
  exports
- Guide de démarrage : nouvel écran « Exporter »

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
