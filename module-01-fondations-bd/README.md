# Module 1 : Fondations des Bases de Données

> **Objectif** : Maîtriser les concepts fondamentaux et la modélisation de BD  
> **Durée** : 3-4 semaines  
> **Niveau** : Débutant (pas de prérequis)  
> **Public** : L3 GRH, Finance-Bancaire-Assurance

---

## 📋 Vue d'ensemble

Ce module pose les **fondations essentielles** pour comprendre et concevoir des bases de données :

1. **Concepts fondamentaux** : Données, tables, colonnes, clés
2. **Modèle Entité-Association (MCD)** : Diagrammes conceptuels
3. **Normalisation** : 1FN, 2FN, 3FN, BCNF
4. **Modèle Logique (MLD)** : Traduction en schéma relationnel
5. **Intégrité et contraintes** : Clés, références, unicité

---

## 🎯 Objectifs pédagogiques

À la fin du module, vous saurez :

- ✅ Définir qu'est-ce qu'une base de données
- ✅ Identifier entités, attributs, relations
- ✅ Concevoir un MCD avec Merise/UML
- ✅ Normaliser un schéma relationnel
- ✅ Traduire MCD → MLD
- ✅ Comprendre les contraintes d'intégrité

---

## 📚 Contenu pédagogique

### Semaine 1 : Concepts Fondamentaux

**Slides** : [`slides/01-concepts-fondamentaux.md`](./slides/01-concepts-fondamentaux.md)

Topics :
- Qu'est-ce qu'une base de données ?
- Données vs information
- Tables, colonnes, lignes
- Clés primaires (PK)
- Types de données (VARCHAR, INT, DATE, etc.)

**Exercices** : [`exercices/ex1-concepts.md`](./exercices/ex1-concepts.md)
- Ex 1.1 : Identifier tables/colonnes dans un cas réel
- Ex 1.2 : Choisir types de données
- Ex 1.3 : Définir clés primaires

### Semaine 1-2 : Modèle Entité-Association (MCD)

**Slides** : [`slides/02-mcd-merise.md`](./slides/02-mcd-merise.md)

Topics :
- Entités et attributs
- Relations (1:1, 1:N, N:M)
- Diagrammes ER (Merise/UML)
- Cardinalités
- Identification des relations

**Exercices** : [`exercices/ex2-mcd.md`](./exercices/ex2-mcd.md)
- Ex 2.1 : Créer MCD banque simple
- Ex 2.2 : Identifier cardinalités
- Ex 2.3 : Diagramme complet entreprise

### Semaine 2-3 : Normalisation

**Slides** : [`slides/03-normalisation.md`](./slides/03-normalisation.md)

Topics :
- Dépendances fonctionnelles
- 1ère Forme Normale (1FN) : Pas de redondance
- 2e Forme Normale (2FN) : Pas de DF partielle
- 3e Forme Normale (3FN) : Pas de DF transitive
- Forme Normale de Boyce-Codd (BCNF)

**Exercices** : [`exercices/ex3-normalisation.md`](./exercices/ex3-normalisation.md)
- Ex 3.1 : Dénormaliser → 1FN
- Ex 3.2 : Dépendances partielles → 2FN
- Ex 3.3 : Dépendances transitives → 3FN
- Ex 3.4 : Cas complexe

### Semaine 3-4 : Modèle Logique (MLD)

**Slides** : [`slides/04-mld-schema-relationnel.md`](./slides/04-mld-schema-relationnel.md)

Topics :
- Traduction MCD → MLD
- Relations N:M → table junction
- Clés étrangères (FK)
- Contraintes d'intégrité référentielle
- Schéma relationnel complet

**Exercices** : [`exercices/ex4-mld.md`](./exercices/ex4-mld.md)
- Ex 4.1 : Transformer MCD en MLD
- Ex 4.2 : Gérer N:M avec table junction
- Ex 4.3 : Clés étrangères et intégrité
- Ex 4.4 : Schéma complet d'entreprise

---

## 🔬 Ressources

### Diagrammes d'exemple
- BD Banque simple : [`ressources/mcd-banque.png`](./ressources/mcd-banque.png)
- BD Entreprise complet : [`ressources/mcd-entreprise.png`](./ressources/mcd-entreprise.png)
- Exemple normalisation : [`ressources/normalisation-exemple.txt`](./ressources/normalisation-exemple.txt)

### Outils recommandés
- **Draw.io** : Diagrammes (web, gratuit)
- **Lucidchart** : Alternative (freemium)
- **MySQL Workbench** : Design ER
- **DBeaver** : Visualisation BD

### Cheat Sheet
- Cardinalités Merise : [`ressources/cardinalites.md`](./ressources/cardinalites.md)
- Types de données SQL : [`ressources/types-donnees.md`](./ressources/types-donnees.md)

---

## 📋 Parcours par niveau

### 👶 **Débutant**
```
Slides 01 (Concepts)
  ↓
Ex 1.1 à 1.3
  ↓
Slides 02 (MCD simple)
  ↓
Ex 2.1 à 2.2
  ↓
Préparer Module 2
```

### 👤 **Intermédiaire**
```
Tous les slides (01-04)
  ↓
Ex 1 à 3 (tous)
  ↓
Diagrammes MCD/MLD
  ↓
Normalisation pratique
```

### 🧠 **Avancé**
```
Tous les exercices
  ↓
Cas d'étude complexe (ex 4.4)
  ↓
Diagrammes avec Draw.io
  ↓
Prêt pour Module 2 & 3
```

---

## ✅ Évaluation

| Critère | Débutant | Intermédiaire | Avancé |
|---------|----------|---------------|--------|
| **Concepts** | Basique | Complet | Nuancé |
| **MCD** | Simple (1-2 entités) | Complexe (5+ entités) | N:M + constraints |
| **Normalisation** | 1FN-2FN | 3FN | BCNF |
| **MLD** | Simple | Avec FK | Complet |

---

## 📝 Tous les exercices

| Exercice | Fichier | Correction | Niveau |
|----------|---------|-----------|--------|
| Concepts BD | `ex1-concepts.md` | `corrections/ex1-correction.md` | ⭐ |
| MCD | `ex2-mcd.md` | `corrections/ex2-correction.md` | ⭐⭐ |
| Normalisation | `ex3-normalisation.md` | `corrections/ex3-correction.md` | ⭐⭐⭐ |
| MLD complet | `ex4-mld.md` | `corrections/ex4-correction.md` | ⭐⭐⭐ |

---

## 🎓 Après ce module

✅ Vous êtes prêt pour **Module 2 : SQL Pratique** 💪

Vous comprenez la structure BD et pouvez concevoir un schéma !

---

## 📌 Notes pédagogiques

- **Commencez très visuel** : Diagrammes d'abord, pas de théorie pure
- **Cas réalistes** : Banque, Entreprise, Assurance (le contexte des étudiants)
- **Erreurs courantes** : Montrez les mauvaises conceptions et pourquoi elles échouent
- **Normalisation progressive** : Ne pas surcharger au début

---

*Last updated: 2026-05-05*  
*Status: Structure template — contenu à remplir*
