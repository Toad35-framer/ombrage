# Changelog Ombrage

## v2.1.0 — Novembre 2026 — Soutien Ko-fi

- Bouton discret **« ☕ Payer un coup »** dans l'en-tête et lien dans le pied de page, vers https://ko-fi.com/jeanpineau (nouvel onglet)
- Compteur d'utilisations local (`nb_utilisations_ombrage` dans le localStorage du navigateur), +1 à chaque ouverture ; **aucune donnée envoyée**
- Tous les 10 lancements, petite fenêtre de remerciement non bloquante (message tiré au hasard parmi 6), boutons « Payer un café » et « Plus tard »
- Aucun changement du calcul ni des exports

## v2.0.0 — Novembre 2026 — Matériaux, profils, optimisation à l'instant T et durabilité

### Matériau et environnement (étape 1)
- Choix du matériau : **aluminium**, **acier protégé** ou **bois**
- Bois : essence, climat d'humidification (FD P 20-651), durée de vie visée L1 à L3
- Acier protégé : catégorie de corrosivité C1 à CX (NF EN ISO 12944-2)
- Aluminium : atmosphère extérieure E11 à E19 (NF P 24-351)

### Profils des consoles et des lames
- Rectangulaire / plat, tube carré ou rectangulaire, tube rond, cornière, U, T, I ou H (bois : rectangulaire)
- Champs propres à chaque profil, rotation 90° ou position (4 positions)
- Console droite symétrique ou identique à la console gauche
- Bouton **?** : sections courantes en Europe, un clic applique la ligne
- Ombre, 3D, coupe et DXF calculés avec la section réelle

### Optimisation à l'instant T
- La carte « Optimisation », le curseur de priorité et l'indice d'efficacité sont supprimés
- Bouton **⟳** à côté de 8 réglages : accroche, inclinaison, longueur et débords du support, nombre, largeur et inclinaison des lames
- Ombre maximale sur le vitrage à la date et à l'heure affichées, valeur la plus économique, les autres réglages restant fixes
- Support traité en plaque pleine pour les boutons du support ; lames bois bornées à 30° minimum
- Résultat sous le champ avec **Annuler** ; optimisations reprises dans la note de synthèse

### Durabilité
- Alertes avec référence (norme, paragraphe, page) : NF DTU 31.1 P1-1, FD P 20-651, Recommandations PACTE 2020, NF EN ISO 12944-2 et -3, NF P 24-351, guide AQC 2014
- Bois : pentes, délardement proposé, retombée, bois de bout, assemblages, 30° minimum des lames, élancement, classe d'emploi et longévité de l'essence ; points singuliers à cocher
- Métal : détection des creux qui retiennent l'eau, faces horizontales, corps creux, protection, dilatation, corrosion galvanique
- Coupe : angles réels α et β en couleur ; nouveau panneau **Détails de durabilité** (sections agrandies)
- DXF : détails agrandis à 1/5, angles cotés, calques `COTES_ANGLES`, `DETAILS`, `EAU`

### Analyse et exports
- Bilans été / hiver conservés pour justifier la conception
- Note DOCX / PDF : nouvelle section « Durabilité », matériau et profils, détails en illustration
- Les réglages v1.x se rechargent (consoles et lames rectangulaires, bois)

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
