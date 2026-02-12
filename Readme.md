# 🕹️ Physics Mini-Games

Ce projet regroupe trois mini-jeux expérimentaux développés sous **Unreal Engine 5.6.1**, mettant l'accent sur la simulation physique, la logique de Blueprint et l'interface utilisateur.

---

## 🛠️ Informations Globales
* **Moteur :** Unreal Engine 5.6.1
* **Langage :** Blueprints
* **Développeur :** Timéo DELMON

---

## 🎮 Jeu 1 : Jetpack Platformer
*Le mini jeu consistait en la création d'un mini jeu de plateforme avec un système de jetpack pour voler au dessus du vide*

### 🔹 Mécaniques Physiques Utilisées
* **Force du Jetpack :** Utilisation de `Add Force` appliquée sur le `Primitive Component` du joueur pour le faire monter en fonction de la strength du jetpack.
* **Force de Vent :** Utilisation de `Add Force` appliquée sur le `Primitive Component` du joueur pour le faire tomber en fonction d'une Timeline.

### 🔹 Choix Techniques
* **Timeline Loop :** Gestion de l'alternance du vent (On/Off) pour créer un rythme de gameplay.

### 🔹 Problèmes Rencontrés & Solutions
* **Perte de référence au Respawn :** Lors de l'ajout d'un respawn lorsque le joueur tombait, j'ai dû repasser sur tous mes blueprints car j'avais des erreurs de référence en supprimant le character pour le recréer. (Mon character est un pawn sphère pour une simplicité sur les add force).

---

## 🎮 Jeu 2 : Sphere Maze
*Le joueur doit faire rouler une balle à travers un labyrinthe pour gagner*

### 🔹 Mécaniques Physiques Utilisées
* **Simulation par défaut de Unreal Engine :** J'ai utilisé pour ce mini jeu une sphère avec simplement le simulate physics d'activé pour que tout se gère simplement, le joueur contrôle la plateforme et doit éviter les trous pour ne pas tomber.

### 🔹 Choix Techniques
* **Ne pas mettre de plafond :** J'ai choisi de ne pas mettre de plafond à mon labyrinthe, ce qui permet de faire sortir la balle si un mouvement trop brusque est réalisé.

---

## 🎮 Jeu 3 : Jenga Tower Shooter
*Un jeu de précision et de destruction d'une tour de jenga basé sur l'équilibre.*

### 🔹 Mécaniques Physiques Utilisées
* **Simulation Chaos :** Gestion de la masse et de la friction pour la stabilité de la tour.
* **Add Impulse at Location :** Application de forces précises aux points d'impact pour générer des rotations réalistes.

### 🔹 Choix Techniques
* **Instanciation dynamique des jenga :** Génération dynamique des matériaux (Bois vs Or) basée sur des variables d'instance.
* **Master Materials :** Optimisation via des Material Instances pour gérer les reflets métalliques et la rugosité du bois sur les jenga en or.
* **GameMode Logic :** Centralisation du décompte des "Gold Blocks" via un `Get All Actors of Class` au BeginPlay.