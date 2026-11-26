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
- Choix du **matériau** (aluminium, acier protégé, bois) et du **profil** de chaque élément (rectangulaire, cornière, U, I ou H, T, tubes), avec les sections courantes en Europe
- Boutons **⟳ d'optimisation à l'instant T** à côté de chaque réglage : ombre maximale sur le vitrage à la date et à l'heure choisies, valeur la plus économique
- **Alertes de durabilité** (pentes insuffisantes, rétention d'eau, classe d'emploi du bois) avec renvoi à la norme, au paragraphe et à la page
- **Export d'une note de synthèse** A4 en **DOCX** ou **PDF**, et d'un **plan DXF** (vue de face, profil, vue en plan) importable dans la plupart des logiciels de dessin

L'outil tourne **intégralement dans le navigateur** : pas de serveur, pas d'inscription, pas d'envoi de données. Il suffit d'un navigateur récent et d'une connexion internet (pour la photo aérienne, la recherche d'adresse et le moteur 3D).

---

## ✨ Fonctionnalités

### ① Site et matériau
- **Nom du chantier** (repris en titre des exports)
- **Matériau du brise-soleil** : aluminium, acier protégé ou bois
  - bois : essence (Douglas, mélèze, pins traités, châtaignier, chêne, robinier, cumaru, ipé, tali), climat d'humidification (sec, modéré, humide), durée de vie visée (L1, L2, L3)
  - acier protégé : catégorie de corrosivité C1 à CX
  - aluminium : atmosphère extérieure E11 à E19
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
- **Support** : altimétrie d'accroche et bandeau au-dessus du linteau (liés), inclinaison, longueur, débords gauche et droite
- **Lames** : nombre, inclinaison sur le support
- **Profil** des consoles et des lames : rectangulaire / plat, tube carré ou rectangulaire, tube rond, cornière, U (UPN, UPE), T, I ou H (IPE, HEA, HEB). Le bois est limité au rectangulaire
  - les champs changent selon le profil (largeur / hauteur, ailes et épaisseur, âme et ailes…)
  - **rotation 90°** pour les sections rectangulaires, **position** (4 positions) pour les cornières, U et T
  - console droite **symétrique** (miroir) ou **identique** à la console gauche
  - bouton **?** : sections courantes en Europe (NF EN 10365, 10056-1, 10055, 10058, 10219-2 / 10210-2 ; sections de bois courantes), un clic applique la ligne
- **L'ombre est calculée avec la section réelle** de chaque profil
- **Boutons ⟳ d'optimisation à l'instant T** à côté de l'altimétrie d'accroche, de l'inclinaison et de la longueur du support, des débords gauche et droit, du nombre, de la largeur et de l'inclinaison des lames :
  - chaque bouton n'optimise que sa valeur, les autres restant fixes
  - il cherche l'**ombre maximale sur le vitrage** à la date et à l'heure affichées, puis retient la valeur **la plus économique** (support le plus court, moins de lames, lame la plus étroite, angle le plus proche de l'horizontale)
  - les boutons du support ne tiennent compte que du support, traité comme une **plaque pleine**, sans les lames
  - en bois, l'inclinaison des lames ne descend jamais sous **30°**
  - résultat affiché sous le champ (avant → après, vitrage à l'ombre), avec **Annuler**

### Durabilité
- Liste d'alertes colorées (à corriger, à vérifier, information, conforme), chacune avec **la norme, le paragraphe et la page**
- **Bois** : pente de la face supérieure des consoles (0–15° piégeante, 15–75° moyenne, 75–90° drainante) avec délardement de 15° proposé, retombée de 23 cm, bois de bout des abouts et des extrémités de lames, assemblage lames / consoles, inclinaison des lames d'au moins 30°, goutte d'eau, élancement selon l'essence, **classe d'emploi** (massivité, conception, climat) et **longévité de l'essence** comparée à la durée de vie visée
  - points singuliers à cocher : consoles capotées, extrémités des lames protégées, lames désolidarisées
- **Acier et aluminium** : détection géométrique des **creux qui retiennent l'eau** selon le profil et sa position, faces supérieures horizontales, corps creux, corrosivité (acier), finition selon l'atmosphère (aluminium), dilatation, corrosion galvanique
- **Vitrage** : rappel du risque de casse thermique sous ombre partielle
- Documents de référence : NF DTU 31.1 P1-1, FD P 20-651, Recommandations professionnelles PACTE « Éléments bois non structuraux rapportés en façade » (2020), NF EN ISO 12944-2 et -3, NF P 24-351, guide AQC « Brise-soleil métalliques » (2014). Seuls les références et les seuils sont repris, aucun extrait des documents.

### ④ Simulation 3D
- Ombres portées sur la façade, le vitrage et le sol
- Vues **Perspective**, **Face**, **Côté** et **Vue du soleil**
- Date et heure au choix, raccourcis 21 juin / équinoxe / 21 décembre / maintenant
- **Défilement** par heures ou par jours à heure fixe, vitesse réglable

### ⑤ Coupe verticale
- Coupe cotée au milieu de la fenêtre : allège, linteau, accroche, avancée, inclinaisons
- Rayons solaires selon l'angle de profil : rayons qui atteignent le vitrage en trait plein, rayons arrêtés en pointillé
- **Angles réels** cotés : α (pente du support) et β (inclinaison des lames par rapport à l'horizontale), en couleur selon les alertes
- **Détails de durabilité** : sections des consoles et d'une lame agrandies, angle par rapport à l'horizontale, minimum à respecter, délardement proposé, zones où l'eau stagne, avec les références

### ⑥ Analyse
- Pourcentage de la surface vitrée au soleil à l'instant affiché
- **Bilans été / hiver** (jours de référence modifiables) : part du rayonnement direct qui atteint le vitrage et énergie reçue en kWh/m² par ciel clair, pour justifier la conception
- Profil de la journée heure par heure
- **Carte annuelle** (le 21 de chaque mois, de 4 h à 22 h), cliquable

### ⑦ Exports
- **Note de synthèse DOCX ou PDF** (A4 portrait, charte Alti-Vent) :
  - titre = nom du chantier, sous-titre = adresse et coordonnées GPS
  - pastilles : indice de la menuiserie, orientation de la façade, date de l'étude
  - tableaux de toutes les données saisies (site, menuiserie, matériau, support et lames avec leurs profils)
  - **durabilité** : tableau des alertes (élément, constat et préconisation, référence)
  - résultats : instant simulé, bilans été / hiver, optimisations réalisées à l'instant T
  - illustrations : photo aérienne avec tracé du mur, vue 3D, coupe, détails de durabilité, profil de la journée, carte annuelle
  - case **« Inclure les réglages enregistrés »** (cochée par défaut) : ajoute, entre les illustrations et la méthode, le bloc de réglages complet à recopier dans « Réglages enregistrés » → « Charger ces réglages » pour retrouver, retravailler ou vérifier l'étude
  - méthode, limites, avertissement et licence
- **Plan DXF** (format R12, lisible par AutoCAD, DraftSight, BricsCAD, LibreCAD, ArchiCAD, Revit, SketchUp Pro…) :
  - vue de face (depuis l'extérieur), profil (coupe au milieu de la fenêtre) et vue en plan avec flèche du nord, disposées en projection, avec les sections réelles des profils
  - **détails agrandis** des sections des consoles et d'une lame (échelle 1/5), angles réels, minimum à respecter et références
  - dessin en **vraie grandeur** (1 unité = 1 mm)
  - choix de l'échelle (1/1, 1/10, 1/20, 1/25, 1/50) : elle règle la hauteur des textes (2,5 mm imprimés), des titres, des cotes et des hachures
  - case **« Avec les cotes »** : cotes de largeur, débords, hauteur, avancée, niveaux d'altimétrie et caractéristiques des lames
  - un calque par famille : `MUR`, `MUR_HACHURES`, `MENUISERIE`, `VITRAGE`, `SUPPORT`, `CONSOLES`, `LAMES`, `AXES`, `COTES`, `COTES_ANGLES`, `DETAILS`, `EAU`, `TEXTES`
  - cartouche texte : chantier, menuiserie, orientation, échelle, date
- Fichiers nommés d'après le chantier et la menuiserie, par exemple `Residence-Les-Pins_MEX-12_ombrage.pdf`

### Confort
- **Guide de démarrage** au premier lancement, réaffichable à tout moment
- Réglages gardés dans le navigateur, copiables pour les transmettre à un autre poste
- Bouton **☕ Payer un coup** (Ko-fi) dans l'en-tête ; tous les 10 lancements, un petit message de remerciement non bloquant. Le compteur de lancements reste dans le navigateur (`localStorage`), rien n'est envoyé

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
| Ombre sur le vitrage | Lancer de rayons depuis une grille de points sur le vitrage vers le soleil, intersection avec chaque lame et chaque console (prisme de la section réelle du profil) et avec l'embrasure |
| Bilan journalier | Part du rayonnement direct reçu par le vitrage, comparée à la même fenêtre sans brise-soleil |
| Optimisation à l'instant T | Balayage d'un seul paramètre sur sa plage, les autres réglages restant fixes ; valeur la plus économique parmi celles qui donnent l'ombre maximale |
| Rétention d'eau (métal) | Creux entre l'enveloppe convexe de la section et son contour, plus bas que leurs deux bords, dans la position réelle de la pièce |
| Classe d'emploi (bois) | FD P 20-651, tableau 3 (pleine exposition) : massivité, conception (NF DTU 31.1 P1-1), climat d'humidification |

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
- Les alertes de durabilité ne remplacent pas l'application des documents cités ; le climat d'humidification du bois est choisi à la main (FD P 20-651, figure 1 et annexe B)
- Les sections normalisées sont des valeurs nominales arrondies (ailes des UPN dessinées parallèles) ; pour l'aluminium, les dimensions sont indicatives
- Les cotes du DXF sont dessinées (lignes et textes), elles ne sont **pas associatives** : elles ne suivent pas une modification de la géométrie dans le logiciel de dessin
- Le format **DWG** (format fermé d'Autodesk) n'est pas produit : le DXF s'ouvre et s'enregistre en DWG dans les logiciels de DAO
- La photo aérienne et la recherche d'adresse IGN couvrent la France

---

## 📂 Structure du dépôt

```
ombrage/
├── index.html              ← l'outil complet, version en cours (autonome, ~190 KB)
├── ombrage-v2.1.0.html     ← archive de la version 2.1.0
├── ombrage-v2.0.0.html     ← archive de la version 2.0.0
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
