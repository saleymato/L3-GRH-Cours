# Contribuer à L3-GRH-Cours

Merci de votre intérêt à contribuer à cette plateforme pédagogique ! 🙌

## Types de contributions bienvenues

- 📝 **Contenus** : cours, notes, exercices, corrections
- 🐛 **Corrections** : bugs, typos, erreurs SQL, clarifications
- 💡 **Améliorations** : suggestions pédagogiques, nouvelles structures
- 📊 **Cas d'études** : mini-projets supplémentaires
- 📚 **Ressources** : données test, scripts, diagrammes

## Comment contribuer

### 1. Fork le repo
```bash
git clone https://github.com/saleymato/L3-GRH-Cours.git
cd L3-GRH-Cours
```

### 2. Créez une branche
```bash
git checkout -b feature/votre-contribution
# ex: feature/exercice-normalisation, fix/sql-syntax
```

### 3. Effectuez vos modifications

#### Pour du **contenu pédagogique** :
- Respectez le format Markdown existant
- Structurez avec des headings clairs (# Module, ## Section)
- Ajoutez des exemples concrets
- Incluez des ressources/diagrammes dans `ressources/`

#### Pour des **exercices** :
- Créez dans le dossier `exercices/`
- Format : `ex{N}-{titre}.md`
- Incluez énoncé, contexte, données test
- Placez correction dans `exercices/corrections/`

#### Pour des **mini-projets** :
- Créez dossier dans `module-03-design-bd/mini-projets/`
- Incluez : `description.md`, `requirements.md`, `schema-solution.sql`, guide d'évaluation
- Nommage : `projet-{N}-{nom}`

### 4. Testez votre contribution

Pour SQL :
```bash
# Vérifier la syntaxe avec SQLite (gratuit)
sqlite3 < votre-fichier.sql
```

Pour Markdown :
- Vérifiez la syntaxe localement (aperçu VS Code, etc.)
- Testez les liens internes

### 5. Validez votre code

```bash
# Format - respectez la structure existante
# Pas de fichiers inutiles (.DS_Store, __pycache__, etc.)

git add .
git commit -m "type: description brève"
# Types : feat (nouveau), fix (correction), docs (documentation), refactor
```

### 6. Poussez votre branche
```bash
git push origin feature/votre-contribution
```

### 7. Ouvrez une Pull Request (PR)
- Allez sur https://github.com/saleymato/L3-GRH-Cours
- Cliquez sur "New Pull Request"
- Décrivez votre contribution :
  - Quel problème résolvez-vous ?
  - Quel contenu ajoutez-vous ?
  - Pourquoi cette approche ?

---

## Guide de style

### Markdown
```markdown
# Module 1 (h1 = titre principal)

## Section principale (h2)

### Sous-section (h3)

**Gras** pour emphase
*Italique* pour nuances
`code` pour code inline

- Listes à puces
- Bien structurées
- Lisibles
```

### SQL
```sql
-- Commentaires explicatifs
SELECT column1, column2
FROM table_name
WHERE condition = 1
ORDER BY column1;

-- Noms explicites
-- UPPERCASE pour keywords SQL
-- lowercase pour noms tables/colonnes
```

### Nommage des fichiers
- Lowercase + tirets : `ex1-concepts-bd.md`
- Numérotation : `01-intro.md`, `02-fondations.md`
- Pas d'espaces ni caractères spéciaux

---

## Standards pédagogiques

Pour maintenir la qualité :

### Exercices
- ✅ Énoncé clair et contextualisé
- ✅ Difficultés graduées (⭐ ⭐⭐ ⭐⭐⭐)
- ✅ Données test réalistes
- ✅ Corrections détaillées avec explications
- ✅ Liens vers concepts pertinents

### Slides/Contenus
- ✅ Objectifs clairs en début
- ✅ Exemples concrets et pertinents
- ✅ Langage simple (pas d'jargon non expliqué)
- ✅ Synthèse/résumé en fin de section
- ✅ Ressources pour approfondir

### Mini-projets
- ✅ Cahier des charges réaliste (contexte entreprise)
- ✅ Approche progressive (étapes bien définies)
- ✅ Données initiales fournies
- ✅ Critères d'évaluation clairs
- ✅ Solution de référence complète

---

## Processus de révision

1. **Vérification automatique** : Syntax SQL, liens Markdown
2. **Révision manuelle** : Qualité pédagogique, cohérence
3. **Feedback** : L'auteur propose ajustements si nécessaire
4. **Fusion** : Approbation finale → merge dans `main`

---

## Crédits

Toute contribution sera :
- Créditée dans le fichier (auteur + date)
- Mentionnée dans les release notes
- Respectée sous la licence CC-BY-SA 4.0

---

## Questions / Aide

- 📋 Ouvrez une [issue](https://github.com/saleymato/L3-GRH-Cours/issues) pour discuter d'abord
- 💬 Utilisez [Discussions](https://github.com/saleymato/L3-GRH-Cours/discussions) pour des questions générales
- ✉️ Contactez l'auteur si besoin

---

**Merci de contribuer à une ressource pédagogique ouverte et de qualité ! 🎓**
