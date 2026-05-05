# Module 3 : Design de BD et Mini-Projets Pratiques

> **Objectif** : Appliquer tous les concepts dans des projets réalistes complets  
> **Durée** : 4-6 semaines  
> **Niveau** : Intermédiaire-Avancé (post-Modules 1-2)  
> **Public** : L3 GRH prêt pour travail appliqué

---

## 📋 Vue d'ensemble

Ce module est **100% pratique** : Vous concevez et implémentez 3 mini-projets complets du cahier des charges au déploiement.

Chaque projet couvre :
- ✅ Analyse des besoins
- ✅ Conception MCD/MLD
- ✅ Implémentation SQL (CREATE TABLE)
- ✅ Données test réalistes
- ✅ Requêtes analytiques
- ✅ Validation et tests

---

## 🎯 Objectifs pédagogiques

À la fin du module, vous saurez :

- ✅ Analyser un cahier des charges réel
- ✅ Concevoir une BD complète (MCD+MLD)
- ✅ Implémenter schéma SQL robuste
- ✅ Peuplez BD avec données réalistes
- ✅ Écrire requêtes analytiques utiles
- ✅ Tester et valider votre BD

---

## 📚 Les 3 Mini-Projets

### 🏦 **Projet 1 : Système Bancaire**

**Niveau** : ⭐⭐ (Débutant-Intermédiaire)  
**Durée** : 1-2 semaines  
**Difficultés** : Relations 1:N simples, cardinalités claires

**Contenus** :
- [`01-banque/description.md`](./mini-projets/projet-01-banque/description.md) — Vue métier
- [`01-banque/requirements.md`](./mini-projets/projet-01-banque/requirements.md) — Cahier des charges
- [`01-banque/mcd-diagramme.png`](./mini-projets/projet-01-banque/mcd-diagramme.png) — Design conceptuel
- [`01-banque/schema-solution.sql`](./mini-projets/projet-01-banque/schema-solution.sql) — Implémentation
- [`01-banque/donnees-test.sql`](./mini-projets/projet-01-banque/donnees-test.sql) — Données
- [`01-banque/requetes.sql`](./mini-projets/projet-01-banque/requetes.sql) — Requêtes utiles
- [`01-banque/guide-evaluation.md`](./mini-projets/projet-01-banque/guide-evaluation.md) — Critères

**Cas métier** :
- Clients, comptes, transactions
- Transactions (dépôts, retraits, virements)
- Soldes et mouvements

---

### 💰 **Projet 2 : Gestion de Paie RH**

**Niveau** : ⭐⭐⭐ (Intermédiaire)  
**Durée** : 2-3 semaines  
**Difficultés** : Plusieurs relations N:M, calculs complexes

**Contenus** :
- [`02-paie-rh/description.md`](./mini-projets/projet-02-paie-rh/description.md) — Vue métier
- [`02-paie-rh/requirements.md`](./mini-projets/projet-02-paie-rh/requirements.md) — Cahier des charges
- [`02-paie-rh/mcd-diagramme.png`](./mini-projets/projet-02-paie-rh/mcd-diagramme.png) — Design
- [`02-paie-rh/schema-solution.sql`](./mini-projets/projet-02-paie-rh/schema-solution.sql) — Schéma complet
- [`02-paie-rh/donnees-test.sql`](./mini-projets/projet-02-paie-rh/donnees-test.sql) — Données
- [`02-paie-rh/requetes.sql`](./mini-projets/projet-02-paie-rh/requetes.sql) — Requêtes analytiques
- [`02-paie-rh/guide-evaluation.md`](./mini-projets/projet-02-paie-rh/guide-evaluation.md) — Critères

**Cas métier** :
- Employés, postes, salaires
- Cotisations (Sécurité Sociale, CNSS)
- Congés et absences
- Historique de paie

---

### 🛡️ **Projet 3 : Système d'Assurance**

**Niveau** : ⭐⭐⭐⭐ (Avancé)  
**Durée** : 2-3 semaines  
**Difficultés** : Complexe, N:M multiples, workflows

**Contenus** :
- [`03-assurance/description.md`](./mini-projets/projet-03-assurance/description.md) — Vue métier
- [`03-assurance/requirements.md`](./mini-projets/projet-03-assurance/requirements.md) — Cahier des charges complet
- [`03-assurance/mcd-diagramme.png`](./mini-projets/projet-03-assurance/mcd-diagramme.png) — Design complexe
- [`03-assurance/schema-solution.sql`](./mini-projets/projet-03-assurance/schema-solution.sql) — Schéma
- [`03-assurance/donnees-test.sql`](./mini-projets/projet-03-assurance/donnees-test.sql) — Données réalistes
- [`03-assurance/requetes.sql`](./mini-projets/projet-03-assurance/requetes.sql) — Requêtes avancées
- [`03-assurance/guide-evaluation.md`](./mini-projets/projet-03-assurance/guide-evaluation.md) — Critères

**Cas métier** :
- Cotisants, polices, couvertures
- Sinistres (déclaration, expertise, remboursement)
- Workflows et états
- Analyse de risques

---

## 📋 Processus pour chaque projet

### 1️⃣ **Phase 1 : Analyse (1-2 jours)**
- Lisez le cahier des charges
- Identifiez entités et relations
- Dessinez MCD préliminaire (sur papier ou Draw.io)

### 2️⃣ **Phase 2 : Conception (2-3 jours)**
- Normalisez le MCD
- Traduisez en MLD (schéma relationnel)
- Vérifiez clés, cardinalités, intégrité

### 3️⃣ **Phase 3 : Implémentation (2-3 jours)**
- Écrivez CREATE TABLE
- Définissez contraintes (PK, FK, UNIQUE, NOT NULL)
- Indexez les colonnes critiques

### 4️⃣ **Phase 4 : Données (1-2 jours)**
- Peuplez avec données test réalistes
- INSERT données clients/employés/cotisants
- Créez mouvements/transactions/sinistres

### 5️⃣ **Phase 5 : Requêtes (2-3 jours)**
- Écrivez requêtes analytiques
- Jointures complexes
- Agrégation et insights

### 6️⃣ **Phase 6 : Validation (1 jour)**
- Testez intégrité données
- Vérifiez requêtes
- Contrôlez performances

---

## 🎯 Parcours recommandé

```
Semaine 1 : Projet 1 (Banque) - Facile
  ├─ Analyse (jour 1)
  ├─ Conception (jour 1)
  ├─ Implémentation (jour 2)
  └─ Données + requêtes (jour 2)

Semaine 2-3 : Projet 2 (Paie) - Moyen
  ├─ Analyse (jour 1-2)
  ├─ Conception (jour 1-2)
  ├─ Implémentation (jour 2-3)
  └─ Données + requêtes (jour 2-3)

Semaine 4-6 : Projet 3 (Assurance) - Avancé
  ├─ Analyse complète (jour 2-3)
  ├─ Conception complexe (jour 2-3)
  ├─ Implémentation (jour 3-4)
  └─ Données + requêtes (jour 3-4)
```

---

## 📚 Ressources partagées

### Templates & Guides
- Template MCD/MLD : [`ressources/template-mcd.txt`](./ressources/template-mcd.txt)
- Template SQL : [`ressources/template-schema.sql`](./ressources/template-schema.sql)
- Checklist validation : [`ressources/checklist-projet.md`](./ressources/checklist-projet.md)

### Outils
- Draw.io : Dessiner MCD/MLD
- SQLiteOnline : Tester SQL online
- DBeaver : Desktop SQL client

---

## ✅ Critères d'évaluation (générique)

Pour chaque projet :

| Critère | Pas OK | OK | Excellent |
|---------|--------|----|---------| 
| **MCD** | Incomplet | Complet, bon | Complet, normalisé |
| **MLD** | Erreurs | Correct | Optimisé |
| **Schéma SQL** | Syntaxe erreurs | Correct | Performant |
| **Données** | Incomplètes | Complètes | Réalistes & volumineuses |
| **Requêtes** | Basiques | Correctes | Complexes & utiles |
| **Documentation** | Absente | Présente | Détaillée |

---

## 🎓 Progression

```
Module 1 (Fondations)
    ↓
Module 2 (SQL)
    ↓
Projet 1 (Banque) ← Facile
    ↓
Projet 2 (Paie) ← Moyen
    ↓
Projet 3 (Assurance) ← Avancé
    ↓
Module 4 (Systèmes Intégrés)
    ↓
🏆 COMPÉTENCE COMPLÈTE
```

---

## 💡 Conseils pour réussir

1. **Commencez simple** : Projet 1 avant les autres
2. **Testez constamment** : Insérez données, exécutez requêtes
3. **Respectez normalisation** : Évite redondance et erreurs
4. **Documentez** : MCD, MLD, requêtes expliquées
5. **Demandez feedback** : Montrez vos designs aux pairs
6. **Comparez solutions** : Voyez comment d'autres conçoivent

---

## 📝 Livrables attendus

Pour chaque projet :
```
projet-X-{nom}/
├── description.md           # Vue métier
├── requirements.md          # Cahier des charges
├── mcd-diagramme.png        # Diagramme MCD
├── schema-solution.sql      # CREATE TABLE
├── donnees-test.sql         # INSERT
├── requetes.sql             # SELECT analytiques
└── guide-evaluation.md      # Critères
```

---

## 🌐 Continuité pédagogique

- ✅ **Module 1** → Théorie + diagrammes
- ✅ **Module 2** → Requêtes SQL
- ✅ **Module 3** → Application complète (vous êtes ici)
- ✅ **Module 4** → Systèmes professionnels

---

*Last updated: 2026-05-05*  
*Status: Structure template — projets à développer*
