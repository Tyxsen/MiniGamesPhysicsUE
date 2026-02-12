# 🕹️ Physics Mini-Games Showcase - UE 5.6.1

Ce projet regroupe trois mini-jeux expérimentaux développés sous **Unreal Engine 5.6.1**, mettant l'accent sur la simulation physique Chaos, la logique de Blueprint et l'interface utilisateur.

---

## 🛠️ Informations Globales
* **Moteur :** Unreal Engine 5.6.1
* **Langage :** Blueprints
* **Système Physique :** Chaos Physics
* **Développeur :** [Ton Nom] (Développeur de jeux vidéo)

---

## 🎮 Jeu 1 : Jenga Tower Shooter
*Un jeu de précision et de destruction basé sur l'équilibre.*

### 🔹 Mécaniques Physiques Utilisées
* **Simulation Chaos :** Gestion de la masse (2.0kg) et de la friction pour la stabilité de la tour.
* **Add Impulse at Location :** Application de forces précises aux points d'impact pour générer des rotations réalistes.
* **Projectile Movement :** Utilisation d'une vélocité initiale constante (3000 cm/s) pour les projectiles.

### 🔹 Choix Techniques
* **Construction Script :** Génération dynamique des matériaux (Bois vs Or) basée sur des variables d'instance.
* **Master Materials :** Optimisation via des Material Instances pour gérer les reflets métalliques et la rugosité du bois.
* **GameMode Logic :** Centralisation du décompte des "Gold Blocks" via un `Get All Actors of Class` au BeginPlay.

### 🔹 Problèmes Rencontrés & Solutions
* **Référencement du HUD :** Correction des erreurs "Accessed None" après respawn via des nœuds `Is Valid` et une récupération dynamique du Player Pawn.
* **Instabilité de la Tour :** Ajustement du Substepping physique pour éviter que les blocs ne s'interpénètrent au repos.

---

## 🎮 Jeu 2 : [Nom du Jeu 2]
*Description courte du concept (ex: Course d'obstacles avec vent).*

### 🔹 Mécaniques Physiques Utilisées
* **Force de Vent :** Utilisation de `Add Force` appliquée sur le `Primitive Component` du joueur en fonction d'une Timeline.
* [Ajoute une autre mécanique ici]

### 🔹 Choix Techniques
* **Timeline Loop :** Gestion de l'alternance du vent (On/Off) pour créer un rythme de gameplay.
* [Ajoute un autre choix ici]

### 🔹 Problèmes Rencontrés & Solutions
* **Perte de référence au Respawn :** Passage d'un stockage de variable fixe à une détection par Overlap pour appliquer les forces uniquement sur les acteurs présents dans la zone.

---

## 🎮 Jeu 3 : [Nom du Jeu 3]
*Description courte du concept.*

### 🔹 Mécaniques Physiques Utilisées
* [Mécanique 1]
* [Mécanique 2]

### 🔹 Choix Techniques
* [Choix 1]
* [Choix 2]

### 🔹 Problèmes Rencontrés & Solutions
* [Problème rencontré] : [Solution trouvée]

---

## 📦 Instructions pour le Build
1. **Packaging :** Le projet doit être buildé en mode *Development* ou *Shipping*.
2. **Maps :** Assurez-vous que toutes les scènes sont incluses dans `Project Settings > Packaging > List of maps to include`.
3. **Contrôles :** - [Clic Gauche] : Tirer / Interagir
   - [R] : Reset Level
   - [Échap] : Quitter