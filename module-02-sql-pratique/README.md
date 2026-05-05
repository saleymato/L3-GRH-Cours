# Module 2 : SQL Pratique

> **Objectif** : Maîtriser SQL pour interroger et manipuler des bases de données  
> **Durée** : 4-5 semaines  
> **Niveau** : Intermédiaire (post-Module 1)  
> **Prérequis** : Concepts BD, normalisation, MLD

---

## 📋 Vue d'ensemble

Ce module couvre :

1. **Syntaxe SQL de base** : SELECT, WHERE, ORDER BY
2. **Jointures (JOIN)** : INNER, LEFT, RIGHT, FULL, CROSS
3. **Agrégation & Groupage** : GROUP BY, HAVING, fonctions agrégats
4. **Sous-requêtes** : Requêtes imbriquées et corrélées
5. **Manipulation de données** : INSERT, UPDATE, DELETE
6. **Procédures stockées & Triggers** : Logique métier en BD
7. **Performance & Indexation** : Optimiser les requêtes

---

## 🎯 Objectifs pédagogiques

À la fin du module, vous saurez :

- ✅ Écrire des requêtes SELECT simples et complexes
- ✅ Utiliser les 5 types de JOIN correctement
- ✅ Grouper et agréger des données
- ✅ Écrire des sous-requêtes optimisées
- ✅ Modifier les données (INSERT/UPDATE/DELETE)
- ✅ Créer des procédures stockées simples
- ✅ Optimiser et indexer une BD

---

## 📚 Contenu pédagogique

### Semaine 1 : SQL Basics

**Slides** : [`slides/01-sql-select-basics.md`](./slides/01-sql-select-basics.md)

Topics :
- Syntaxe SELECT de base
- Clause WHERE, opérateurs
- ORDER BY, LIMIT
- Alias et expressions

**Exercices** : [`exercices/ex1-select-basics.sql`](./exercices/ex1-select-basics.sql)
- Ex 1.1 : SELECT simples
- Ex 1.2 : WHERE avec conditions
- Ex 1.3 : Tri et limitation

### Semaine 2 : Jointures

**Slides** : [`slides/02-joins.md`](./slides/02-joins.md)

Topics :
- INNER JOIN
- LEFT / RIGHT JOIN
- FULL OUTER JOIN
- CROSS JOIN
- Self-join
- Cardinalités et jointures

**Exercices** : [`exercices/ex2-joins.sql`](./exercices/ex2-joins.sql)
- Ex 2.1 : INNER JOIN basique
- Ex 2.2 : Jointures multiples
- Ex 2.3 : LEFT JOIN et NULL
- Ex 2.4 : Self-join (arborescence)

### Semaine 2-3 : Agrégation & Groupage

**Slides** : [`slides/03-agregation.md`](./slides/03-agregation.md)

Topics :
- Fonctions agrégats (COUNT, SUM, AVG, MIN, MAX)
- GROUP BY
- HAVING
- Agrégation imbriquée

**Exercices** : [`exercices/ex3-agregation.sql`](./exercices/ex3-agregation.sql)
- Ex 3.1 : COUNT et agrégats simples
- Ex 3.2 : GROUP BY
- Ex 3.3 : HAVING (filtrage post-groupage)
- Ex 3.4 : Cas métier (totaux, moyennes)

### Semaine 3-4 : Sous-requêtes & Requêtes complexes

**Slides** : [`slides/04-sous-requetes.md`](./slides/04-sous-requetes.md)

Topics :
- Sous-requêtes scalaires
- Sous-requêtes liste (IN, NOT IN)
- Sous-requêtes corrélées
- EXISTS / NOT EXISTS

**Exercices** : [`exercices/ex4-sous-requetes.sql`](./exercices/ex4-sous-requetes.sql)
- Ex 4.1 : Sous-requêtes simples
- Ex 4.2 : IN et listes
- Ex 4.3 : Sous-requêtes corrélées
- Ex 4.4 : EXISTS

### Semaine 4-5 : DML & Stored Procedures

**Slides** : [`slides/05-dml-procedures.md`](./slides/05-dml-procedures.md)

Topics :
- INSERT (simples et multiples)
- UPDATE (avec conditions)
- DELETE
- Transactions
- Procédures stockées
- Triggers basiques

**Exercices** : [`exercices/ex5-dml.sql`](./exercices/ex5-dml.sql)
- Ex 5.1 : INSERT
- Ex 5.2 : UPDATE
- Ex 5.3 : DELETE
- Ex 5.4 : Procédures simples

---

## 🔬 Jupyter Notebooks interactifs

Pratiquer SQL en ligne (optionnel mais recommandé) :

**Notebook** : [`notebooks/SQL-pratique.ipynb`](./notebooks/SQL-pratique.ipynb)

- Requêtes exécutables
- Explication pas à pas
- Visualisation résultats
- À utiliser avec Colab (gratuit, pas d'installation)

---

## 📊 Ressources

### Schéma de test
- Base "Banque" : [`ressources/schema-banque.sql`](./ressources/schema-banque.sql)
- Base "Entreprise" : [`ressources/schema-entreprise.sql`](./ressources/schema-entreprise.sql)
- Données test incluses

### Outils recommandés
- **SQLiteOnline** : Web, gratuit, pas d'installation
- **DBeaver** : Desktop, gratuit, puissant
- **pgAdmin** : Interface PostgreSQL (si localement)

### Cheat Sheet
- Syntaxe SQL résumée : [`ressources/sql-cheatsheet.md`](./ressources/sql-cheatsheet.md)
- Fonctions courantes : [`ressources/fonctions-sql.md`](./ressources/fonctions-sql.md)

---

## 📋 Parcours par niveau

### 👶 **Débutant**
```
Slides 01 (SELECT basics)
  ↓
Ex 1.1 à 1.3
  ↓
Slides 02 (INNER JOIN simple)
  ↓
Ex 2.1 à 2.2
  ↓
Slides 03 (COUNT, SUM)
  ↓
Ex 3.1 à 3.2
```

### 👤 **Intermédiaire**
```
Slides 01 à 04
  ↓
Ex 1 à 4 (tous)
  ↓
Cas d'étude : requêtes métier réalistes
```

### 🧠 **Avancé**
```
Tous les exercices
  ↓
Notebook Jupyter (exécution interactive)
  ↓
Cas métier complexes
  ↓
Optimisation (EXPLAIN PLAN)
  ↓
Préparer Mini-Projet 1 (Banque)
```

---

## ✅ Évaluation

| Critère | Débutant | Intermédiaire | Avancé |
|---------|----------|---------------|--------|
| **SELECT** | Basique | Conditions complexes | Optimisé |
| **JOIN** | INNER simple | Multiples | Self-join, optimisé |
| **GROUP BY** | Basique | HAVING | Complexe/imbriqué |
| **Sous-requêtes** | N/A | Simples | Corrélées, EXISTS |
| **DML** | Basique | UPDATE/DELETE condition | Transactions |

---

## 📝 Tous les exercices

| Exercice | Fichier | Correction | Niveau |
|----------|---------|-----------|--------|
| SELECT basique | `ex1-select-basics.sql` | `corrections/ex1-correction.sql` | ⭐ |
| Jointures | `ex2-joins.sql` | `corrections/ex2-correction.sql` | ⭐⭐ |
| Agrégation | `ex3-agregation.sql` | `corrections/ex3-correction.sql` | ⭐⭐ |
| Sous-requêtes | `ex4-sous-requetes.sql` | `corrections/ex4-correction.sql` | ⭐⭐⭐ |
| DML | `ex5-dml.sql` | `corrections/ex5-correction.sql` | ⭐⭐ |

---

## 🎓 Après ce module

✅ Vous êtes prêt pour **Module 3 : Mini-projets pratiques**

Vous saurez interroger une BD complète et produire des rapports !

---

## 📌 Notes pédagogiques

- Commencez **très simple** (SELECT d'une table)
- Augmentez progressivement (JOIN → GROUP BY → sous-requêtes)
- **Pratiquez beaucoup** — SQL s'apprend en faisant
- Montrez l'ordre d'exécution (FROM → JOIN → WHERE → SELECT → ORDER BY)
- Mentionnez les **pièges courants** (NULL, jointures multiples, performance)

---

*Last updated: 2026-05-05*  
*Status: Structure template — contenu à remplir*
