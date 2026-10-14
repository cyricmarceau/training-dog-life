# Training Dog Life — mise en ligne

Le site a 3 fichiers : `index.html` (le jeu), `firebase-config.js` (tes clés) et `firestore.rules` (la sécurité de la base de données).

## 1. Créer le projet Firebase (gratuit, plan Spark)
1. Va sur https://console.firebase.google.com et clique **Créer un projet** (nom : training-dog-life). Google Analytics n'est pas nécessaire.

## 2. Ajouter une application Web
1. Dans le projet, clique l'icône **</>** (Web), donne un nom, ne coche pas Hosting.
2. Firebase affiche un bloc `firebaseConfig = { apiKey: ..., ... }`.
3. Ouvre `firebase-config.js` et remplace les 6 valeurs par les tiennes.

## 3. Activer les comptes par mot de passe
1. Menu **Build → Authentication → Commencer**.
2. Onglet **Méthode de connexion → Adresse e-mail/Mot de passe → Activer → Enregistrer.**
   (Tes amis n'entrent jamais de courriel : le jeu utilise seulement un nom de gladiateur et un mot de passe.)

## 4. Créer la base de données
1. Menu **Build → Firestore Database → Créer une base de données**, région `northamerica-northeast1 (Montréal)`, mode **production**.
2. Onglet **Règles** : colle tout le contenu de `firestore.rules`, puis **Publier**.

## 5. Mettre le site en ligne (Netlify, gratuit, sans ligne de commande)
1. Va sur https://app.netlify.com/drop.
2. Glisse le dossier contenant `index.html`, `firebase-config.js` et `firestore.rules`.
3. Netlify te donne une adresse du genre `https://nom-aleatoire.netlify.app` (renommable dans les paramètres du site).

## 6. Autoriser l'adresse du site dans Firebase
1. **Authentication → Paramètres → Domaines autorisés → Ajouter un domaine**.
2. Ajoute ton adresse Netlify sans `https://` (ex. `training-dog-life.netlify.app`).

## 7. Inviter tes amis
Envoie-leur l'adresse du site. Ils cliquent **Créer un compte**, choisissent un nom, un mot de passe et une couleur.

## Bon à savoir
- Plan gratuit Firebase : largement suffisant pour un groupe d'amis (50 000 lectures / jour).
- Mot de passe oublié : pas de récupération par courriel (pas de vrai courriel). Tu peux supprimer le compte dans **Authentication → Utilisateurs** pour que la personne le recrée.
- La clé `apiKey` dans `firebase-config.js` n'est pas secrète : c'est normal qu'elle soit visible. La sécurité vient des règles de l'étape 4.
- Pour mettre à jour le site plus tard : refais un glisser-déposer du dossier sur Netlify (onglet **Deploys** de ton site).
