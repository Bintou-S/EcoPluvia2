# EcoPluvia

Site de démonstration du projet de valorisation des eaux de pluie à Dakar (groupe 129).

## Lancer le site
1. Ouvrez le dossier `ecopluvia` dans VS Code (Fichier, Ouvrir le dossier).
2. Installez l'extension « Live Server », puis clic droit sur `index.html` et « Open with Live Server ». Vous pouvez aussi double-cliquer sur `index.html`.
3. Il faut internet pour afficher la carte.

## Accès
Pas de connexion dans cette version de démonstration : un clic sur « Habitant », « Maraîcher » ou « Mairie » ouvre l'espace. Le lien discret « Espace administrateur » est en bas de la page d'accueil. La barre en haut (Accueil et espaces, Le système, etc.) permet de naviguer.

## Qui achète ?
L'eau est vendue aux maraîchers et à toute la population (habitants), au même prix. La mairie est partenaire : elle suit l'impact et les signalements, elle n'achète pas.

## Les sections de présentation (barre sous l'en-tête)
0. **Le système** : schéma du système (image `schema-systeme.png`), de la rue au maraîchage, avec les 4 étapes expliquées par les boutons « Étape précédente / suivante » (grille, décantation, filtre, stockage et pompe solaire) et les deux protections A (bac à déchets) et B (bassin tampon). Code dans `jury.js`, fonction `sysBody()`.
1. **Simulateur de devis** : l'utilisateur règle surface, jours d'arrosage et mois de saison sèche. Le site calcule le volume, le coût EcoPluvia et l'économie, puis génère un devis imprimable (PDF). Hypothèses dans `jury.js` : 4 litres par m² et par arrosage, 600 FCFA le m³ payé aujourd'hui (à confirmer par l'enquête de terrain).
2. **Appli mobile** : maquette de l'agent de terrain. Livraison, relevé de niveau et entretien modifient vraiment le stock des réservoirs et les ventes. Prime de l'agent : `prime` dans `data.js` (10 % par défaut).
3. **Impact et dossier** : chiffres calculés à partir des ventes, stock et ventes par zone, tableau de comparaison, liste de mise en place à cocher.
4. **Équipe** : les six membres du groupe 129.

Le prix de l'eau est de 25 FCFA les 100 litres, décidé par l'équipe (`prix` dans `data.js`).

## Les fichiers
`index.html` (la page), `styles.css` (apparence, couleurs en haut), `data.js` (prix, réservoirs avec `lat` et `lng`, commandes, utilisateurs), `app.js` (espaces habitant, maraîcher, mairie, équipe), `jury.js` (sections de présentation).

## Modifier
- Couleurs : variables en haut de `styles.css`. Tarif : `prix` dans `data.js`, ou Équipe du projet, Réglages.
- Réservoirs : `res` dans `data.js` (nom, `cap`, `niv`, `lat`, `lng`). Ajoutez d'autres zones de Dakar en copiant une ligne.
- Remise à zéro : Équipe du projet, Réglages, « Réinitialiser la démonstration ».

## Passer à une vraie version
1. Serveur et base de données. 2. Vraie authentification (aujourd'hui il n'y en a pas). 3. API Wave et Orange Money (fonction `pay()` dans `app.js`). 4. Capteurs de niveau d'eau. 5. Hébergement (GitHub Pages, Netlify).
