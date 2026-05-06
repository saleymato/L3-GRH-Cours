# Slide 2 : Modèle Entité-Association (MCD - Merise)

> **Durée** : 60-90 minutes  
> **Niveau** : Intermédiaire (⭐⭐)  
> **Prérequis** : Slide 1 (Concepts fondamentaux)  
> **Objectif** : Concevoir des diagrammes BD avant d'écrire le SQL

---

## 📚 Table des matières

1. [Qu'est-ce qu'un MCD ?](#quest-ce-quun-mcd)
2. [Concepts clés](#concepts-clés)
3. [Entités](#entités)
4. [Relations et cardinalités](#relations-et-cardinalités)
5. [Symboles Merise](#symboles-merise)
6. [Exemples complets](#exemples-complets)
7. [Étapes pour créer un MCD](#étapes-pour-créer-un-mcd)
8. [Pièges courants](#pièges-courants)

---

## Qu'est-ce qu'un MCD ?

### 🎯 Définition

**MCD** = **Modèle Conceptuel de Données**  
(Aussi appelé **Diagramme Entité-Association** ou **ER Diagram**)

C'est un **diagramme visuel** qui :
- ✅ Représente les **entités** (tables)
- ✅ Montre les **relations** (liens entre tables)
- ✅ Indique les **cardinalités** (combien par combien)
- ✅ Aide à **concevoir** la BD avant de la créer

### 🔄 Processus

```
Cahier des charges
        ↓
    MCD (Diagramme)  ← NOUS SOMMES ICI
        ↓
    MLD (Schéma logique)
        ↓
    SQL (Code)
        ↓
    Base de données réelle
```

### 💡 Analogy

```
MCD = Plan d'une maison (avant de construire)
SQL = Maison réelle (après construction)
```

Si le plan est mauvais → la maison sera mauvaise !

---

## Concepts clés

### 📋 Les 3 piliers du MCD

| Concept | Définition | Exemple |
|---------|-----------|---------|
| **Entité** | Une classe/catégorie d'objets | Client, Produit, Facture |
| **Attribut** | Une propriété d'une entité | Nom, Email, Date de naissance |
| **Relation** | Un lien entre deux entités | Un client PASSE des commandes |

---

## Entités

### 🎁 Qu'est-ce qu'une entité ?

Une **entité** est :
- ✅ Une **classe d'objets** similaires
- ✅ Une **chose** du monde réel
- ✅ Quelque chose qu'on veut **stocker des informations** sur

### 📦 Représentation visuelle

```
┌─────────────────┐
│     CLIENT      │  ← Nom de l'entité
├─────────────────┤
│ id_client (PK)  │
│ nom             │
│ email           │
│ telephone       │
│ adresse         │
└─────────────────┘
```

### 🏦 Exemples d'entités (Banque)

```
┌──────────────┐   ┌───────────────┐   ┌──────────────┐
│    CLIENT    │   │    COMPTE     │   │ TRANSACTION  │
├──────────────┤   ├───────────────┤   ├──────────────┤
│ id_client    │   │ num_compte    │   │ id_trans     │
│ nom          │   │ solde         │   │ date         │
│ email        │   │ devise        │   │ montant      │
│ telephone    │   │ type          │   │ type         │
│ adresse      │   │ date_ouvert   │   │ description  │
└──────────────┘   └───────────────┘   └──────────────┘
```

### 🏢 Exemples d'entités (Entreprise)

```
┌─────────────┐   ┌────────────┐   ┌─────────────┐
│  EMPLOYE    │   │ DEPARTEMENT│   │   PROJET    │
├─────────────┤   ├────────────┤   ├─────────────┤
│ id_emp      │   │ id_dept    │   │ id_projet   │
│ nom         │   │ nom        │   │ nom         │
│ prenom      │   │ budget     │   │ budget      │
│ email       │   │ localisation│   │ date_debut │
│ telephone   │   │ responsable│   │ date_fin    │
└─────────────┘   └────────────┘   └─────────────┘
```

### 🔑 Clé primaire dans une entité

```
┌──────────────┐
│    CLIENT    │
├──────────────┤
│ id_client (PK)  ← Clé primaire (unique, jamais NULL)
│ nom
│ email
│ telephone
│ adresse
└──────────────┘
```

**Notation** :
- **(PK)** = Primary Key = Clé Primaire

---

## Relations et cardinalités

### 🔗 Qu'est-ce qu'une relation ?

Une **relation** est un **lien** entre deux entités.

**Exemple** :
```
Un CLIENT PASSE des COMMANDES
    ↓
Un CLIENT peut passer plusieurs COMMANDES
Une COMMANDE est passée par exactement UN CLIENT
```

### 📊 Types de relations

#### **1. Relation 1:1 (Un-à-Un)**

```
┌──────────────┐           ┌──────────────┐
│   PERSONNE   │ --- A --- │   PASSEPORT  │
└──────────────┘           └──────────────┘

Une personne a EXACTEMENT UN passeport
Un passeport appartient à EXACTEMENT UNE personne
```

**Exemple concret** :
- Chaque personne → 1 passeport unique
- Chaque passeport → 1 personne unique

---

#### **2. Relation 1:N (Un-à-Plusieurs)**

```
┌──────────────┐          ┌──────────────┐
│   CLIENT     │ --- A --- │   COMMANDE   │
└──────────────┘          └──────────────┘

Un CLIENT peut avoir PLUSIEURS COMMANDES
Une COMMANDE appartient à EXACTEMENT UN CLIENT
```

**Exemple concret** :
- Client 001 → 5 commandes
- Commande 1001 → Client 001 seulement

---

#### **3. Relation N:M (Plusieurs-à-Plusieurs)**

```
┌──────────────┐          ┌──────────────┐
│   ETUDIANT   │ --- A --- │    COURS     │
└──────────────┘          └──────────────┘

Un ETUDIANT peut suivre PLUSIEURS COURS
Un COURS peut être suivi par PLUSIEURS ETUDIANTS
```

**Exemple concret** :
- Ali suit : Maths, Français, Anglais (3 cours)
- Maths est suivi par : Ali, Fatou, Ibrahim (3 étudiants)

---

### 📍 Cardinalités Merise

La cardinalité indique : **combien par combien ?**

#### Notation Merise

```
┌──────────────┐          ┌──────────────┐
│   CLIENT     │ ──0,N─── │   COMMANDE   │
│ (0 ou 1)     │          │ (0 ou N)     │
└──────────────┘          └──────────────┘

0, 1 = la cardinalité du côté CLIENT
0, N = la cardinalité du côté COMMANDE
```

### 🎯 Interprétation

```
0, N  = Zéro ou plusieurs (0, 1, 2, 3, ... illimité)
1, N  = Un ou plusieurs (1, 2, 3, ... illimité)
0, 1  = Zéro ou un
1, 1  = Exactement un
```

---

### 📊 Tableau des cardinalités

| Notation Merise | Signification | Exemple |
|---|---|---|
| **0, 1** | Zéro ou un | Un client peut avoir 0 ou 1 assurance |
| **1, 1** | Exactement un | Un passeport → exactement 1 personne |
| **0, N** | Zéro ou plusieurs | Un client peut avoir 0 ou plusieurs factures |
| **1, N** | Un ou plusieurs | Un département a 1 ou plusieurs employés |

---

## Symboles Merise

### 🎨 Diagramme standard

```
Entité:                    Relation:
┌─────────────┐           ┌─────────────┐
│  ENTITE     │           │  RELATION   │
│ ┌───────┐   │           │ ┌─────────┐ │
│ │attr 1 │   │           │ │ Verbe   │ │
│ │attr 2 │   │           │ └─────────┘ │
│ └───────┘   │           └─────────────┘
└─────────────┘

Cardinalités:

A ──0,1── B    = A et B liées par cardinalité 0 ou 1
A ──1,N── B    = A et B liées par cardinalité 1 à plusieurs
A ──0,N── B    = A et B liées par cardinalité 0 à plusieurs
A ──1,1── B    = A et B liées par cardinalité exactement 1
```

---

## Exemples complets

### 🏦 Exemple 1 : Système Bancaire

#### Cas

Une banque gère :
- Clients (nom, email, adresse)
- Comptes (numéro, solde, devise)
- Transactions (date, montant, type)

**Règles métier** :
- 1 client peut avoir plusieurs comptes
- 1 compte appartient à 1 seul client
- 1 compte peut avoir plusieurs transactions
- 1 transaction concerne 1 seul compte

#### MCD

```
┌──────────────┐           ┌──────────────┐           ┌───────────────┐
│    CLIENT    │ ──1,N──── │    COMPTE    │ ──1,N──── │  TRANSACTION  │
├──────────────┤           ├──────────────┤           ├───────────────┤
│id_client(PK) │ AVOIR      │num_compte(PK)│ CONTENIR  │id_trans(PK)   │
│nom           │           │solde         │           │date           │
│email         │           │devise        │           │montant        │
│telephone     │           │type_compte   │           │type           │
│adresse       │           │date_ouvert   │           │description    │
└──────────────┘           └──────────────┘           └───────────────┘
```

#### Lectures du MCD

- **"Un CLIENT peut AVOIR de zéro à plusieurs COMPTES"**
- **"Un COMPTE doit CONTENIR de une à plusieurs TRANSACTIONS"**

---

### 🏢 Exemple 2 : Entreprise

#### Cas

Une entreprise gère :
- Employés (nom, email, salaire)
- Départements (nom, budget, localisation)
- Projets (nom, budget, dates)
- Compétences (nom, niveau requis)

**Règles métier** :
- 1 employé travaille dans 1 département
- 1 département a plusieurs employés
- 1 employé peut travailler sur plusieurs projets
- 1 projet peut avoir plusieurs employés
- 1 employé a plusieurs compétences
- 1 compétence peut être maîtrisée par plusieurs employés

#### MCD

```
                    ┌──────────────────┐
                    │   DEPARTEMENT    │
                    ├──────────────────┤
                    │id_dept (PK)      │
                    │nom               │
                    │budget            │
                    │localisation      │
                    └──────────────────┘
                            ▲
                            │ 1,N
                    TRAVAILLER DANS
                            │
                    ┌──────────────────┐
                    │   EMPLOYE        │ ──0,N─── AVOIR ──0,N─── COMPETENCE
                    ├──────────────────┤                         ├──────────┐
                    │id_emp (PK)       │                         │id_comp(PK)
                    │nom               │                         │nom       │
                    │email             │                         │niveau    │
                    │salaire           │                         └──────────┘
                    │date_embauche     │
                    └──────────────────┘
                            ▲
                            │ 0,N
                     TRAVAILLER SUR
                            │
                    ┌──────────────────┐
                    │   PROJET         │
                    ├──────────────────┤
                    │id_projet (PK)    │
                    │nom               │
                    │budget            │
                    │date_debut        │
                    │date_fin          │
                    └──────────────────┘
```

---

### 🎓 Exemple 3 : Université

#### Cas

Une université gère :
- Étudiants (nom, email, niveau)
- Cours (nom, code, crédit)
- Professeurs (nom, email, département)
- Salles (numéro, capacité, étage)

**Règles métier** :
- 1 étudiant suit plusieurs cours
- 1 cours est suivi par plusieurs étudiants
- 1 cours est enseigné par 1 professeur
- 1 professeur peut enseigner plusieurs cours
- 1 cours a plusieurs séances
- 1 séance se déroule dans 1 salle
- 1 salle peut accueillir plusieurs séances

#### MCD Simplifié

```
┌────────────┐  0,N        1,N  ┌────────────┐
│  ETUDIANT  │ ────────────────  │   COURS    │
├────────────┤  SUIVRE          ├────────────┤
│id_etu (PK) │                  │id_cours(PK)│
│nom         │                  │code        │
│email       │                  │nom         │
│niveau      │                  │credit      │
└────────────┘                  └────────────┘
                                        ▲
                                  1,N   │
                                ENSEIGNER
                                        │
                                ┌────────────┐
                                │ PROFESSEUR │
                                ├────────────┤
                                │id_prof (PK)│
                                │nom         │
                                │email       │
                                │specialite  │
                                └────────────┘
```

---

## Étapes pour créer un MCD

### 🎯 Processus complet

#### **Étape 1 : Identifier les entités**

À partir du cahier des charges, listez :
- "Qu'est-ce qu'on veut stocker ?"
- "Quelles informations recueillir ?"

**Exemple Banque** :
```
✅ Client
✅ Compte
✅ Transaction
```

---

#### **Étape 2 : Identifier les attributs**

Pour chaque entité, listez les propriétés :
- "Quoi stocker sur chaque client ?"
- "Quoi stocker sur chaque compte ?"

**Exemple Banque** :
```
CLIENT:
  - nom
  - email
  - telephone
  - adresse

COMPTE:
  - numero
  - solde
  - devise
  - type_compte
```

---

#### **Étape 3 : Identifier les clés primaires**

Pour chaque entité, trouvez l'identifiant unique :

**Exemple Banque** :
```
CLIENT:
  - id_client (PK) ← Unique pour chaque client

COMPTE:
  - num_compte (PK) ← Unique pour chaque compte

TRANSACTION:
  - id_transaction (PK) ← Unique pour chaque transaction
```

---

#### **Étape 4 : Identifier les relations**

Trouvez les liens entre entités :
- "Un client PASSE combien de commandes ?"
- "Une commande appartient à combien de clients ?"

**Exemple Banque** :
```
CLIENT ──? COMPTE
  └─ "Un client peut avoir plusieurs comptes"
  └─ "Un compte appartient à 1 client"
  └─ Relation : 1:N (Un-à-Plusieurs)

COMPTE ──? TRANSACTION
  └─ "Un compte a plusieurs transactions"
  └─ "Une transaction concerne 1 compte"
  └─ Relation : 1:N (Un-à-Plusieurs)
```

---

#### **Étape 5 : Identifier les cardinalités**

Pour chaque relation, précisez : **combien par combien ?**

```
CLIENT ──0,N────1,1── COMPTE

Lire : "Un client a de zéro à plusieurs comptes"
       "Un compte appartient à exactement un client"
```

---

#### **Étape 6 : Dessiner le MCD**

Utilisez un outil (Draw.io, Lucidchart, MySQL Workbench) pour :
- Placer les entités
- Tracer les relations
- Ajouter les cardinalités

---

## Pièges courants

### ❌ Piège 1 : Oublier une entité

**Mauvais** :
```
CLIENT ──── COMMANDE

# Oublie la table PRODUIT et la relation entre COMMANDE et PRODUIT
```

**Bon** :
```
CLIENT ──── COMMANDE ──── PRODUIT

# Complète : montre l'article commandé
```

---

### ❌ Piège 2 : Mal interpréter les cardinalités

**Mauvais** :
```
CLIENT ──1,1── FACTURE

# Faux ! Un client peut avoir plusieurs factures
```

**Bon** :
```
CLIENT ──0,N── FACTURE

# Correct : Un client peut avoir 0, 1, 2, ... factures
```

---

### ❌ Piège 3 : Stocker des données calculées

**Mauvais** :
```
COMMANDE:
  - montant_total  ❌ (peut être calculé depuis les articles)
```

**Bon** :
```
COMMANDE:
  - date_commande  ✅ (info essentielle)
  - statut         ✅ (info essentielle)

# Le montant_total se calcule depuis les articles
```

---

### ❌ Piège 4 : Relations N:M mal gérées

**Mauvais** (en SQL, pas possible directement) :
```
ETUDIANT ──N,N── COURS

# Ne peut pas stocker directement dans SQL
```

**Bon** (créer une table junction) :
```
ETUDIANT ──0,N── INSCRIPTION ──1,N── COURS

# La table INSCRIPTION relie ETUDIANT et COURS
```

---

## 🎯 Résumé

### 📌 Points clés à retenir

1. ✅ **MCD** = diagramme **avant** écrire SQL
2. ✅ **Entité** = classe d'objets (CLIENT, PRODUIT)
3. ✅ **Relation** = lien entre entités (PASSE, CONTIENT)
4. ✅ **Cardinalité** = combien par combien ? (0,1 / 1,N)
5. ✅ **Types** : 1:1 / 1:N / N:M
6. ✅ **Clé primaire** = identifiant unique (PK)

---

## 📚 Ressources supplémentaires

### 🔗 Fichiers connexes
- **Slide 1** : `slides/01-concepts-fondamentaux.md` (révision)
- **Exercice 2** : `exercices/ex2-mcd.md` (pratique)
- **Glossaire** : `ressources-transversales/glossaire.md`

### 🛠️ Outils recommandés
- **Draw.io** : Gratuit, web, simple
- **Lucidchart** : Freemium, puissant
- **MySQL Workbench** : Gratuit, spécialisé BD

---

## ❓ Questions fréquentes

**Q1 : Différence entre MCD et MLD ?**  
R : MCD = conceptuel (design) / MLD = logique (schéma SQL)

**Q2 : Pourquoi pas directement écrire SQL ?**  
R : MCD aide à visualiser, éviter erreurs, discuter avec clients/équipe

**Q3 : Comment gérer N:M en SQL ?**  
R : Créer table junction (ex: INSCRIPTION entre ETUDIANT et COURS)

**Q4 : Peut-on avoir plusieurs clés primaires ?**  
R : Non, une seule clé primaire par entité. (Mais plusieurs clés candidates)

---

## 🏁 Conclusion

Le MCD est **ESSENTIEL** pour :
- 📋 Clarifier les besoins
- 🎨 Visualiser la structure
- 🔍 Vérifier la cohérence
- 👥 Communiquer avec l'équipe
- 🐛 Éviter les erreurs coûteuses

**Sans bon MCD → BD chaotique** ❌  
**Avec bon MCD → BD solide** ✅

---

## 🎓 Prochaines étapes

| Étape | Fichier | Status |
|-------|---------|--------|
| 1️⃣ Slide 1 | `slides/01-concepts-fondamentaux.md` | ✅ Complété |
| 2️⃣ Exercice 1 | `exercices/ex1-concepts.md` | ✅ Complété |
| 3️⃣ **Slide 2** | `slides/02-mcd-merise.md` | ✅ **VOUS ÊTES ICI** |
| 4️⃣ Exercice 2 | `exercices/ex2-mcd.md` | ⏳ Prochainement |
| 5️⃣ Slide 3 | `slides/03-normalisation.md` | ⏳ À créer |

---

*Last updated: 2026-05-06*  
*Niveau : Intermédiaire (⭐⭐)*  
*Prochaine étape : Exercice 2 - Concevoir des MCD*
