# L3 GRH — Plateforme Pédagogique Intégrée

> **Ressources open-source pour l'enseignement des Bases de Données, SQL et Systèmes de Gestion**  
> Université Abdou Moumouni • Niamey, Niger  
> Cours L3 Gestion des Ressources Humaines, Finance-Bancaire-Assurance

---

## 📚 À propos

Cette plateforme regroupe **supports pédagogiques structurés, exercices progressifs et mini-projets** pour l'enseignement des bases de données et systèmes de gestion en L3.

### 🎯 Objectifs
- ✅ Maîtrise conceptuelle (modélisation, design)
- ✅ Compétences pratiques (SQL, requêtes complexes)
- ✅ Application réelle (cas d'études : banque, paie RH, assurance)
- ✅ Reproductibilité et open-source éducatif

### 👥 Public cible
- Étudiants **L3 GRH** (Université Abdou Moumouni)
- Étudiants autodidactes en gestion/informatique
- Professionnels en transition vers les bases de données

---

## 📑 Structure du cours

### **Module 1 : Fondations des Bases de Données**
*Concepts fondamentaux, modélisation, design relationnel*

- Introduction : qu'est-ce qu'une BD ?
- Modèle entité-association (MCD)
- Normalisation (1FN, 2FN, 3FN, BCNF)
- Principes de design relationnel
- **Durée estimée** : 3-4 semaines

**📂 Dossier** : [`module-01-fondations-bd/`](./module-01-fondations-bd/)

---

### **Module 2 : SQL Pratique**
*Requêtes, SELECT, JOIN, agrégation, procédures*

- Syntaxe SQL de base
- SELECT, WHERE, ORDER BY
- JOIN (INNER, LEFT, RIGHT, FULL)
- Agrégation (GROUP BY, HAVING, fonctions)
- Sous-requêtes
- Procédures stockées et triggers
- **Durée estimée** : 4-5 semaines

**📂 Dossier** : [`module-02-sql-pratique/`](./module-02-sql-pratique/)

---

### **Module 3 : Design de BD et Cas d'Études**
*Application intégrée : créer une BD complète du cahier des charges au déploiement*

**Trois mini-projets au choix** :

1. **Système bancaire** : gestion de comptes, transactions, clients
2. **Gestion de paie RH** : employés, salaires, congés, cotisations
3. **Système d'assurance** : polices, sinistres, cotisants

Chaque projet inclut :
- 📋 Cahier des charges
- 🎨 Diagramme MCD/MLD
- 💾 Schéma SQL solution
- ✅ Données test
- 📊 Requêtes analytiques

**📂 Dossier** : [`module-03-design-bd/`](./module-03-design-bd/)

---

### **Module 4 : Systèmes de Gestion Intégrés**
*ERP, workflows, audit, sécurité*

- Architecture des systèmes de gestion
- Workflows et processus
- Audit et traçabilité
- Sécurité des données
- Considérations d'implémentation

**📂 Dossier** : [`module-04-systemes-gestion/`](./module-04-systemes-gestion/)

---

## 🗂️ Arborescence complète

```
L3-GRH-Cours/
│
├── 📄 README.md (ce fichier)
├── 📄 LICENSE (CC-BY-SA 4.0)
├── 📄 CONTRIBUER.md
│
├── 📁 module-01-fondations-bd/
│   ├── 📄 README.md
│   ├── 📁 slides/
│   ├── 📁 notes/
│   ├── 📁 exercices/
│   │   └── 📁 corrections/
│   └── 📁 ressources/
│
├── 📁 module-02-sql-pratique/
│   ├── 📄 README.md
│   ├── 📁 slides/
│   ├── 📁 exercices/
│   │   └── 📁 corrections/
│   ├── 📁 notebooks/
│   └── 📁 ressources/
│
├── 📁 module-03-design-bd/
│   ├── 📄 README.md
│   ├── 📁 mini-projets/
│   │   ├── 📁 projet-01-banque/
│   │   ├── 📁 projet-02-paie-rh/
│   │   └── 📁 projet-03-assurance/
│   └── 📁 ressources/
│
├── 📁 module-04-systemes-gestion/
│   ├── 📄 README.md
│   ├── 📁 slides/
│   ├── 📁 cas-etudes/
│   └── 📁 ressources/
│
├── 📁 evaluations/
│   ├── 📁 qcm/
│   ├── 📁 controles/
│   └── 📁 examens/
│
├── 📁 ressources-transversales/
│   ├── 📄 glossaire.md
│   ├── 📄 outils-recommandes.md
│   ├── 📁 donnees-test/
│   └── 📁 scripts/
│
└── 📁 .github/
    └── 📁 workflows/
```

---

## 🚀 Utilisation

### Pour les **étudiants**
1. Clonez le repo : `git clone https://github.com/saleymato/L3-GRH-Cours.git`
2. Naviguez dans le module correspondant
3. Suivez les notes + exercices
4. Comparez vos solutions avec les corrections
5. Travaillez les mini-projets progressivement

### Pour les **enseignants**
1. Adaptez les ressources à votre contexte
2. Contribuez vos améliorations (voir [CONTRIBUER.md](./CONTRIBUER.md))
3. Créez des évaluations personnalisées
4. Partagez vos cas d'études

---

## 🛠️ Outils recommandés

| Besoin | Outil | Gratuit |
|--------|-------|--------|
| **Design BD** | Draw.io, Lucidchart | ✅ Draw.io |
| **Gestion SQL** | DBeaver, SQLiteOnline | ✅ Tous deux |
| **Notebooks interactifs** | Jupyter, Google Colab | ✅ Tous deux |
| **IDE léger** | VS Code, Thonny | ✅ Tous deux |
| **Environnement DB** | SQLite, PostgreSQL | ✅ Tous deux |

---

## 📖 Glossaire & Ressources

Consultez [`ressources-transversales/glossaire.md`](./ressources-transversales/glossaire.md) pour :
- Définitions (BD, relation, clé primaire, etc.)
- Acronymes (MCD, MLD, SGBD, etc.)
- Références externes

---

## 📝 Format des ressources

### Slides
- Format : **Markdown** (convertible en PDF via Pandoc)
- Structurés en sections numérotées
- Diagrammes embarqués (ASCII ou PNG)

### Exercices
- Énoncé + contexte clair
- Progressive difficulty (⭐ ⭐⭐ ⭐⭐⭐)
- Corrections détaillées avec explications
- Données test fournies

### Mini-projets
- Cahier des charges réaliste
- Livrables attendus clairement définis
- Critères d'évaluation
- Solutions de référence

---

## 📊 Parcours recommandé

```
Débutant complet
    ↓
Module 1 (fondations)
    ↓
Module 2 (SQL basics)
    ↓
Mini-projet 1 (banque) ← Plus simple
    ↓
Mini-projet 2 (paie RH) ← Moyen
    ↓
Mini-projet 3 (assurance) ← Avancé
    ↓
Module 4 (systèmes intégrés)
    ↓
Évaluations finales
```

---

## 🤝 Contribution

Vous avez des améliorations, corrections ou cas d'études à partager ?

Voir [`CONTRIBUER.md`](./CONTRIBUER.md) pour :
- Soumettre une issue
- Proposer une pull request
- Style guide
- Processus de révision

---

## 📜 Licence

Cette plateforme est sous **Creative Commons Attribution-ShareAlike 4.0 International (CC-BY-SA 4.0)**.

**Vous pouvez** :
- ✅ Utiliser, modifier, distribuer
- ✅ Adapter pour vos cours
- ✅ Partager vos améliorations

**À condition de** :
- 📌 Attribuer les auteurs originaux
- 🔄 Partager vos modifications sous la même licence

Voir [`LICENSE`](./LICENSE) pour les détails complets.

---

## 👨‍🏫 Auteur & Maintenance

**Saley Mato Idrissa**  
Université Abdou Moumouni, Niamey  
[@saleymato](https://github.com/saleymato)

---

## 📮 Questions / Feedback

- 📋 Ouvrez une [issue](https://github.com/saleymato/L3-GRH-Cours/issues)
- 🔀 Proposez une [pull request](https://github.com/saleymato/L3-GRH-Cours/pulls)
- 💬 Discussions : utilisez l'onglet [Discussions](https://github.com/saleymato/L3-GRH-Cours/discussions)

---

## 🌍 Contexte

Ressource développée dans un environnement aux ressources contraintes, optimisée pour **accessibilité maximale** :
- Fichiers légers (Markdown, SQL pur)
- Pas de dépendances lourdes
- Compatible offline
- Adaptée au contexte pédagogique africain

**Bienvenue ! 🎓**

---

*Last updated: 2026-05-06*  
*Version: 1.0-initial*
