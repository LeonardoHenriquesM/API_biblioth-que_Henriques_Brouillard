# TP_SpringBoot_Henriques_Brouillard (tp.leothy.springboot)

#  API de Gestion de Bibliothèque (Spring Boot)

Projet backend développé pour approfondir la maîtrise des architectures RESTful et des standards du développement Java en entreprise.

##  Stack Technique
* **Framework** : Spring Boot
* **Langage** : Java
* **Base de données** : H2 (en mémoire pour le développement)
* **Outillage** : 
    * **Lombok** (pour réduire le code répétitif/boilerplate)
    * **Swagger/OpenAPI** (pour une documentation API interactive)
* **Build** : Maven

##  Fonctionnalités clés
* **CRUD Complet** : Gestion intégrale des entités Auteurs et Livres.
* **Recherche & Filtrage** : Filtrage dynamique (titre, catégorie, année) avec pagination et tri optimisés pour la performance.
* **Statistiques** : Analyse des données (top auteurs, répartition par catégorie).
* **Sécurité** : Protection des endpoints sensibles par clé API personnalisable.

##  Installation et Lancement
1. Cloner le projet : `git clone [URL_DU_REPO]`
2. Lancer l'application : `mvn spring-boot:run`
3. Accéder à l'API : `http://localhost:8080`
4. Documentation interactive (Swagger UI) : `http://localhost:8080/swagger-ui.html`

## les endpoints

### auteurs

- `GET http://localhost:8080/auteurs`
- `GET http://localhost:8080/auteurs/id`
- `POST http://localhost:8080/auteurs`
- `PUT http://localhost:8080/auteurs/id`
- `DELETE http://localhost:8080/auteurs/id`

### les livres
 `GET /livres` avec filtres :

  - `titre`
  - `identifiantAuteur`
  - `categorie` (`ROMAN`, `ESSAI`, `POESIE`, `AUTRE`)
  - `anneeMin`
  - `anneeMax`
  - pages et tri classique : `page`, `size`, `sort=anneeParution,desc`…

- `GET http://localhost:8080/livres/id`
- `POST http://localhost:8080/livres`
- `PUT http://localhost:8080/livres/id`
- `DELETE http://localhost:8080/livres/id`

### stats

- `GET http://localhost:8080/statistiques/livres_par_categorie`
- `GET http://localhost:8080/statistiques/top-auteurs`

## cle pour l'api

toutes les requêtes **POST / PUT / PATCH / DELETE** vont demander cet en-tête pour la vérification :

```http
Dans postman aller dans headers et mettre Key = cle_api et Value = trop_style
```

vous pouvez changer le nom de la cle dans `application.properties` :

```properties
application.cle-api=trop_style
```

## lombok

Les classes/DTO utilisent Lombok (`@Data`, `@Builder`, etc.) je sais plus si c'était demandé mais j'aime bien l'utiliser ça mévite de réecrire touts les getters et setters et les builders etc ..

## doc avec les explications de chaque annotation

Dans `docs/annotations_springb.md` je me suis aidé de l'ia et des docs officielles: 

python(Python – Decorators & Annotations)
java(Java – Annotations)
Jakarta EE(Jakarta EE (anciennement Java EE) – Annotations pour frameworks)
