# Écran TRMNL sur iPad

Une page web qui affiche sur un iPad (ou n'importe quel navigateur) l'écran d'un appareil [TRMNL](https://trmnl.com) et le met à jour au même rythme que l'appareil.

La page interroge directement l'API des appareils TRMNL (`GET /api/display`), comme le ferait le boîtier. Il n'y a ni serveur intermédiaire ni clé dans ce dépôt : la clé de l'appareil est saisie sur l'iPad et reste dans son navigateur (stockage local).

## Utilisation

1. Ouvre la page dans Safari sur l'iPad.
2. Colle la clé de l'appareil. Elle se trouve sur trmnl.com, dans les réglages de l'appareil, champ **API Key**.
3. Choisis l'affichage clair, sombre ou nuit, puis touche **Afficher l'écran**.
4. Touche Partager, puis **Sur l'écran d'accueil**, et ouvre l'écran depuis cette icône pour l'avoir en plein écran.
5. Dans les Réglages de l'iPad, mets le verrouillage automatique sur **Jamais** et laisse l'iPad branché.

Touche l'écran pour voir l'heure de la dernière mise à jour, changer d'écran, actualiser ou ouvrir les réglages.

## Boutons

Touche l'écran pour afficher la barre :

- **Actualiser** : TRMNL recharge les données de l'écran affiché (tous les widgets d'un écran combiné), le recalcule et le renvoie environ 30 secondes plus tard. L'écran reste le même. C'est la fonction spéciale « Refresh » du boîtier (`Special-Function: refresh`).
- **◀** : écran précédent (fonction « Rewind », `Special-Function: rewind`).
- **▶** : écran suivant.

Glisser le doigt vers la gauche ou la droite fait la même chose que ▶ et ◀. Seule la clé de l'appareil est nécessaire. La page se présente avec le firmware 1.5.9, le minimum requis par ces fonctions.

## Bon à savoir

- Chaque mise à jour compte comme une connexion de l'appareil et fait avancer sa playlist. Si un boîtier TRMNL tourne en même temps sur la même clé, les deux se partagent la playlist. Dans ce cas, utilise plutôt [TRMNL Mirror](https://trmnl.com/mirror), qui se contente de recopier l'écran du boîtier.
- La page fonctionne aussi avec un serveur TRMNL auto-hébergé : renseigne son adresse dans « Serveur ».
- Compatible avec les anciens iPad (le code n'utilise que du JavaScript ES5).
