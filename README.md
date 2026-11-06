# Ombrage — Simulation d'ombrage de brise-soleil à lames

Outil web de calcul de la **course du soleil** et de simulation de l'**ombre portée d'un brise-soleil à lames** sur une fenêtre. Il sert à dimensionner et régler un brise-soleil pour **bloquer le soleil d'été** tout en **laissant entrer le soleil d'hiver**.

> ⚠ **Avertissement** : Cet outil est fourni à des fins pédagogiques et d'assistance au pré-dimensionnement. Les résultats doivent être vérifiés par un professionnel qualifié.

---

## 🌤 Présentation

Un brise-soleil bien réglé arrête le soleil haut de l'été et laisse passer le soleil bas de l'hiver. Le bon réglage dépend de la latitude du site, de l'orientation exacte de la façade, des dimensions de la fenêtre et de la géométrie des lames. Trouver ce réglage à la main demande de nombreux tracés d'ombre, date par date et heure par heure.

**Ombrage** automatise ces tracés :

- Calcul de la **position du soleil** (azimut, hauteur) pour n'importe quel lieu, date et heure
- Saisie du site par **adresse** ou **coordonnées GPS**, avec **photo aérienne IGN**
- **Tracé du mur sur la photo** : l'orientation de la façade par rapport au nord se remplit automatiquement
- **Vue 3D** avec ombres portées en temps réel, animation par heures ou par jours
- **Coupe verticale** cotée avec les rayons solaires selon l'angle de profil
- **Pourcentage de vitrage au soleil**, à l'instant et sur la journée, en tenant compte de la largeur, de l'épaisseur, du nombre et de l'inclinaison des lames
- **Optimisation automatique** de l'inclinaison des lames, de l'inclinaison du support et de la longueur du support
- **Export d'une note de synthèse** A4 en **DOCX** ou **PDF**, et d'un **plan DXF** (vue de face, profil, vue en plan) importable dans la plupart des logiciels de dessin

L'outil tourne **intégralement dans le navigateur** : pas de serveur, pas d'inscription, pas d'envoi de données. Il suffit d'un navigateur récent et d'une connexion internet (pour la photo aérienne, la recherche d'adresse et le moteur 3D).

---

## ✨ Fonctionnalités

### ① Site
- **Nom du chantier** (repris en titre des exports)
- **Recherche par adresse** avec suggestions (API Géocodage IGN Géoplateforme)
- Champ **« coller GPS »** (`48.1173, -1.6778`, `48,1173 ; -1,6778`…) et saisie manuelle latitude / longitude
- **Photo aérienne IGN** (BD ORTHO) avec zoom et déplacement
- Bouton **Déplacer le point** pour placer le site d'un clic, avec géocodage inverse de l'adresse
- Bouton **Tracer le mur** : deux clics le long du nu de la façade donnent son orientation par rapport au nord
- Bouton **Inverser l'extérieur** si la flèche « ext. » pointe vers le bâtiment
- Direction du soleil à l'heure affichée tracée sur la photo

### ② Façade et fenêtre
- **Indice de la fenêtre** (repère de menuiserie extérieure, ex. MEX 12)
- Orientation de la façade (0° = nord, 90° = est, 180° = sud, 270° = ouest), avec boussole
- Largeur de la fenêtre
- Hauteur, altimétrie d'allège et altimétrie de linteau **liées** (la modification de l'une met à jour les autres)
- Retrait de la menuiserie (ombre de l'embrasure)

### ③ Brise-soleil
- **Support** : altimétrie d'accroche et bandeau au-dessus du linteau (liés), inclinaison, longueur, débords gauche et droite, largeur et hauteur des consoles
- **Lames** : nombre, largeur, épaisseur, inclinaison sur le support

### ④ Simulation 3D
- Ombres portées sur la façade, le vitrage et le sol
- Vues **Perspective**, **Face**, **Côté** et **Vue du soleil**
- Date et heure au choix, raccourcis 21 juin / équinoxe / 21 décembre / maintenant
- **Défilement** par heures ou par jours à heure fixe, vitesse réglable

### ⑤ Coupe verticale
- Coupe cotée au milieu de la fenêtre : allège, linteau, accroche, avancée, inclinaisons
- Rayons solaires selon l'angle de profil : rayons qui atteignent le vitrage en trait plein, rayons arrêtés en pointillé

### ⑥ Optimisation
- Jours de référence été et hiver modifiables
- Curseur de priorité entre **apports d'hiver** et **protection d'été**
- Optimisation de l'inclinaison des lames, de l'inclinaison du support, de la longueur du support, ou des trois ensemble
- Courbe de l'indice selon la valeur testée et retour aux valeurs précédentes en un clic

### ⑦ Analyse
- Pourcentage de la surface vitrée au soleil à l'instant affiché
- Bilan des jours de référence : part du rayonnement direct qui atteint le vitrage et énergie reçue en kWh/m² par ciel clair
- **Indice d'efficacité** sur 100
- Profil de la journée heure par heure
- **Carte annuelle** (le 21 de chaque mois, de 4 h à 22 h), cliquable

### ⑧ Exports
- **Note de synthèse DOCX ou PDF** (A4 portrait, charte Alti-Vent) :
  - titre = nom du chantier, sous-titre = adresse et coordonnées GPS
  - pastilles : indice de la menuiserie, orientation de la façade, date de l'étude
  - tableaux de toutes les données saisies (site, menuiserie, support, lames)
  - résultats : instant simulé, jours de référence été / hiver, indice d'efficacité, dernière optimisation
  - illustrations : photo aérienne avec tracé du mur, vue 3D, coupe, profil de la journée, carte annuelle
  - case **« Inclure les réglages enregistrés »** (cochée par défaut) : ajoute, entre les illustrations et la méthode, le bloc de réglages complet à recopier dans « Réglages enregistrés » → « Charger ces réglages » pour retrouver, retravailler ou vérifier l'étude
  - méthode, limites, avertissement et licence
- **Plan DXF** (format R12, lisible par AutoCAD, DraftSight, BricsCAD, LibreCAD, ArchiCAD, Revit, SketchUp Pro…) :
  - vue de face (depuis l'extérieur), profil (coupe au milieu de la fenêtre) et vue en plan avec flèche du nord, disposées en projection
  - dessin en **vraie grandeur** (1 unité = 1 mm)
  - choix de l'échelle (1/1, 1/10, 1/20, 1/25, 1/50) : elle règle la hauteur des textes (2,5 mm imprimés), des titres, des cotes et des hachures
  - case **« Avec les cotes »** : cotes de largeur, débords, hauteur, avancée, niveaux d'altimétrie et caractéristiques des lames
  - un calque par famille : `MUR`, `MUR_HACHURES`, `MENUISERIE`, `VITRAGE`, `SUPPORT`, `CONSOLES`, `LAMES`, `AXES`, `COTES`, `TEXTES`
  - cartouche texte : chantier, menuiserie, orientation, échelle, date
- Fichiers nommés d'après le chantier et la menuiserie, par exemple `Residence-Les-Pins_MEX-12_ombrage.pdf`

### Confort
- **Guide de démarrage** au premier lancement, réaffichable à tout moment
- Réglages gardés dans le navigateur, copiables pour les transmettre à un autre poste

---

## 🚀 Utilisation

### Option 1 — En ligne (recommandé)

L'outil est publié via GitHub Pages :

👉 **https://Toad35-framer.github.io/ombrage/**

### Option 2 — En local

1. Téléchargez le fichier [`index.html`](./index.html) (ou clonez ce dépôt)
2. Ouvrez-le dans un navigateur récent (Chrome, Firefox, Edge, Safari)
3. Une connexion internet est nécessaire pour la photo aérienne, la recherche d'adresse et le moteur 3D

L'outil est entièrement contenu dans un seul fichier HTML : aucune installation, aucune dépendance à installer manuellement (Three.js, JSZip et jsPDF sont chargés via CDN à la volée).

---

## 🧭 Méthode de calcul

| Élément | Mise en œuvre |
|---|---|
| Position du soleil | Formules NOAA d'après J. Meeus, *Astronomical Algorithms* : déclinaison, équation du temps, angle horaire, azimut et hauteur |
| Réfraction atmosphérique | Correction de Saemundsson près de l'horizon |
| Rayonnement direct | Modèle de ciel clair de Meinel avec masse d'air de Kasten-Young, pondéré par l'incidence sur la façade |
| Ombre sur le vitrage | Lancer de rayons depuis une grille de points sur le vitrage vers le soleil, intersection avec chaque lame, chaque console et l'embrasure |
| Bilan journalier | Part du rayonnement direct reçu par le vitrage, comparée à la même fenêtre sans brise-soleil |
| Indice d'efficacité | Moyenne pondérée (curseur de priorité) entre la part reçue en hiver et la part arrêtée en été |
| Optimisation | Balayage de chaque paramètre sur sa plage, les autres réglages restant fixes |

### Conventions
- Cotes en **millimètres**, angles en **degrés**
- **Orientation de la façade** : direction vers laquelle elle regarde, depuis le nord, sens horaire
- **Inclinaison du support** : 0° = de niveau, positif = descend vers l'extérieur
- **Inclinaison des lames** : mesurée par rapport au support, positif = bord extérieur relevé
- **Gauche / droite** : vues depuis l'extérieur
- Lames réparties à pas égal sur la longueur du support ; une console à chaque extrémité

### Limites connues
- Seul le **rayonnement direct** est pris en compte : le rayonnement diffus et le rayonnement réfléchi ne sont pas calculés
- Le ciel est supposé **clair** : la nébulosité réelle du site n'est pas prise en compte
- Les **masques lointains** (bâtiments voisins, arbres, relief) ne sont pas modélisés
- Les lames sont supposées **opaques**
- L'heure saisie est l'**heure légale du poste** : pour un site situé dans un autre fuseau horaire, régler l'heure en conséquence
- L'outil ne fait **aucun calcul de structure** (charges, vent, fixations)
- Les cotes du DXF sont dessinées (lignes et textes), elles ne sont **pas associatives** : elles ne suivent pas une modification de la géométrie dans le logiciel de dessin
- Le format **DWG** (format fermé d'Autodesk) n'est pas produit : le DXF s'ouvre et s'enregistre en DWG dans les logiciels de DAO
- La photo aérienne et la recherche d'adresse IGN couvrent la France

---

## 📂 Structure du dépôt

```
ombrage/
├── index.html              ← l'outil complet, version en cours (autonome, ~130 KB)
├── ombrage-v1.2.0.html     ← archive de la version 1.2.0
├── ombrage-v1.1.0.html     ← archive de la version 1.1.0
├── ombrage-v1.0.0.html     ← archive de la version 1.0.0
├── CHANGELOG.md            ← historique des versions
├── LICENSE                 ← licence CC BY-NC-ND 4.0
└── README.md               ← ce fichier
```

---

## 🔧 Sources de données

- **IGN Géoplateforme — WMTS** : photos aériennes (BD ORTHO)
- **IGN Géoplateforme — Géocodage** : recherche par adresse et géocodage inverse
- **Three.js r128** : moteur 3D (chargé via CDN)
- **JSZip 3.10** et **jsPDF 2.5** : création des fichiers DOCX et PDF dans le navigateur (chargés via CDN)
- **J. Meeus, *Astronomical Algorithms*** et **NOAA Solar Calculator** : formules de position du soleil

---

## 📜 Licence

[![Licence CC BY-NC-ND 4.0](https://licensebuttons.net/l/by-nc-nd/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.fr)

Cette œuvre est mise à disposition sous **licence Creative Commons
Attribution - Pas d'Utilisation Commerciale - Pas de Modification 4.0
International** ([CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.fr)).

Vous pouvez **partager** (copier et redistribuer) l'œuvre par tous moyens
et sous tous formats, à condition de :

- **Attribution (BY)** — créditer l'œuvre (Jean Pineau, Ombrage) et inclure un lien vers la licence
- **Pas d'utilisation commerciale (NC)** — usage non commercial uniquement
- **Pas de modification (ND)** — pas de distribution d'œuvre modifiée

Voir [LICENSE](./LICENSE) pour le texte complet.

> **Avertissement** — Cet outil est fourni à des fins pédagogiques et
> d'assistance au pré-dimensionnement. Les résultats doivent être
> vérifiés par un professionnel qualifié. L'auteur ne saurait être tenu
> responsable des conséquences d'une utilisation du logiciel pour un
> dimensionnement réel sans vérification indépendante.

---

## 👤 Auteurs

- **Jean Pineau** — Charpentier bois (Bretagne) — conception et spécifications
- **Claude** (Anthropic) — assistant de développement

---

## 🤝 Contribution

Les retours, suggestions et corrections sont bienvenus via les **Issues** GitHub ou en m'envoyant directement un message. Si vous identifiez un cas où l'outil donne un résultat erroné par rapport à un tracé d'ombre manuel, merci de joindre les réglages (bouton « Copier les réglages »), la date, l'heure et la valeur attendue.
