# Module 4 : Systèmes de Gestion Intégrés

> **Objectif** : Comprendre les systèmes de gestion complets (ERP, workflows, audit)  
> **Durée** : 2-3 semaines  
> **Niveau** : Avancé (post-Module 3)  
> **Prérequis** : Conception BD complète, requêtes SQL complexes

---

## 📋 Vue d'ensemble

Ce module couvre **l'architecture et les bonnes pratiques** dans les systèmes de gestion intégrés :

1. **Architecture ERP/SGBD** : Composants, couches
2. **Workflows et processus** : Automation, états
3. **Audit et traçabilité** : Historique, logs
4. **Sécurité des données** : Authentification, permissions, encryption
5. **Performance et scalabilité** : Indexation, partitioning, cache
6. **Maintenance et monitoring** : Backups, sauvegarde, alertes

---

## 🎯 Objectifs pédagogiques

À la fin du module, vous saurez :

- ✅ Concevoir une architecture BD scalable
- ✅ Implémenter workflows et automates
- ✅ Mettre en place audit & traçabilité
- ✅ Gérer sécurité et permissions
- ✅ Optimiser performance
- ✅ Planifier maintenance & disaster recovery

---

## 📚 Contenu pédagogique

### Partie 1 : Architecture et Systèmes Intégrés

**Slides** : [`slides/01-architecture-systemes.md`](./slides/01-architecture-systemes.md)

Topics :
- Composants d'un système de gestion
- SGBD vs application
- Architectures 2-tier, 3-tier, microservices
- Scalabilité (horizontal vs vertical)

**Cas d'étude** : [`cas-etudes/01-architecture-banque.md`](./cas-etudes/01-architecture-banque.md)
- BD centrale + succursales
- Réplication & synchronisation
- Failover & haute disponibilité

### Partie 2 : Workflows & Processus

**Slides** : [`slides/02-workflows.md`](./slides/02-workflows.md)

Topics :
- États et transitions
- Diagrammes d'état
- Validation et contraintes
- Notification et escalade

**Exemple concret** : Workflow de paie
```
État initial : "EN_CREATION"
  ↓ (données saisies)
État : "EN_ATTENTE_VALIDATION"
  ↓ (gestionnaire valide)
État : "APPROUVEE"
  ↓ (exécution)
État : "PAYEE"
```

**Cas d'étude** : [`cas-etudes/02-workflow-sinistre.md`](./cas-etudes/02-workflow-sinistre.md)
- Déclaration sinistre (assurance)
- Validation, expertise, remboursement
- Transitions & conditions

### Partie 3 : Audit & Traçabilité

**Slides** : [`slides/03-audit-traçabilite.md`](./slides/03-audit-traçabilite.md)

Topics :
- Tables d'audit (shadow tables)
- Logs des modifications (CREATE, UPDATE, DELETE)
- Qui a fait quoi ? Quand ? Comment ?
- Compliance & réglementation

**Pattern : Trigger d'audit**
```sql
CREATE TRIGGER audit_employes_update
AFTER UPDATE ON employes
FOR EACH ROW
BEGIN
  INSERT INTO audit_log (table_name, operation, old_value, new_value, user, timestamp)
  VALUES ('employes', 'UPDATE', OLD.*, NEW.*, CURRENT_USER, NOW());
END;
```

**Cas d'étude** : [`cas-etudes/03-audit-finances.md`](./cas-etudes/03-audit-finances.md)
- Traçabilité des transactions bancaires
- Piste d'audit pour conformité
- Récupération historique

### Partie 4 : Sécurité

**Slides** : [`slides/04-securite.md`](./slides/04-securite.md)

Topics :
- Authentification & autorisation
- Rôles et permissions (RBAC)
- Encryption (données, transmission)
- RGPD & protection données
- Injection SQL, XSS, malveillance

**Pattern : RBAC (Role-Based Access Control)**
```sql
-- Rôles
CREATE ROLE responsable_paie;
CREATE ROLE comptable;

-- Permissions
GRANT SELECT ON paies TO responsable_paie;
GRANT SELECT, UPDATE ON paies TO comptable;

-- Utilisateurs
CREATE USER marie@company.com;
GRANT responsable_paie TO marie@company.com;
```

**Cas d'étude** : [`cas-etudes/04-securite-banque.md`](./cas-etudes/04-securite-banque.md)
- Authentification à 2 facteurs
- Permissions par département
- Encryption données sensibles

### Partie 5 : Performance & Optimisation

**Slides** : [`slides/05-performance.md`](./slides/05-performance.md)

Topics :
- Index (simples, composés, full-text)
- EXPLAIN PLAN & query optimization
- Partitioning des données
- Cache (Redis, Memcached)
- Pagination vs LIMIT

**Exemple : Indexation**
```sql
-- Avant (requête lente)
SELECT * FROM transactions WHERE date_transaction > '2024-01-01';

-- Solution : Ajouter index
CREATE INDEX idx_transactions_date ON transactions(date_transaction);

-- Bonus : Index composite
CREATE INDEX idx_employes_dept_nom ON employes(departement, nom);
```

**Cas d'étude** : [`cas-etudes/05-performance-assurance.md`](./cas-etudes/05-performance-assurance.md)
- BD de 1M+ sinistres
- Requêtes analytiques lentes
- Stratégies d'optimisation

### Partie 6 : Maintenance & Monitoring

**Slides** : [`slides/06-maintenance.md`](./slides/06-maintenance.md)

Topics :
- Backups & restore
- Disaster recovery (RTO, RPO)
- Monitoring & alertes
- Réplication & redundance
- Migrations & mises à jour

**Checklist maintenance**
- Backups quotidiens ✅
- Tests de restauration
- Monitoring des performances
- Logs d'erreurs
- Capacity planning

**Cas d'étude** : [`cas-etudes/06-dr-entreprise.md`](./cas-etudes/06-dr-entreprise.md)
- Plan de réaction sinistre
- RTO = 1h, RPO = 15min
- Stratégies de réplication

---

## 🔬 Ressources

### Diagrammes & Templates
- Architecture 3-tier : [`ressources/architecture-3tier.txt`](./ressources/architecture-3tier.txt)
- Diagramme workflow : [`ressources/workflow-template.txt`](./ressources/workflow-template.txt)
- Modèle d'audit : [`ressources/audit-template.sql`](./ressources/audit-template.sql)

### Outils recommandés
- **pgAdmin** : Interface PostgreSQL
- **MySQL Workbench** : MySQL + design
- **DBeaver** : Multi-SGBD, puissant
- **Grafana** : Monitoring
- **Prometheus** : Métriques

---

## ✅ Évaluation

Capacités attendues :

| Capacité | Niveau |
|----------|--------|
| Concevoir architecture BD scalable | Avancé |
| Implémenter audit & traçabilité | Moyen |
| Gérer sécurité (RBAC) | Moyen |
| Optimiser requêtes SQL | Avancé |
| Planifier maintenance | Moyen |

---

## 🎓 Après ce module

✅ Vous êtes **compétent complet** en gestion de BD professionnelles ! 🏆

---

## 📌 Notes pédagogiques

- **Théorique + pratique** : Montrez des configurations réelles
- **Cas réalistes** : Mettez l'accent sur les défis d'entreprise
- **Sécurité en priorité** : Insistez sur les bonnes pratiques
- **Monitoring continu** : Ne pas ignorer après déploiement

---

*Last updated: 2026-05-05*  
*Status: Structure template — contenu à développer*
