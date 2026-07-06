# Mariage Jade & Renaud : page infos invités

Une seule page (`index.html`), pensée pour être ouverte depuis le QR code à la fin de la vidéo faire-part : les invités y retrouvent la date, le lieu (carte + boutons GPS) et les infos pratiques.

## 1. Mettre la page en ligne (à faire une fois, par Renaud)

1. Sur GitHub : **Settings** → **Pages** (menu de gauche)
2. Section *Build and deployment* → Source : **Deploy from a branch**
3. Branch : `main`, dossier `/ (root)` → **Save**
4. Après 1-2 minutes, la page est en ligne sur :

   **https://renaudsegonds.github.io/mariage-JR/**

C'est cette URL qu'il faut encoder dans le QR code (n'importe quel générateur de QR code gratuit fait l'affaire, ex. l'outil intégré de Canva ou qr-code-generator.com).

## 2. Remplir les vraies infos (checklist)

Tout se modifie directement sur GitHub : ouvrir `index.html` → icône crayon → modifier → **Commit changes**. Les blocs à changer sont signalés par des commentaires `⚠️ À MODIFIER` dans le fichier :

- [ ] La date et la commune (bloc HÉRO)
- [ ] Le nom du lieu et l'adresse complète (bloc LIEU)
- [ ] **Les coordonnées GPS** : un seul endroit, tout en bas de la page dans le bloc `<script>` (les lignes `var LAT = ...` et `var LNG = ...`). La carte ET les 3 boutons (Google Maps, Waze, Plans) se mettent à jour automatiquement. Pour trouver les coordonnées : clic droit sur le lieu dans Google Maps → le premier élément du menu copie `latitude, longitude` (ex. `43.6892, -1.3729`) ; coller la latitude dans `LAT`, la longitude dans `LNG`
- [ ] Les horaires de la journée (bloc PROGRAMME)
- [ ] Le numéro de téléphone pour confirmer sa venue (bloc INFOS PRATIQUES), dans le texte ET dans le lien `tel:+33...`
- [ ] Supprimer les blocs inutiles (dress code, hébergement) si pas besoin

Chaque modification commitée est en ligne au bout d'environ une minute.

## Aperçu du rendu

`exemple-rendu.html` est une copie de la page remplie avec des infos fictives (mariage à Seignosse), juste pour visualiser le résultat final. Ce fichier n'est **pas** sur GitHub : il sert d'aperçu local, la vraie page à remplir reste `index.html`.

## Notes

- La carte est une intégration **OpenStreetMap** : gratuite, sans clé API ni compte à créer. Un simple bout de code (le `<script>` en bas) construit la carte et les liens à partir des coordonnées.
- La page n'est pas référencée par Google (balise `noindex`) : seuls ceux qui ont le lien ou le QR code la trouvent. Le repo étant public, ce n'est pas un coffre-fort : ne pas y mettre d'info sensible.
- Un seul fichier HTML autonome (les polices viennent de Google Fonts, la carte d'OpenStreetMap).
