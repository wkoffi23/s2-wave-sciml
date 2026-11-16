# 🌊 Wave Propagation on the Sphere ($\mathbb{S}^2$) — Numerical Solver & Neural Operators

> **Modélisation physique, solveur numérique vectorisé en milieu inhomogène et apprentissage d'opérateurs neuronaux (SciML) pour la prédiction auto-régressive d'ondes sur la sphère.**

## 🎯 Objectifs du projet

Ce dépôt regroupe le code et le rapport d'étude portant sur la résolution numérique et l'approximation par apprentissage profond de l'équation des ondes sur la sphère unité $\mathbb{S}^2$ :

1. **Modélisation physique & mathématique :** Formulation de l'équation des ondes sur $\mathbb{S}^2$ (opérateur de Laplace-Beltrami), cas linéaire vs non-linéaire (Klein-Gordon / Shallow Water) et applications géophysiques.
2. **Solveur numérique vectorisé :** Implémentation haute performance capable de simuler la propagation d'ondes dans un milieu inhomogène $c(\theta, \phi)$ et de générer des jeux de données d'entraînement.
3. **Neural Operators auto-régressifs :** Entraînement et comparaison de deux architectures adaptées à la géométrie sphérique (**SFNO** — *Spherical Fourier Neural Operator* et **GNO** — *Graph Neural Operator*) pour prédire l'évolution temporelle sur $k$ pas de temps.
4. **Validation physique :** Analyse des erreurs en déroulement temporel (*rollout*), conservation de l'énergie, spectre harmonique et ouverture vers les régimes non-linéaires.


## 📁 Structure du projet

```text
s2-wave-sciml/
├── pyproject.toml          # Dépendances et métadonnées du package
├── README.md               # Présentation du projet, équations et résultats clés
├── .gitignore              # Ignorer __pycache__, .venv, data/, checkpoints/
├── src/
│   └── s2_wave/
│       ├── __init__.py
│       ├── physics/        # Solveur vectorisé sur la sphère & génération de milieux c(x)
│       ├── models/         # Architectures des 2 Neural Operators (ex: SFNO & GNO)
│       └── utils/          # Visualisation (projections Mollweide/3D) et métriques d'énergie
├── scripts/                # Scripts CLI : generate_data.py, train.py, evaluate.py
├── notebooks/              # Exploration rapide et brouillons de figures
└── report/                 # Rapport final (Quarto .qmd, Jupyter Book ou LaTeX)

