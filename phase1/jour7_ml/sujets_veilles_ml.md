## 🧠 Fiche de consignes – Veille individuelle sur le *Machine Learning*

### 🎯 Objectif de la veille

Découvrir et **comprendre les bases du Machine Learning** à travers une recherche personnelle sur un sous-thème précis.
L’objectif n’est **pas de produire une présentation parfaite**, mais de **montrer ce que vous avez compris** avec vos mots et vos exemples.

---

### 🗓️ Déroulé

* **Durée :** 3h00
* **Restitution :** présentation orale individuelle devant le groupe.
* **Durée de présentation :** 5 minutes maximum + 2 minutes d’échanges.

---

### 🧩 Consignes générales

1. **Faites vos propres recherches** (articles, vidéos, tutoriels, cours en ligne, supports de formation).
   * Vous pouvez utiliser ChatGPT ou d’autres outils **pour mieux comprendre**, mais **pas pour rédiger ou générer votre présentation complète**.

2. **Présentez avec vos mots** : l’essentiel est de montrer votre compréhension.

3. **Structure recommandée (5 à 10 slides maximum) :**
  * **Slide 1 : Définition et principes de base**
  * Présentez les notions fondamentales liées à votre sujet. Utilisez des mots simples et donnez une ou deux définitions claires. Ajoutez un schéma ou une image pour illustrer le concept.
  * **Slide 2 : Exemple concret ou visuel simple**
  * Choisissez un exemple d’application du concept étudié. Montrez un cas réel ou une visualisation (graphique, capture d’écran, image). Expliquez en quoi cet exemple illustre bien votre sujet.
  * **Slide 3 : Avantages et limites / enjeux**
  * Exposez les points forts et les limites du concept. Évoquez les conditions dans lesquelles il fonctionne bien et celles où il montre des faiblesses. Vous pouvez mentionner des enjeux éthiques, techniques ou pratiques.
  * **Slide 4 : Applications ou outils**
  * Citez quelques outils, bibliothèques ou environnements liés à votre sujet (ex. scikit-learn, TensorFlow, H2O…). Donnez des exemples d’utilisation dans des secteurs concrets (santé, finance, industrie, etc.).
  * **Slide 5 : Concepts associés / vocabulaire clé**
  * Listez et expliquez brièvement les mots-clés essentiels à connaître pour comprendre le sujet (par exemple : features, target, hyperparamètres, accuracy…).
  * **Slide 6 : Schéma ou visualisation explicative**
  * Intégrez un schéma synthétique ou un visuel explicatif (processus, architecture, diagramme). Commentez-le avec vos mots.
  * **Slide 7 : Étude de cas simplifiée**
  * Proposez un petit scénario fictif ou réel illustrant le sujet (par exemple : comment une entreprise utilise le clustering pour segmenter sa clientèle).
  * **Slide 8 : Problèmes courants / erreurs à éviter**
  * Soulignez les erreurs typiques ou pièges rencontrés lors de l’application du concept (ex : surapprentissage, biais, mauvaise métrique, mauvaise interprétation des résultats).
  * **Slide 9 : Actualités ou tendances**
  * Donnez un aperçu d’une avancée récente, d’une technologie émergente ou d’une évolution notable du domaine.
  * **Slide 10 : Synthèse et question ouverte**
  * Terminez par une courte synthèse personnelle (3-4 points clés retenus). Posez une question ouverte pour inviter à la réflexion ou au débat.

4. **Support libre** : PowerPoint, Google Slides, Canva, quarto ou PDF.
   * Police lisible, visuels simples, peu de texte.
   * **Nom du fichier :** `Nom_Prenom_Sujet_ML.pdf`

---

## 📚 Sujets et pistes de travail

### 🔹 Sujet 1 : Panorama des différents algorithmes de Machine Learning

**Pistes de travail :**

* Différence entre **apprentissage supervisé, non supervisé et par renforcement**.
* Exemples d’algorithmes : régression, kNN, SVM, arbres de décision, k-means…
* Applications réelles (ex : recommandation Netflix, reconnaissance d’image, détection de spam).
* **Question à se poser :** comment choisir un algorithme selon le type de problème ?

---

### 🔹 Sujet 2 : Le split d’un dataset et les métriques

**Pistes de travail :**

* Pourquoi faut-il **diviser un jeu de données** (train / test / validation) ?
* Principe de la **cross-validation**.
* Les **principales métriques** : R², RMSE, Accuracy, Recall, F1-score…
* Exemples simples : comparer la précision d’un modèle avec différentes métriques.
* **Question à se poser :** que se passe-t-il si on évalue un modèle uniquement sur ses données d’entraînement ?

---

### 🔹 Sujet 3 : Le problème de régression

**Pistes de travail :**

* Principe de la **régression linéaire** et **multilinéaire**.
* Quand utiliser la régression ? (ex : prédire un prix, une température, une consommation).
* Visualiser la droite de régression.
* Différence entre **régression** et **classification**.
* **Question à se poser :** que mesure vraiment la pente et l’interception d’une droite de régression ?

---

### 🔹 Sujet 4 : La classification

**Pistes de travail :**

* Définition et exemples : classer des emails, reconnaître des chiffres, diagnostiquer une maladie.
* Méthodes principales : **arbres de décision**, **k plus proches voisins (kNN)**, **SVM**.
* Notions de frontière de décision.
* **Question à se poser :** pourquoi la classification n’est-elle pas une régression ?

---

### 🔹 Sujet 5 : Le clustering

**Pistes de travail :**

* Différence entre clustering et classification.
* Exemple classique : **k-means**, regroupement de clients ou d’images.
* Mesure de la qualité du regroupement (inertie, silhouette).
* Applications réelles : segmentation marketing, détection d’anomalies.
* **Question à se poser :** que signifie “proche” entre deux données ?

---

### 🔹 Sujet 6 : La problématique de l’overfitting

**Pistes de travail :**

* Définition de **l’overfitting** (sur-apprentissage).
* Exemple simple : un modèle qui “apprend par cœur” sans généraliser.
* Comment le détecter ? (différence entre performance train/test).
* Solutions : régularisation, simplification du modèle, plus de données, dropout (en NN).
* **Question à se poser :** comment trouver le bon équilibre entre performance et généralisation ?

---

### 🔹 Sujet 7 : L’AutoML

**Pistes de travail :**

* Qu’est-ce que **l’AutoML** et pourquoi l’utiliser ?
* Exemples d’outils : Google AutoML, H2O, AutoGluon.
* Ce que fait l’AutoML : sélection d’algorithmes, réglage d’hyperparamètres, évaluation automatique.
* Limites : boîte noire, perte de compréhension, besoin d’expertise humaine.
* **Question à se poser :** l’AutoML rend-il inutile le data scientist ?

---

### 🔹 Sujet 8 : Les réseaux de neurones

**Pistes de travail :**

* Idée de base : neurones artificiels, couches, poids et biais.
* Réseaux simples vs profonds (deep learning).
* Applications : reconnaissance d’image, NLP, jeux.
* Visualiser un réseau de neurones basique (entrée → couche cachée → sortie).
* **Question à se poser :** pourquoi les réseaux de neurones nécessitent-ils beaucoup de données ?

---

### 🔹 Sujet 9 : Les LLMs (Grands Modèles de Langage)

**Pistes de travail :**

* Lien entre réseaux de neurones et LLMs.
* Exemples : ChatGPT, Gemini, Claude, Llama.
* Notion d’entraînement sur de très grands corpus de texte.
* Forces et limites (compréhension du langage, hallucinations, biais).
* **Question à se poser :** un LLM “comprend”-il vraiment ce qu’il dit ?

---

## 🧭 Grille d’évaluation

L’évaluation repose sur les critères suivants :

* **Compréhension du sujet** : capacité à expliquer les notions avec ses propres mots.
* **Clarté et vulgarisation** : présentation accessible à des non-spécialistes.
* **Illustration / exemples** : présence d’exemples concrets ou visuels.
* **Respect des consignes** : durée, nombre de slides, cohérence du contenu.
* **Engagement oral** : posture, dynamisme, capacité à répondre aux questions.

---

### ⚠️ À ne pas faire

* Copier-coller du contenu trouvé en ligne ou généré par une IA sans compréhension.
* Lire vos notes ou vos slides mot pour mot.
* Dépasser 5 slides ou 5 minutes.
* Employer du jargon non expliqué.
