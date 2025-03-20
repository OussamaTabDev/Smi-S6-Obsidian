## **Chapitre 1 : Généralités – Approfondissement avec plus d’exemples et précisions**

---

# **I. Notion de Système – Exemples et Clarifications**

📌 **Exemples supplémentaires de systèmes** :

| <font color="#3fffff">Type de Système | <font color="#3fffff">Description               </font> | <font color="#3fffff">Exemples </font>   |
| ------------------------------------- | ------------------------------------------------------- | ---------------------------------------- |
| **Naturel**                           | Existent sans intervention humaine                      | Climat, Système digestif, Écosystème     |
| **Artificiel**                        | Créés par l’homme                                       | Réseau de transport, Centrale électrique |
| **Abstrait**                          | Modélisation conceptuelle                               | Théories mathématiques, Algorithmes      |
| **Concret**                           | Existent physiquement                                   | Téléphone, Robot, Voiture                |

📌 **Précision sur les interactions des systèmes** :

- Un système **peut être composé de sous-systèmes**.
    - **Exemple** : Un **ordinateur** est un système qui contient des sous-systèmes comme le processeur, la carte graphique et la mémoire.
- Un système **peut interagir avec d’autres systèmes**.
    - **Exemple** : Un **site e-commerce** interagit avec une **banque** pour le paiement, un **stock de produits** pour vérifier la disponibilité, et un **système de livraison** pour l’expédition.

📌 **Exemple d’erreur dans la conception d’un système** :

- 🚨 **Pont de Tacoma (1940, USA)** → Un pont mal conçu s’est effondré à cause de la résonance aérodynamique.
- 💰 **Bug logiciel sur une carte bancaire (1996, Australie)** → Un client a pu retirer 10 millions de dollars à cause d’une erreur dans le système bancaire.

---

# **II. Notion de Modèle – Exemples et Précisions**

📌 **Autres types de modèles courants en informatique** :

|Type de Modèle|Description|Exemples|
|---|---|---|
|**Modèle de données**|Représente comment les données sont organisées et stockées|Schéma d’une base de données (ex : MySQL, PostgreSQL)|
|**Modèle de processus**|Décrit les étapes d’un système en fonctionnement|Modèle BPMN d’un processus métier|
|**Modèle prédictif**|Permet de faire des prévisions basées sur des données existantes|Algorithme de prédiction des ventes|

📌 **Différence entre un modèle statique et dynamique** :

- **Modèle statique** : Décrit **l’état du système à un moment donné**.
    - **Exemple** : Plan d’architecture d’un bâtiment.
- **Modèle dynamique** : Montre **l’évolution du système dans le temps**.
    - **Exemple** : Diagramme d’activité en UML qui montre **le fonctionnement d’un programme pas à pas**.

📌 **Cas où un modèle est insuffisant** :

- 🛑 Un **modèle météo** peut être imprécis si les données collectées sont insuffisantes.
- 🛑 Un **modèle économique** ne prend pas toujours en compte **les événements imprévisibles** (crise, guerre, pandémie).

---

# **III. Notion de Logiciel – Exemples et Cas d’Étude**

📌 **Types de logiciels et exemples** :

|Type de Logiciel|Description|Exemples|
|---|---|---|
|**Logiciel système**|Permet de gérer le matériel et les ressources de l’ordinateur|Windows, Linux, MacOS|
|**Logiciel applicatif**|Permet aux utilisateurs d’exécuter des tâches spécifiques|Word, Photoshop, Google Chrome|
|**Middleware**|Permet aux applications de communiquer entre elles|API de paiement Stripe, base de données SQL|
|**Logiciel embarqué**|Fonctionne dans un matériel spécifique|Programme d’un pacemaker, système ABS d’une voiture|

📌 **Cas réels de problèmes logiciels** :

- **Bug du Pentium (1994)** → Erreur dans le processeur Intel qui provoquait des erreurs de calcul.
- **Échec du vol Mars Climate Orbiter (1999)** → Une erreur d’unité de mesure (mètres vs pieds) a provoqué la perte d’un satellite.

📌 **Exemple de logiciel critique où les erreurs sont inacceptables** :

- Logiciel d’un **système médical** qui contrôle la **dose de radiothérapie**.
- Logiciel d’un **avion de ligne** qui ajuste **l’altitude et la vitesse**.

---

# **IV. Introduction au Génie Logiciel – Approfondissement et Exemples**

📌 **Pourquoi le génie logiciel est-il apparu ?**  
Dans les années 60-70, la programmation était faite sans méthode structurée.  
➡️ **Résultat** : Bugs fréquents, dépassements de budget et échecs de projets.  
📌 **Exemple :**

- **Projet de la NASA (Apollo 11, 1969)** → Premier exemple de **développement logiciel structuré** qui a permis l’alunissage en toute sécurité.

📌 **Métiers du génie logiciel** :

|Métier|Rôle|
|---|---|
|**Analyste**|Étudie les besoins et conçoit les spécifications|
|**Développeur**|Écrit et teste le code|
|**Architecte logiciel**|Conçoit la structure technique du logiciel|
|**Testeur QA**|Vérifie la qualité et détecte les bugs|
|**Chef de projet**|Gère les ressources, le planning et le budget|

---

# **V. Critères de Qualité d’un Logiciel – Exemples Détaillés**

📌 **Critères essentiels de qualité d’un logiciel et exemples concrets** :

|Critère|Définition|Exemples|
|---|---|---|
|**Fiabilité**|Le logiciel fonctionne sans erreurs graves|Une application bancaire ne doit **pas perdre les transactions**|
|**Robustesse**|Il fonctionne même dans des conditions extrêmes|Un logiciel médical doit **continuer à fonctionner même en cas de panne d’un capteur**|
|**Extensibilité**|Facile à modifier ou améliorer|Un site e-commerce doit pouvoir **ajouter de nouveaux moyens de paiement**|
|**Sécurité**|Protège les données contre les cyberattaques|Un service de messagerie doit chiffrer les conversations|
|**Performance**|Temps de réponse rapide et faible consommation des ressources|Google doit charger une page **en moins d’une seconde**|
|**Compatibilité**|Fonctionne sur plusieurs plateformes|Un jeu doit fonctionner **sur Windows, Mac et Linux**|

---

# **VI. Conclusion – Synthèse des Points Essentiels**

📌 **Points clés à retenir :**  
✅ Un **système** est un ensemble organisé qui transforme des entrées en sorties.  
✅ Un **modèle** est une simplification qui permet de comprendre un phénomène complexe.  
✅ Un **logiciel** est plus qu’un simple programme : il doit être fiable, sécurisé et évolutif.  
✅ Le **génie logiciel** est une **discipline essentielle** qui assure la qualité des logiciels.

📌 **Exemples finaux pour illustrer l’importance du génie logiciel** :

- **Si un jeu vidéo est mal conçu** → Il crashe et provoque des pertes de données.
- **Si un système de train automatique a un bug** → Il peut provoquer des accidents mortels.
- **Si un site e-commerce est mal optimisé** → Il perd des ventes car trop lent.

💡 **Le développement logiciel ne consiste pas seulement à coder, mais à structurer et à garantir la fiabilité du produit !**

---

📌 **Si tu veux approfondir une section ou voir plus d’exemples spécifiques, dis-moi ! 😊**