# Réservation des Terrains — EMI

Version simple du système de réservation : le site reste un seul fichier `index.html`.

## Fonctionnement

- 3 terrains : Mini-foot, Basketball, Volleyball.
- Créneaux de 8h à 22h.
- 1 seule réservation par génie et par jour, quel que soit le terrain.
- Chaque réservation contient le génie et le nom du représentant.
- Une réservation ne peut pas être modifiée ou supprimée par un étudiant.
- La suppression nécessite le mot de passe administrateur Firebase.
- Les réservations sont synchronisées en temps réel avec Firestore.

## Filières incluses

- GC — Génie Civil
- GE — Génie Électrique
- GRT — Génie Réseaux et Télécommunications
- GI — Génie Industriel
- GINF — Génie Informatique
- GM — Génie Mécanique
- GMIN — Génie Minéral
- MIS — Génie Modélisation et Informatique Scientifique
- GPI — Génie des Procédés Industriels

## Configuration Firebase

1. Créer un projet Firebase.
2. Activer **Firestore Database**.
3. Activer **Authentication > Sign-in method > Email/Password**.
4. Dans **Authentication > Users**, créer manuellement l'utilisateur :
   - Email : `admin.reservation@emi.local`
   - Mot de passe : utiliser le mot de passe administrateur privé choisi pour ce projet.
5. Dans **Project Settings > Your apps**, créer une Web App et copier la configuration dans `firebaseConfig` dans `index.html`.
6. Dans **Firestore Database > Rules**, remplacer les règles par le contenu de `firestore.rules`, puis publier.
7. Envoyer `index.html`, `firestore.rules` et ce README sur GitHub.
8. Dans **GitHub > Settings > Pages**, publier depuis la branche `main` / dossier racine.

## Important

Ne mets jamais le mot de passe administrateur dans le dépôt GitHub. Il n'apparaît pas dans `index.html` : Firebase Authentication le vérifie côté serveur.
