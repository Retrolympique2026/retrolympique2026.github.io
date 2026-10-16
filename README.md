# 🏆 Retrolympique 2026 — MCCI Business School

Site officiel des **Retrolympiques 2026** de la MCCI Business School (Journée Sportive du **23 octobre 2026** au Racing Club).

Le site permet de suivre en temps réel les scores, le classement des équipes (7 équipes / 7 dieux de l'Olympe), le calendrier des 12 épreuves et le mur photos.

---

## 🛠️ Modifications & Backend mis en place

Le backend temps réel a été activé et configuré avec **Google Firebase (Firestore + Authentication)** pour permettre aux arbitres et organisateurs de mettre à jour les scores en direct le jour de l'événement.

### Ce qui a été configuré :
1. **Firebase Firestore Database** : Base de données NoSQL synchronisée en temps réel avec tous les visiteurs du site.
2. **Firebase Authentication** : Module d'authentification par Email & Mot de passe pour sécuriser l'accès aux modifications.
3. **Règles de sécurité Firestore** :
   - **Lecture** : Ouverte à tous les visiteurs (scores et classements publics en direct).
   - **Écriture** : Réservée aux comptes administrateurs connectés.
4. **Fichier `config.js`** : Rempli avec les clés de l'application Firebase (`retrolympique2026`).

---

## 👥 Comptes Administrateurs (Arbitres & Table de Marque)

Trois comptes d'administration ont été créés pour permettre à plusieurs organisateurs / arbitres de saisir les résultats en parallèle :

| Rôle / Arbitre | Adresse Email | Mot de passe |
|---|---|---|
| **Admin 1** | `admin1@retrolympique.fr` | *(fourni aux organisateurs)* |
| **Admin 2** | `admin2@retrolympique.fr` | *(fourni aux organisateurs)* |
| **Admin 3** | `admin3@retrolympique.fr` | *(fourni aux organisateurs)* |

> ℹ️ **Sécurité** : Les mots de passe sont transmis directement aux organisateurs et arbitres autorisés. Ils peuvent être réinitialisés ou gérés depuis la [Console Firebase](https://console.firebase.google.com/project/retrolympique2026/authentication/users).

---

## 🔑 Comment accéder à l'espace Organisation ?

Il existe deux manières simples d'accéder au panneau d'administration :

### Méthode 1 : Lien direct (le plus rapide)
Ajouter `#orga` à la fin de l'adresse du site dans le navigateur :
```text
http://localhost/retrolympique/#orga
```
*(ou l'URL publique de déploiement + `#orga`)*

### Méthode 2 : Depuis le site
1. Descendre tout en bas de la page (footer).
2. À droite (sous le bouton d'inscription), cliquer sur **« Accès organisation »**.
3. Renseigner l'email et le mot de passe d'un des comptes admin ci-dessus.

---

## 📋 Guide d'utilisation de la Table de Marque (Jour J)

Une fois connecté :
1. Un bouton **« Orga »** apparaît dans la barre de navigation en haut de l'écran.
2. Le tiroir latéral **« Table de marque »** s'ouvre :
   - **Choisir l'épreuve** dans la liste déroulante (Football, Basketball, Relais, Uno, etc.).
   - **Changer le statut** (*À venir*, *En cours*, *Terminée*).
   - **Saisir les points** : boutons `+` et `−` sur les scores des matchs ou sélectionner le podium final.
   - **Attribuer les bonus** : Fair-play (jusqu'à 5 pts) et Créativité mascottes/drapeau (jusqu'à 10 pts).
3. **Publier les scores** :
   - Vos saisies sont d'abord enregistrées localement en brouillon.
   - Cliquez sur le bouton rouge **« Publier en direct »** pour envoyer les scores sur Firestore.
   - Tous les visiteurs connectés verront instantanément les scores et le classement se mettre à jour !

---

## 📁 Structure des fichiers

- [`index.html`](file:///c:/wamp64/www/retrolympique/index.html) : Application Web complète (HTML, styles CSS, scripts clients, logique de classement et interface admin).
- [`config.js`](file:///c:/wamp64/www/retrolympique/config.js) : Configuration des clés API Firebase.
- [`css/`](file:///c:/wamp64/www/retrolympique/css/) : Feuilles de styles complémentaires (`reset.css`, `style.css`).
- [`qr/`](file:///c:/wamp64/www/retrolympique/qr/) : Fichiers QR Codes pour diffusion mobile aux participants.
- [`README.md`](file:///c:/wamp64/www/retrolympique/README.md) : Cette documentation.
