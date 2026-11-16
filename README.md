[![Academic Year](https://img.shields.io/badge/Epitech-Tek2-green?style=for-the-badge&logo=epitech&logoColor=white)](https://www.epitech.eu/)
[![CI: Jenkins](https://img.shields.io/badge/CI-Jenkins-D24939.svg?style=for-the-badge&logo=jenkins)](https://www.jenkins.io/)
[![Module](https://img.shields.io/badge/Module-G--DOP--400-informational?style=for-the-badge)](#)

# 🤖 MyMarvin — Configuration as Code (JCasC) & Générateur de Jobs Jenkins

**MyMarvin** est un projet d'automatisation d'infrastructure CI/CD permettant de provisionner une instance **Jenkins** entièrement configurée sans aucune intervention manuelle, en combinant **Jenkins Configuration as Code (JCasC)** et **Job DSL** en Groovy.

---

## ⚙️ Composants du Projet

### 1. `my_marvin.yml` (Jenkins Configuration as Code)
- **Bannière Système Personnalisée** : `"Welcome to the Chocolatine-Powered Marvin Jenkins Instance."`.
- **Gestion des Identités (Security Realm)** :
  - Inscription libre désactivée (`allowsSignup: false`).
  - Définition d'utilisateurs locaux sécurisés par injection de variables d'environnement :
    - `chocolateen` (Hugo)
    - `vaugie_g` (Garance)
    - `i_dont_know` (Jeremy)
    - `nasso`
- **Matrice d'Autorisations** : Attribution granulaire des droits d'administration, de lecture et d'exécution de builds.

### 2. `job_dsl.groovy` (Générateur Dynamique de Pipelines)
- **Création de Dossiers** : Initialisation automatique de l'espace de travail `Tools`.
- **Job `Tools/clone-repository`** :
  - Job paramétré recevant l'URL Git d'un dépôt (`GIT_REPOSITORY_URL`).
  - Nettoie l'espace avant compilation (`preBuildCleanup`) et effectue le clone automatisé.
- **Job `Tools/SEED`** :
  - Méta-générateur de pipelines automatisant la création de jobs de compilation et de tests unitaires pour chaque projet Epitech.

---

## 🚀 Déploiement Local

Le dossier `bonus/` contient une stack Docker Compose permettant d'instancier immédiatement Jenkins avec JCasC :

```bash
cd bonus
docker compose up -d
```
L'interface d'administration Jenkins sera immédiatement accessible sur `http://localhost:8080`.
