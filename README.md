# Plans pour dossier d’urbanisme – éditeur libre

Un outil gratuit, open source (MIT) et sans installation, **100 % pensé pour les dossiers d’urbanisme français** : il aide le grand public à dessiner, dans le navigateur, les pièces graphiques d’une déclaration préalable (DP) ou d’un permis de construire (PCMI), et à savoir quel dossier déposer.

Tout tient dans **un seul fichier, `index.html`** (HTML, CSS et JavaScript, aucune dépendance). Il faut une connexion Internet pour la vue « Situation » (carte IGN) ; le reste fonctionne sans appel réseau.

## Les vues

| Vue | Pièce | Ce que l’outil apporte |
|---|---|---|
| **Situation** | DP1 / PCMI1 | Carte IGN (plan, photo aérienne) centrée sur votre adresse, parcelle cadastrale tracée, échelle 1/5 000 à 1/25 000, nord et source |
| **Plan de masse** | DP2 / PCMI2 | Parcelle, bâti existant / à démolir / projeté, clôtures, portails, accès, stationnement, réseaux (eau, électricité, EU, EP), fenêtres et portes sur les murs, distances aux limites, emprises |
| **Niveaux** | (notice, calcul) | Plans des niveaux (sous-sol à combles), murs avec épaisseur, pièces, **surface de plancher** calculée au nu intérieur, zones non comptées (≤ 1,80 m, trémies, garages…) |
| **Coupe** | DP3 / PCMI3 | Terrain naturel et projeté, altitudes, dénivelé, pente, point le plus haut |
| **Façades** | DP4 / PCMI5 | Murs, matériaux, toitures (2 pans, croupes, terrasse, pentes libres), fenêtres, portes, baies, lucarnes, cheminées, garde-corps ; **génération des 4 façades depuis le plan de masse**, nommées d’après leur orientation, avec les ouvertures du plan |
| **Insertion** | DP6 / PCMI6 | Photo du terrain + projet dessiné par-dessus (opacité réglable), végétation existante |

## Mon dossier

Le bouton **Mon dossier** :
- indique **quel dossier déposer** (dispense, déclaration préalable, permis de construire de maison individuelle ou autre) et le Cerfa correspondant, d’après la nature des travaux, les surfaces, la zone, les secteurs protégés ;
- signale l’**obligation de recourir à un architecte** (seuil de 150 m² de surface de plancher) ;
- liste les **pièces à joindre**, indique celles que l’outil génère et celles à fournir en plus ;
- vérifie les **règles du PLU que vous saisissez** (recul, emprise, hauteur) ;
- produit un **PDF complet** : page de garde, liste de contrôle, puis les plans.

Chaque vue a un texte d’aide en français expliquant ce que le service instructeur attend de la pièce.

> ⚠️ **Les réponses sont indicatives.** Elles reposent sur les règles générales du Code de l’urbanisme ; le PLU de la commune peut prévoir plus strict. **Confirmez toujours auprès de votre mairie** avant de déposer. L’outil ne remplace pas un professionnel.

## Fonctions communes

- Dessin en **mètres réels**, feuille **A4 ou A3**, portrait ou paysage, échelle choisie ou automatique, légende, barre d’échelle, nord, cartouche.
- Murs avec épaisseur, ouvertures posées d’un clic sur un mur, cotes libres, symboles (arbres, voitures, personnes, repères).
- **Image de fond** (cadastre, photo, plan existant) avec mise à l’échelle par deux points.
- **Copier / coller** (Ctrl+C, Ctrl+V ou boutons), y compris d’une vue à l’autre quand le type d’objet existe dans les deux (ex. un mur d’un niveau à l’autre).
- **Tactile** : un doigt pour dessiner ou déplacer, deux doigts pour zoomer et déplacer la vue, barre « Terminer / Dernier point / Abandonner » pour les tracés.
- **Visite guidée** au premier lancement (11 étapes, relançable avec le bouton **?**).
- **Mode sombre** (suit le réglage du système, bouton ☾ / ☀ pour forcer) ; la feuille reste blanche comme le papier.
- **Mes dossiers** : plusieurs dossiers enregistrés automatiquement dans le navigateur, à reprendre, dupliquer, supprimer ou télécharger en copie `.json` (pour les mettre à l’abri ou les ouvrir sur un autre appareil). Un rappel propose d’enregistrer une copie après une vingtaine de minutes de travail.
- Annuler / rétablir ; « Ouvrir… » reprend une copie `.json`.

## Exports

- **PDF** (impression du navigateur : « Enregistrer au format PDF », marges « Aucune », échelle 100 %), **SVG**, **PNG**.
- **DXF** (R12, mètres, échelle 1:1) : un calque par type d’objet, **hachures**, **vraies cotes** (entités DIMENSION), épaisseur des murs, surfaces des pièces. Le fond de carte n’est pas inclus.
- **Import DXF** (ASCII) : lignes, polylignes, cercles, arcs, textes, cotes. Unité détectée ou choisie, lignes jointes en polylignes, reconnaissance des calques d’un export de l’outil. Hachures, blocs, splines et DXF binaires ne sont pas repris.

## Confidentialité

Aucun compte, aucune donnée envoyée à un serveur de l’auteur. **Seule la vue Situation** contacte des services publics depuis votre navigateur : géocodage de l’adresse, tuiles de carte et API cadastre de la **Géoplateforme de l’IGN**. L’adresse que vous tapez et la zone affichée leur sont donc transmises. Vos dossiers restent dans le stockage local de votre navigateur (pas de compte, rien sur un serveur) et dans les fichiers que vous enregistrez. Vider les données du navigateur efface les dossiers : gardez des copies `.json`.



## Développement

Aucune compilation : ouvrez `index.html`. Le code est organisé en sections commentées (types d’objets, rendu, carte, dossier, interactions, export DXF). Les contributions sont bienvenues.

## Licence

MIT – voir `LICENSE`. Fond de carte : © IGN – Géoplateforme.
