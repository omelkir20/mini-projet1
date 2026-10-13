## Mini-projet 1 : Déployer une application web à deux niveaux avec Kubernetes (k3s)
1. Présentation du mini-projet
2. Module : Orchestration de conteneurs avec Kubernetes (k3s)
Objectif : Déployer une application web composée d'un frontend et d'une API, en utilisant des manifestes YAML versionnés dans un dépôt Git.
Le projet consiste à :
- Déployer une API avec 3 réplicas.
- Déployer un frontend avec 2 réplicas.
- Créer deux Services de type ClusterIP.
- Tester la communication interne par DNS.
- Exposer les deux applications avec Ingress et Traefik.
- Effectuer une mise à jour sans interruption et un rollback.
- Diagnostiquer et corriger une panne volontaire.
2. Architecture de l'application

L'application est composée de deux briques : le frontend, accessible à l'utilisateur, et l'API, qui fournit les données.

                     Utilisateur
                          |
                     Ingress Traefik
                    /               \
          web.k3s.local           api.k3s.local
                |                       |
          frontend-svc                api-svc
           ClusterIP                 ClusterIP
                |                       |
          Deployment                 Deployment
           frontend                     api
          2 réplicas                3 réplicas
                \                       /
                 Communication DNS
Le frontend communique avec l'API en utilisant le nom DNS de son Service. Les Services assurent la communication interne, tandis que l'Ingress permet l'accès depuis l'extérieur du cluster.
## Étape 0 : Préparer le terrain
![](cap/c1.PNG)
![](cap/c2.PNG)
![](cap/c3.PNG)
![](cap/etape0.PNG)
![](cap/etape0.1.PNG)
![](cap/etape0.2.PNG)
## Étape 1 : Déployer l'API
![](cap/etape1.PNG)
![](cap/etape1.1.PNG)
## Étape 2 : Déployer le frontend
![](cap/etape2.PNG)
![](cap/etape2.1.PNG)
## Étape 3 : Créer les Services et tester la communication interne
![](cap/etape3.PNG)
![](cap/etape3.1.PNG)
## Étape 4 : Exposer les applications avec Ingress
![](cap/etape4.PNG)
![](cap/etape4.1.PNG)
![](cap/etape4.2.PNG)
## Étape 5 : Mise à jour sans interruption
![](cap/etape5.PNG)
![](cap/etape5.1.PNG)
![](cap/etape5.2.PNG)
## Étape 6 : Panne et diagnostic
![](cap/etape6.PNG)
![](cap/etape6.1.PNG)
![](cap/etape6.2.PNG)
![](cap/etape6.3.PNG)
![](cap/etape6.4.PNG)
![](cap/etape6.5.PNG)
![](cap/etape6.6.PNG)
