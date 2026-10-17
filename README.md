# Écran TRMNL sur iPad

Une page web qui affiche sur un iPad (ou n'importe quel navigateur) l'écran d'un appareil [TRMNL](https://trmnl.com) et le met à jour au même rythme que l'appareil.

La page interroge directement l'API des appareils TRMNL (`GET /api/display`), comme le ferait le boîtier. Il n'y a ni serveur intermédiaire ni clé dans ce dépôt : la clé de l'appareil est saisie sur l'iPad et reste dans son navigateur (stockage local).

## Utilisation

1. Ouvre la page dans Safari sur l'iPad.
2. Colle la clé de l'appareil. Elle se trouve sur trmnl.com, dans les réglages de l'appareil, champ **API Key**.
3. Choisis l'affichage clair, sombre ou nuit, puis touche **Afficher l'écran**.
4. Touche Partager, puis **Sur l'écran d'accueil**, et ouvre l'écran depuis cette icône pour l'avoir en plein écran.
5. Dans les Réglages de l'iPad, mets le verrouillage automatique sur **Jamais** et laisse l'iPad branché.

Touche l'écran pour voir l'heure de la dernière mise à jour, actualiser ou ouvrir les réglages.

## Actualisation forcée (facultatif)

Sans autre réglage, « Actualiser » redemande l'écran à TRMNL, qui passe alors au suivant de la playlist avec les données déjà en cache.

Avec une **clé de compte** en plus, « Actualiser » demande à TRMNL de recharger tout de suite les données de chaque plugin (`POST /api/plugin_settings/{id}/refreshes`), attend que l'écran soit recalculé, puis réaffiche le même écran (`GET /api/display/current`) sans avancer la playlist.

1. Sur trmnl.com, dans les réglages du compte, crée une clé avec seulement les droits **Read** et **Content**, limitée si possible aux plugins affichés.
2. Sur l'iPad, ouvre Réglages, puis « Actualisation forcée », et colle la clé.

Chaque forçage compte dans le quota horaire de calculs d'écran du compte TRMNL : la page n'en autorise qu'un toutes les 2 min. La clé reste dans le navigateur de l'iPad, comme celle de l'appareil.

## Bon à savoir

- Chaque mise à jour compte comme une connexion de l'appareil et fait avancer sa playlist. Si un boîtier TRMNL tourne en même temps sur la même clé, les deux se partagent la playlist. Dans ce cas, utilise plutôt [TRMNL Mirror](https://trmnl.com/mirror), qui se contente de recopier l'écran du boîtier.
- La page fonctionne aussi avec un serveur TRMNL auto-hébergé : renseigne son adresse dans « Serveur ».
- Compatible avec les anciens iPad (le code n'utilise que du JavaScript ES5).
