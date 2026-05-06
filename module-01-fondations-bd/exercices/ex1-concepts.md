# Exercice 1 : Concepts Fondamentaux des Bases de Données

> **Niveau** : Débutant (⭐)  
> **Durée estimée** : 30-45 minutes  
> **Prérequis** : Avoir suivi la Slide 1 (Concepts fondamentaux)  
> **Objectif** : Maîtriser les concepts clés : tables, colonnes, lignes, clés primaires, types de données

---

## 📋 Vue d'ensemble

Cet exercice comporte **3 exercices progressifs** :

1. **Ex 1.1** : Identifier tables et colonnes dans un cas réel
2. **Ex 1.2** : Choisir les types de données appropriés
3. **Ex 1.3** : Définir les clés primaires

Chaque exercice a :
- ✅ Un énoncé clair
- ✅ Des indices si nécessaire
- ✅ Une correction détaillée avec explications

---

## 🎯 Exercice 1.1 : Identifier tables et colonnes

### 📝 Énoncé

Une **université** doit gérer ses étudiants. Voici les informations qu'elle veut stocker :

```
Étudiant 1 :
- Numéro d'étudiant : 001
- Nom : Ali Sow
- Prénom : Ali
- Email : ali.sow@univ.ne
- Date de naissance : 15-05-2004
- Adresse : Niamey, Niger
- Filière : Informatique
- Année d'étude : L3

Étudiant 2 :
- Numéro d'étudiant : 002
- Nom : Fatou Diallo
- Prénom : Fatou
- Email : fatou.d@univ.ne
- Date de naissance : 22-08-2003
- Adresse : Maradi, Niger
- Filière : Gestion
- Année d'étude : L3
```

### ❓ Questions

**1. Quelle(s) table(s) voyez-vous ?**

💡 *Indice* : Qu'est-ce qu'on décrit ? Une seule catégorie d'informations ?

**2. Quelles colonnes pour cette table ?**

💡 *Indice* : Listez tous les attributs (caractéristiques) des étudiants

**3. Combien de lignes dans la table ?**

💡 *Indice* : Combien d'étudiants avons-nous ?

---

## ✅ CORRECTION 1.1

### Réponse 1 : Table(s)

```
TABLE : etudiants
```

**Explication** :
- On décrit une seule catégorie d'information : les étudiants
- Donc : 1 table
- Si on avait aussi les professeurs, cours, etc., ce serait plusieurs tables

---

### Réponse 2 : Colonnes

```
TABLE: etudiants
├── num_etudiant
├── nom
├── prenom
├── email
├── date_naissance
├── adresse
├── filiere
└── annee_etude
```

**Sous forme de tableau** :

| num_etudiant | nom | prenom | email | date_naissance | adresse | filiere | annee_etude |
|---|---|---|---|---|---|---|---|
| 001 | Sow | Ali | ali.sow@univ.ne | 15-05-2004 | Niamey, Niger | Informatique | L3 |
| 002 | Diallo | Fatou | fatou.d@univ.ne | 22-08-2003 | Maradi, Niger | Gestion | L3 |

**Explication** :
- Chaque caractéristique d'un étudiant = 1 colonne
- Chaque étudiant = 1 ligne
- Total : 8 colonnes

---

### Réponse 3 : Lignes

```
Nombre de lignes : 2
```

**Explication** :
- Ali = 1 ligne
- Fatou = 1 ligne
- **Total : 2 lignes**

---

## 🎯 Exercice 1.2 : Choisir les types de données

### 📝 Énoncé

Pour la table `etudiants` créée à l'exercice 1.1, **choisissez le type de données** pour chaque colonne :

| Colonne | Type ? |
|---------|--------|
| num_etudiant | ? |
| nom | ? |
| prenom | ? |
| email | ? |
| date_naissance | ? |
| adresse | ? |
| filiere | ? |
| annee_etude | ? |

**Types disponibles** :
- `INT` : nombre entier (1, 42, 1000)
- `VARCHAR(n)` : texte jusqu'à n caractères ("Ali", "ali@univ.ne")
- `TEXT` : texte long (descriptions)
- `DATE` : date (2004-05-15)
- `DECIMAL(n,d)` : nombre avec décimales (99.99)
- `BOOLEAN` : vrai/faux

### 💡 Indices

- **num_etudiant** : Un identifiant numérique
- **nom, prenom** : Du texte court
- **email** : Du texte court, format email
- **date_naissance** : C'est une date !
- **adresse** : Du texte, potentiellement long (rue, quartier, ville, pays)
- **filiere** : Du texte court (Informatique, Gestion, etc.)
- **annee_etude** : Texte court (L1, L2, L3, M1, M2)

---

## ✅ CORRECTION 1.2

### Réponse

| Colonne | Type | Pourquoi ? |
|---------|------|-----------|
| num_etudiant | INT | Identifiant numérique |
| nom | VARCHAR(50) | Texte court, max 50 caractères |
| prenom | VARCHAR(50) | Texte court, max 50 caractères |
| email | VARCHAR(100) | Email, max 100 caractères |
| date_naissance | DATE | Format date (YYYY-MM-DD) |
| adresse | VARCHAR(200) | Texte moyen (rue, ville, pays) |
| filiere | VARCHAR(50) | Texte court (Informatique, Gestion) |
| annee_etude | VARCHAR(10) | Texte court (L1, L2, L3) |

### Explication détaillée

**INT vs VARCHAR ?**
- `num_etudiant = INT` : C'est un nombre → INT
- `nom = VARCHAR` : C'est du texte → VARCHAR

**Pourquoi VARCHAR et pas TEXT ?**
- `VARCHAR(50)` = texte jusqu'à 50 caractères maximum (optimisé)
- `TEXT` = texte sans limite (pour descriptions longues)
- Pour un nom, 50 caractères c'est plus que suffisant

**Pourquoi DATE et pas VARCHAR ?**
- `date_naissance = DATE` : Permet de comparer/trier les dates
- Avec `VARCHAR("15-05-2004")`, c'est juste du texte, pas une vraie date

**Remarque importante** :
```sql
-- BON : La BD comprend que c'est une date
date_naissance DATE

-- MOINS BON : La BD traite ça comme du texte
date_naissance VARCHAR(10)
```

---

## 🎯 Exercice 1.3 : Définir les clés primaires

### 📝 Énoncé

Pour chaque scénario, **identifiez la clé primaire** (l'identifiant unique) :

#### **Scénario A : Table clients d'une banque**

| id_client | nom | email | telephone |
|---|---|---|---|
| 001 | Ali | ali@ex.com | 223-1001 |
| 002 | Fatou | fatou@ex.com | 223-1002 |
| 003 | Ibrahim | ibrahim@ex.com | 223-1003 |

**Questions** :
- Quelle colonne identifie de manière **unique** chaque client ?
- Pourquoi pas `email` ou `telephone` ?

---

#### **Scénario B : Table employés d'une entreprise**

| num_emp | nom | email | departement |
|---|---|---|---|
| E-001 | Idrissa | idrissa@ent.com | IT |
| E-002 | Mariam | mariam@ent.com | HR |
| E-003 | Moussa | moussa@ent.com | IT |

**Question** :
- Quelle est la clé primaire ?

---

#### **Scénario C : Table produits d'une boutique**

| code_produit | nom_produit | prix |
|---|---|---|
| PROD-001 | Laptop | 850000 |
| PROD-002 | Souris | 15000 |
| PROD-003 | Clavier | 25000 |

**Question** :
- Quelle est la clé primaire et pourquoi ?

---

## ✅ CORRECTION 1.3

### Scénario A : Clé primaire = `id_client`

**Explication** :
- `id_client` = unique pour chaque client ✅
- `email` : Pourrait être partagé (non-unique) ❌
- `telephone` : Pourrait être partagé ❌
- `nom` : Plusieurs Ali peuvent exister ❌

```
Clé primaire : id_client
```

---

### Scénario B : Clé primaire = `num_emp`

**Explication** :
- `num_emp` = numéro unique pour chaque employé ✅
- `nom` : Pourrait avoir doublons (Ex: 2 Moussa) ❌
- `email` : Chaque employé a un email unique, mais `num_emp` est mieux ✅
- `departement` : Plusieurs employés par département ❌

```
Clé primaire : num_emp
```

---

### Scénario C : Clé primaire = `code_produit`

**Explication** :
- `code_produit` = code unique pour chaque produit ✅
- `nom_produit` : Pourrait avoir doublons (Ex: 2 laptops) ❌
- `prix` : Plusieurs produits au même prix ❌

```
Clé primaire : code_produit
```

---

## 🎓 Règles importantes pour les clés primaires

### ✅ Une clé primaire doit être :

1. **Unique** : Pas deux lignes avec la même valeur
2. **Non-NULL** : Jamais vide
3. **Immuable** : Ne change jamais après création
4. **Simple** : Généralement un seul attribut

### ❌ Mauvais choix de clé primaire

**Exemple 1** : `nom` pour clients
```
❌ Plusieurs clients peuvent s'appeler "Ali"
```

**Exemple 2** : `email` pour employés
```
❌ Un employé pourrait changer d'email
❌ L'email pourrait être partagé
```

**Exemple 3** : `prix` pour produits
```
❌ Plusieurs produits au même prix
❌ Le prix change dans le temps
```

---

## 📊 Synthèse des concepts

### Tableau récapitulatif

| Concept | Définition | Exemple |
|---------|-----------|---------|
| **Table** | Collection de données | `etudiants` |
| **Colonne** | Attribut/caractéristique | `email`, `nom` |
| **Ligne** | Enregistrement/occurrence | Ali Sow (1 étudiant) |
| **Clé primaire** | Identifiant unique | `id_etudiant = 001` |
| **INT** | Nombre entier | `001`, `42`, `1000` |
| **VARCHAR(n)** | Texte jusqu'à n caractères | `"Ali"`, `"ali@ex.com"` |
| **DATE** | Date au format YYYY-MM-DD | `2004-05-15` |

---

## 🎯 Exercices supplémentaires (optionnel)

### Exercice bonus 1.4 : Concevoir une table

**Scénario** : Une librairie doit gérer ses **livres**. Ils veulent stocker :
- Identifiant unique du livre
- Titre
- Auteur
- Genre
- Prix
- Année de publication
- Nombre de pages

**À faire** :
1. Nommez la table
2. Listez toutes les colonnes
3. Choisissez le type de données pour chaque colonne
4. Identifiez la clé primaire

---

## ✅ CORRECTION 1.4 (Bonus)

### Réponse

```sql
TABLE: livres
┌─────────────┬─────────────────┬──────────────────┐
│   Colonne   │   Type          │   Remarque       │
├─────────────┼─────────────────┼──────────────────┤
│ id_livre    │ INT (PK)        │ Clé primaire     │
│ titre       │ VARCHAR(200)    │ Texte long       │
│ auteur      │ VARCHAR(100)    │ Nom auteur       │
│ genre       │ VARCHAR(50)     │ Roman, Science.. │
│ prix        │ DECIMAL(10,2)   │ Montant          │
│ annee_pub   │ INT             │ Année            │
│ nb_pages    │ INT             │ Nombre pages     │
└─────────────┴─────────────────┴──────────────────┘
```

### Exemple de données

| id_livre | titre | auteur | genre | prix | annee_pub | nb_pages |
|---|---|---|---|---|---|---|
| 1 | Les Misérables | Victor Hugo | Roman | 15000 | 1862 | 1464 |
| 2 | Le Seigneur des Anneaux | J.R.R. Tolkien | Fantasy | 25000 | 1954 | 1216 |
| 3 | Fondation | Isaac Asimov | Science-Fiction | 18000 | 1951 | 255 |

---

## 🚀 Pour aller plus loin

Après avoir maîtrisé cet exercice, vous êtes prêt pour :

✅ **Slide 2** : Modèle Entité-Association (MCD)  
✅ **Exercice 2** : Concevoir un MCD  
✅ **Module 2** : SQL - interroger les données

---

## 📚 Ressources utiles

- **Slide 1** : `slides/01-concepts-fondamentaux.md` (révision)
- **Glossaire** : `ressources-transversales/glossaire.md`
- **Cheat Sheet Types** : `ressources/types-donnees.md`

---

## 💡 Conseils pédagogiques

### Pour les étudiants
- ✅ Faites les exercices **sans regarder** la correction d'abord
- ✅ Comparez votre réponse avec la correction
- ✅ Comprenez **pourquoi** c'est la bonne réponse
- ✅ Refaites l'exercice 1 semaine plus tard (consolidation)

### Points clés à retenir
1. **Table** = ensemble d'entités similaires
2. **Colonne** = attribut/caractéristique
3. **Type de données** = format (INT, VARCHAR, DATE, etc.)
4. **Clé primaire** = identifiant unique, jamais NULL

---

## ✨ Prochaines étapes

| Étape | Fichier | Status |
|-------|---------|--------|
| 1️⃣ Slide 1 | `slides/01-concepts-fondamentaux.md` | ✅ Complété |
| 2️⃣ **Exercice 1** | `exercices/ex1-concepts.md` | ✅ **VOUS ÊTES ICI** |
| 3️⃣ Slide 2 | `slides/02-mcd-merise.md` | ⏳ Prochainement |
| 4️⃣ Exercice 2 | `exercices/ex2-mcd.md` | ⏳ Prochainement |

---

*Last updated: 2026-05-06*  
*Niveau : Débutant (⭐)*  
*Prochaine étape : Slide 2 - Modèle Entité-Association*
