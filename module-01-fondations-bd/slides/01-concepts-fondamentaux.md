# Slide 1 : Introduction aux Bases de Données

> **Durée** : 45-60 minutes  
> **Niveau** : Débutant  
> **Objectif** : Comprendre les concepts fondamentaux des BD et pourquoi elles sont essentielles

---

## 📚 Table des matières

1. [Qu'est-ce qu'une base de données ?](#quest-ce-quune-base-de-données)
2. [Données vs Information](#données-vs-information)
3. [Exemples réels](#exemples-réels)
4. [Avantages des BD](#avantages-des-bd)
5. [Concepts clés](#concepts-clés)
6. [Cas pratique : Banque](#cas-pratique--banque)

---

## Qu'est-ce qu'une base de données ?

### 🎯 Définition simple

Une **base de données (BD)** est :
- ✅ **Un ensemble organisé** de données
- ✅ **Stocké de manière persistante** (durée dans le temps)
- ✅ **Accessible et modifiable** facilement
- ✅ **Géré par un système** (SGBD)

### 💾 Exemple visuel

```
Fichier texte (MAUVAIS)                Base de données (BON)
═══════════════════════                ═══════════════════

Employe1: Ali                          TABLE: employes
Salaire: 500000                        ┌─────────┬────────┐
Poste: Manager                         │   nom   │ salaire│
                                       ├─────────┼────────┤
Employe2: Fatou                        │ Ali     │ 500000 │
Salaire: 450000                        │ Fatou   │ 450000 │
Poste: Technicien                      │ Ibrahim │ 400000 │
                                       └─────────┴────────┘
```

---

## Données vs Information

### 🔍 Distinction importante

| Donnée | Information |
|--------|-------------|
| **Fait brut, non traité** | **Donnée traitée, utile** |
| `2026-05-06` | Aujourd'hui c'est le 6 mai 2026 |
| `15000` | Solde de compte : 15 000 XOF |
| `M, F, M, M` | 75% hommes, 25% femmes |

### 📊 Processus

```
Données brutes (SGBD)
        ↓
    Requête SQL
        ↓
    Traitement
        ↓
Information utile (Rapport)
```

### 💡 Exemple métier

**Donnée brute** :
```
Client: 001, Compte: 1001, Solde: 250000
Client: 002, Compte: 1002, Solde: 180000
Client: 003, Compte: 1003, Solde: 420000
```

**Information** :
```
Solde moyen : 283 333 XOF
Solde max : 420 000 XOF
Clients avec solde < 200 000 : 2
```

---

## Exemples réels

### 🏦 Banque

```
TABLE: comptes
┌─────────┬──────────┬──────────┬─────────┐
│ num_cpte │ client   │ solde    │ devise  │
├─────────┼──────────┼──────────┼─────────┤
│ 1001    │ Ali      │ 250 000  │ XOF     │
│ 1002    │ Fatou    │ 180 000  │ XOF     │
│ 1003    │ Ibrahim  │ 420 000  │ XOF     │
└─────────┴──────────┴──────────┴─────────┘
```

**Données** : num_cpte, client, solde, devise  
**Information** : "Ali a un compte avec 250 000 XOF"

---

### 🏢 Entreprise

```
TABLE: employes
┌─────┬──────────┬────────┬───────────────────┐
│ id  │ nom      │ poste  │ date_embauche     │
├─────┼──────────┼────────┼───────────────────┤
│ 101 │ Idrissa  │ Manager│ 2020-01-15        │
│ 102 │ Mariam   │ Dev    │ 2021-06-10        │
│ 103 │ Moussa   │ Tech   │ 2022-03-20        │
└─────┴──────────┴────────┴───────────────────┘
```

---

### 🛡️ Assurance

```
TABLE: polices
┌─────────┬──────────┬─────────────┬─────────┐
│ num_pol │ client   │ type_couv   │ prime   │
├─────────┼──────────┼─────────────┼─────────┤
│ 5001    │ Aissatou │ Automobile  │ 85 000  │
│ 5002    │ Mamadou  │ Santé       │ 45 000  │
│ 5003    │ Oumou    │ Habitation  │ 120 000 │
└─────────┴──────────┴─────────────┴─────────┘
```

---

## Avantages des BD

### ✅ Pourquoi utiliser une BD ?

#### 1️⃣ **Organisation**
- Données structurées et logiques
- Facile à trouver information
- Pas de redondance inutile

#### 2️⃣ **Intégrité**
- Données cohérentes
- Pas de contradictions
- Validations automatiques

#### 3️⃣ **Performance**
- Recherche très rapide (index)
- Requêtes complexes en secondes
- Gestion de millions de lignes

#### 4️⃣ **Sécurité**
- Contrôle d'accès (qui peut voir quoi)
- Chiffrage des données sensibles
- Audit/traçabilité des modifications

#### 5️⃣ **Accès multi-utilisateurs**
- Plusieurs utilisateurs simultanément
- Transactions (tout ou rien)
- Pas de conflits

#### 6️⃣ **Sauvegarde & Récupération**
- Backups automatiques
- Récupération en cas de problème
- Continuité d'activité

---

## Concepts clés

### 📋 Vocabulaire essentiel

#### **Table (Relation)**
C'est une collection de données organisée en lignes et colonnes.

```
TABLE: clients
┌────┬─────────┬────────────┐
│ id │  nom    │   email    │
├────┼─────────┼────────────┤
│ 1  │ Ali     │ ali@ex.com │
│ 2  │ Fatou   │ fa@ex.com  │
└────┴─────────┴────────────┘
```

#### **Colonne (Attribut)**
C'est une caractéristique d'une entité.

```
Colonnes de clients : id, nom, email
```

#### **Ligne (Enregistrement)**
C'est une occurrence d'une entité.

```
Ligne 1: 1, Ali, ali@ex.com
Ligne 2: 2, Fatou, fa@ex.com
```

#### **Clé Primaire (PK)**
C'est l'identifiant unique d'une ligne.

```
Clé primaire : id
- id=1 → Ali (unique)
- id=2 → Fatou (unique)
```

#### **Type de donnée**
C'est le format de la colonne.

```
id : INT (nombre entier)
nom : VARCHAR(50) (texte jusqu'à 50 caractères)
email : VARCHAR(100) (texte)
date_embauche : DATE (date)
salaire : DECIMAL(10,2) (nombre décimal)
```

---

## Types de données courants

### 📊 Tableau des types SQL

| Type | Exemple | Utilisation |
|------|---------|-------------|
| **INT** | 42, 1000, -50 | Nombres entiers |
| **DECIMAL(10,2)** | 99.99, 1500.50 | Montants, prix |
| **VARCHAR(100)** | "Ali", "ali@ex.com" | Texte court |
| **TEXT** | Long texte | Descriptions, commentaires |
| **DATE** | 2026-05-06 | Dates |
| **DATETIME** | 2026-05-06 14:30:00 | Date et heure |
| **BOOLEAN** | TRUE, FALSE | Oui/Non |

---

## Cas pratique : Banque

### 🏦 Scénario réel

Une banque a besoin de gérer :
- ✅ Clients (nom, prénom, adresse)
- ✅ Comptes (numéro, solde, devise)
- ✅ Transactions (date, montant, type)
- ✅ Cartes bancaires (numéro, expiration)

### 💾 Structure simplifiée

```
TABLE: clients
┌────┬─────────┬────────┬──────────────┐
│ id │ nom     │ email  │ telephone    │
├────┼─────────┼────────┼──────────────┤
│ 1  │ Ali     │ ali@ex │ 223 xxxxxxx  │
│ 2  │ Fatou   │ fat@ex │ 223 yyyyyyy  │
└────┴─────────┴────────┴──────────────┘

TABLE: comptes
┌─────────┬────────┬───────────┬────────┐
│ num_cpte│ client │ solde     │ devise │
├─────────┼────────┼───────────┼────────┤
│ 1001    │ 1      │ 250 000   │ XOF    │
│ 1002    │ 2      │ 180 000   │ XOF    │
└─────────┴────────┴───────────┴────────┘

TABLE: transactions
┌────┬──────────┬──────────┬──────────┬──────────┐
│ id │ compte   │ date     │ montant  │ type     │
├────┼──────────┼──────────┼──────────┼──────────┤
│ 1  │ 1001     │ 06-05-26 │ 50 000   │ retrait  │
│ 2  │ 1001     │ 07-05-26 │ 100 000  │ depot    │
└────┴──────────┴──────────┴──────────┴──────────┘
```

### ❓ Questions qu'on peut poser

Avec une BD, on peut répondre :
- "Quel est le solde du compte 1001 ?"
- "Combien Ali a retiré en mai 2026 ?"
- "Quel client a le solde le plus élevé ?"
- "Lister tous les comptes avec solde > 200 000 XOF"

---

## 🎯 Résumé

### 📌 Points clés à retenir

1. ✅ Une **BD** = ensemble **organisé** de données
2. ✅ **Données** ≠ **Information** (traitement)
3. ✅ **Tables** = structures (lignes + colonnes)
4. ✅ **Clé primaire** = identifiant unique
5. ✅ **Types de données** = format des colonnes
6. ✅ **Avantages** = organisation, sécurité, performance

### 💡 Prochaines étapes

Dans les prochains cours, nous apprendrons :
1. **MCD** : Comment concevoir une BD (Entités + Relations)
2. **Normalisation** : Comment éviter redondance et erreurs
3. **SQL** : Comment interroger et modifier les données

---

## 🎓 Exercices pratiques

### Exercice 1.1 : Identifier une table
**Cas** : Une école avec étudiants, cours, inscriptions

❓ **Questions** :
- Quelles seraient les tables ?
- Quelles colonnes pour chaque table ?
- Quelles clés primaires ?

**Exemple de réponse** :
```
TABLE: etudiants
- id (clé primaire)
- nom
- prenom
- date_naissance
- email

TABLE: cours
- id_cours (clé primaire)
- nom_cours
- professeur
- credits
```

### Exercice 1.2 : Choisir les types de données
**Cas** : Table "employes"

❓ **Colonnes** :
- Numéro employé : ? (INT)
- Nom : ? (VARCHAR(50))
- Salaire : ? (DECIMAL(10,2))
- Date d'embauche : ? (DATE)
- Actif (oui/non) : ? (BOOLEAN)

---

## 📚 Ressources supplémentaires

### 🔗 Lectures recommandées
- Glossaire : `ressources-transversales/glossaire.md`
- Types de données : `ressources/types-donnees.md`
- Diagrammes d'exemple : `ressources/mcd-banque.png`

### 🛠️ Outils à découvrir
- **Draw.io** : Pour dessiner diagrammes BD
- **SQLiteOnline** : Pour pratiquer SQL

---

## ❓ Questions fréquentes

**Q1 : Pourquoi pas juste un fichier Excel ?**  
R : Excel n'a pas de sécurité, pas d'indexation, pas de requêtes complexes. BD = scalable !

**Q2 : Quelle est la différence entre BD et SGBD ?**  
R : BD = données / SGBD = logiciel pour gérer la BD (MySQL, PostgreSQL, SQL Server)

**Q3 : Combien de tables peut avoir une BD ?**  
R : Illimité ! Ça dépend de votre design. Petite BD : 5-10 tables. Grande : 100+ tables.

---

## 🏁 Conclusion

Les bases de données sont **essentielles** dans le monde digital :
- 💼 Gestion d'entreprise
- 🏦 Systèmes bancaires
- 🛡️ Assurances
- 📱 Applications mobiles
- 🌐 Réseaux sociaux
- ... et bien d'autres !

**Prochain cours** : Module 1 - Slide 2 : Modèle Entité-Association (MCD)

---

*Last updated: 2026-05-06*  
*Prochaine slide* : `02-mcd-merise.md`
