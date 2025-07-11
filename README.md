# Gitlab-Project
Le projet consiste à tester, build, et déployer un site eCommerce avec un backend développé en Spring Boot et un frontend avec Angular. La base de données utilisée est MySQL

# Projet de Site eCommerce

## Contexte du Projet
Le projet consiste à tester, build, et déployer un site eCommerce avec un backend développé en Spring Boot et un frontend avec Angular. La base de données utilisée est MySQL.

## Technologies Utilisées
- **Angular:** 15.0.0
- **Spring Boot:** 3.0.1
- **Angular CLI:** 15.0.0
- **Node.js:** 18.12.1
- **SASS:** 1.56.0

## Variables d'Environnement
Pour la base de données MySQL, les variables d'environnement suivantes sont utilisées :
- `USERNAME`
- `PASSWORD`
- `DB_NAME`


## Images de Base pour les Dockerfiles
1. backend : `eclipse-temurin:17-jdk-alpine`
2. fronted: `node:18-alpine`
3. mysql : `mysql:8`

### Mysql Dockerfile
```dockerfile
image: mysql:8
...
EXPOSE 3306
....
```
**Énoncé de création de pipelines CI/CD sur GitLab CI pour le projet "Mero"**
 
**Contexte :** Vous faites partie de l'équipe de développement du projet "Mero", une plateforme de ecommerce. Afin d'optimiser le processus de développement et de déploiement de l'application, vous avez décidé de mettre en place des pipelines CI/CD en utilisant GitLab CI.
 
**Objectif :** Mettre en œuvre des pipelines CI/CD automatisés sur GitLab CI pour le projet "Mero" afin de garantir une intégration continue et un déploiement continu fiable.
 
**Tâches à réaliser :**
1. Configurer un runner GitLab pour exécuter les jobs du pipeline. Assurez-vous que le runner soit correctement enregistré et disponible pour exécuter les tâches définies dans le pipeline.
 
Ps : essayer d'utiliser le local et une machine EC2 comme runners.
 
2. Créer un fichier `.gitlab-ci.yml` à la racine du dépôt du projet pour définir les différentes étapes du pipeline.
 
3. Configurer les étapes du pipeline, telles que la compilation du code, l'exécution des tests unitaires et des tests d'intégration, la création des artefacts pour le backend et le frontend.
 
4. Créer une étape pour construire une image Docker et la pousser vers le registre de GitLab (Pareil backend,frontend et mysql).

5. Créer une CD pour déployer toute l'application sur une instance EC2 AWS dans des conteneurs Docker. ( Si l'étape 4 est faite)
5. Si l'étape 4 n'est pas faite, le déploiement va se derouler sur une instance EC2 dans un service tomcat, pour cela: 
Configurer une étape pour le déploiement sur un serveur Web Tomcat qui doit être installé et configuré via Ansible. ( serivce tomcat par composant : back et front)
  
7. Mettre en place des environnements distincts pour le déploiement sur des branches spécifiques, par exemple `develop`, `feature/mero`, etc.
 ( par exemple sur les branches feature, on lance juste build et test, sur develop on lance tout).
 
---
Remarques :
L'étape 4 concerne uniquement les personnes qui ont déjà travailé avec Docker.
 
Pensez à voir le contenu des fichiers pour prendre les informations nécessaires (versions, cred et tout).
 
