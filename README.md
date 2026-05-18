# PROJET 7 : SYSTÈME DE RECOMMANDATION DE PRODUITS

## Algorithme de Filtrage Collaboratif basé sur la Théorie des Graphes



### 1. PRÉSENTATION DU PROJET

Inspiré des systèmes de pointe utilisés par les leaders du e-commerce (tels qu'Amazon), ce moteur de recommandation analyse le comportement d'achat pour suggérer des produits hautement pertinents.

Le système repose sur deux piliers scientifiques :

1. **Modélisation par Graphe Biparti :** Représentation des interactions entre deux ensembles distincts (Utilisateurs  Produits).
2. **Mesure de Proximité :** Utilisation de l'indice de **similarité de Jaccard** pour identifier les voisinages (k-Nearest Neighbors) et prédire les préférences futures.

---

### 2. ARCHITECTURE TECHNIQUE

Le code adopte une structure modulaire, favorisant la scalabilité et la maintenance :

* `main.py` : Point d'entrée principal et gestion du menu interactif.
* `models.py` : Définition des entités (Classes *Utilisateur* et *Produit*).
* `graphe.py` : Implémentation du Graphe Biparti via des tables de hachage.
* `recommandation.py` : Cœur algorithmique (Calcul de Jaccard, Tri et Filtrage).
* `gestion_donnees.py` : Gestion des flux d'E/S (Parsing de fichiers et export Graphviz).
* `donnees.txt` : Base de données textuelle des historiques d'achats.

---

### 3. CONFIGURATION ET PRÉREQUIS

* **Langage :** Python 3.8+
* **Dépendances :** Aucune bibliothèque tierce n'est requise. Le projet exploite exclusivement la bibliothèque standard Python (`sys`, `webbrowser`, `urllib`), garantissant une portabilité totale.

---

### 4. GUIDE D'UTILISATION

Suivez ces étapes pour tester les fonctionnalités du moteur :

1. **Initialisation :** Exécutez `$ python main.py` depuis votre terminal.
2. **Chargement :** Sélectionnez l'option **[1]** pour charger `donnees.txt` et compiler le graphe en mémoire.
3. **Analyse & Visualisation (Optionnel) :** * Option **[2]** : Statistiques du réseau (nœuds et arêtes).
* Option **[3]** : Visualisation graphique du réseau via votre navigateur.


4. **Recommandation :** Choisissez l'option **[4]**.
* Sélectionnez un utilisateur cible (ex: ID 16 ou 18).
* Le système identifie instantanément les "voisins" similaires et génère une liste de suggestions priorisées.



---

### 5. MÉTHODOLOGIE D'IMPLÉMENTATION

* **Modélisation :** Graphe biparti non-orienté où chaque arête symbolise une transaction.
* **Optimisation :** Utilisation intensive des dictionnaires Python pour des recherches de nœuds en complexité constante .
* **Logique Mathématique :** L'indice de Jaccard est utilisé pour comparer les ensembles d'achats :



---

### 7. SCÉNARIOS DE DÉMONSTRATION

Des profils types ont été configurés pour valider la précision de l'algorithme :

* **Profil "Gamer" (ID 16 - Sofyane) :**
* *Analyse :* Forte corrélation détectée avec les profils de Moad et Yassine.
* *Résultat :* Suggestions d'accessoires (Souris RGB, Chaise Gaming).


* **Profil "Professionnel" (ID 18 - Manal) :**
* *Analyse :* Proximité identifiée avec Ahmed et Karim.
* *Résultat :* Suggestions de matériel de bureau (Webcam Pro, Clavier Silent).
