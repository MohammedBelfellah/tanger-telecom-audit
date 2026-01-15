# 📡 Diagnostic de Couverture Mobile - Région Tanger-Tétouan

[![Netlify Status](https://img.shields.io/badge/Deployed-Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)](https://tanger-telecom-audit.netlify.app/)
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

> **Analyse géospatiale et visualisation interactive de l'infrastructure télécommunication au Maroc**

---

## 📋 Description

Ce projet réalise un **audit complet de la couverture mobile** dans la région de Tanger-Tétouan en analysant les données d'antennes 2G/3G/4G/5G. Il combine :

- 🗺️ **Analyse spatiale** : grillage géographique à 1 km de résolution avec correction cosinus
- 🤖 **Machine Learning** : clustering DBSCAN pour détecter les zones orphelines
- 📊 **Visualisations professionnelles** : graphiques statiques exportables (PNG) pour rapports
- 🌍 **Carte interactive** : interface Folium déployée sur Netlify avec calques multiples

**🔗 [Voir la carte interactive en direct](https://tanger-telecom-audit.netlify.app/)**

---

## ✨ Fonctionnalités

### 🔍 Analyse de Données
- ✅ Filtrage géographique précis (bbox Tanger-Tétouan)
- ✅ Nettoyage automatique (qualité des mesures, doublons, valeurs aberrantes)
- ✅ Classification technologique : **Class_A (4G/5G)** vs **Class_B (2G/3G)**
- ✅ Fraîcheur temporelle : antennes actives depuis 2015+

### 🗺️ Cartographie Intelligente
- ✅ Grille spatiale 1 km² avec correction cosinus pour latitude
- ✅ Statut de couverture par maille : **Connectée** / **Fracture** / **Vide**
- ✅ Détection d'anomalies : antennes 2G/3G isolées (hors clusters modernes)
- ✅ Zones critiques : équipements obsolètes (< 2020)

### 📊 Business Intelligence
- ✅ Comparaison des opérateurs : **IAM**, **Orange**, **Inwi**
- ✅ Taux de modernisation 4G/5G par opérateur
- ✅ Évolution temporelle des déploiements (2010-2026)
- ✅ Export CSV des zones prioritaires pour intervention

### 📈 Visualisations
| Graphique | Description |
|-----------|-------------|
| **Fig1** | Répartition globale des technologies (camembert) |
| **Fig2** | Statut de couverture par maille (barres) |
| **Fig3** | Comparaison opérateurs (barres groupées) |
| **Fig4** | Évolution temporelle (histogramme empilé) |

---

## 🛠️ Technologies Utilisées

### Stack Python
```
pandas          → Manipulation de données
numpy           → Calculs géospatiaux
folium          → Cartographie interactive
scikit-learn    → Clustering DBSCAN
matplotlib      → Visualisations statiques
seaborn         → Styling des graphiques
```

### Infrastructure
- **Jupyter Notebook** : environnement d'analyse
- **Git** : versioning du code
- **Netlify** : déploiement automatique de la carte HTML

---

## 📦 Installation

### 1. Cloner le dépôt
```bash
git clone https://github.com/MohammedBelfellah/tanger-telecom-audit.git
cd tanger-telecom-audit
```

### 2. Installer les dépendances
```bash
pip install pandas numpy folium scikit-learn matplotlib seaborn jupyter
```

### 3. Lancer le notebook
```bash
jupyter notebook mean.ipynb
```

---

## 🚀 Utilisation

### Exécution du pipeline complet
1. **Ouvrir `mean.ipynb`** dans Jupyter
2. **Exécuter toutes les cellules** (Kernel → Run All)
3. **Outputs générés** :
   - `index.html` : carte interactive
   - `Fig1_Repartition_Global.png`
   - `Fig2_Statut_Mailles.png`
   - `Fig3_Operateurs_Comparaison.png`
   - `Fig4_Evolution_Temporelle.png`
   - `Rapport_Zones_A_Moderniser.csv` : liste des antennes prioritaires

### Paramètres configurables (Cellule 2)
```python
BBOX = {"lat_min": 34.5, "lat_max": 36.0, "lon_min": -6.5, "lon_max": -4.5}
GRID_KM = 1.0              # Résolution de la grille
ACTIVE_YEAR_MIN = 2015     # Seuil de fraîcheur
LAT_REF = 35.7             # Latitude de référence
```

---

## 📊 Résultats Clés

### 🎯 Métriques de Couverture
- **610+ mailles** analysées dans la région
- **~200 antennes actives** après filtres de qualité
- **Distribution 4G/5G vs 2G/3G** : visualisée en temps réel
- **Zones de fracture** : identifiées avec précision géographique

### 🏆 Insights Opérateurs
- Taux de modernisation par MNC (Maroc Telecom, Orange, Inwi)
- Stratégies de déploiement 4G/5G par zone
- Antennes orphelines hors clusters modernes

---

## 🌐 Démo en Ligne

**🔗 Carte Interactive :** [https://tanger-telecom-audit.netlify.app/](https://tanger-telecom-audit.netlify.app/)

**Fonctionnalités de la carte :**
- ✅ Calques activables : Zones connectées / Fractures / Points critiques
- ✅ Zoom interactif et navigation fluide
- ✅ Popups informatifs sur chaque antenne
- ✅ Rectangles colorés par statut de couverture

---

## 📁 Structure du Projet

```
tanger-telecom-audit/
├── mean.ipynb                          # Notebook principal d'analyse
├── morocco_towers.csv                   # Données brutes (13 MB)
├── index.html                          # Carte interactive (déployée)
├── Fig1_Repartition_Global.png         # Graphique 1
├── Fig2_Statut_Mailles.png             # Graphique 2
├── Fig3_Operateurs_Comparaison.png     # Graphique 3
├── Fig4_Evolution_Temporelle.png       # Graphique 4
├── Rapport_Zones_A_Moderniser.csv      # Export CSV priorités
└── README.md                           # Ce fichier
```

---

## 🎓 Cas d'Usage

### Pour les Opérateurs Télécoms
- Identifier les zones sous-couvertes (2G/3G uniquement)
- Prioriser les investissements 4G/5G
- Benchmarking concurrentiel

### Pour les Collectivités
- Audit de fracture numérique territoriale
- Planification d'aménagement numérique
- Suivi de l'égalité d'accès aux réseaux

### Pour les Chercheurs
- Analyse géospatiale de l'infrastructure télécommunication
- Étude de l'évolution technologique (2010-2026)
- Modélisation de la couverture réseau

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Pour proposer des améliorations :

1. **Fork** le projet
2. Créer une branche (`git checkout -b feature/amelioration`)
3. Commit les changements (`git commit -m 'Ajout feature X'`)
4. Push vers la branche (`git push origin feature/amelioration`)
5. Ouvrir une **Pull Request**

---

## 📝 License

Ce projet est sous licence **MIT**. Consultez le fichier [LICENSE](LICENSE) pour plus de détails.

---

## 👨‍💻 Auteur

**Mohammed Belfellah**  
📧 Email : [mohammedbelfellah2@gmail.com]  
🔗 GitHub : [@MohammedBelfellah](https://github.com/MohammedBelfellah)  

---

## 🙏 Remerciements

- Données : [OpenCellID](https://opencellid.org/) / Sources publiques
- Cartographie : [Folium](https://python-visualization.github.io/folium/) & [OpenStreetMap](https://www.openstreetmap.org/)
- Machine Learning : [scikit-learn](https://scikit-learn.org/)
- Déploiement : [Netlify](https://www.netlify.com/)

---

## 📸 Captures d'écran

### Carte Interactive
![Carte Interactive](https://via.placeholder.com/800x400?text=Carte+Interactive+Tanger-T%C3%A9touan)

### Graphiques d'Analyse
![Graphiques](https://via.placeholder.com/800x400?text=Visualisations+Statistiques)

---

<div align="center">

**⭐ Si ce projet vous aide, n'oubliez pas de lui donner une étoile sur GitHub ! ⭐**

Made with ❤️ in Morocco 🇲🇦

</div>
