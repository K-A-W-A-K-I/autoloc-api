# AutoLoc API

Projet Spring Boot - API de gestion de location de véhicules

## Atelier 1 - Configuration initiale

### Technologies utilisées
- Java 17
- Spring Boot 3.2.0
- Spring Data JPA
- MySQL
- Lombok
- Maven

### Structure du projet
```
autoloc-api
├── src
│   ├── main
│   │   ├── java/tn/esprit/autoloc
│   │   │   ├── domain (entités JPA)
│   │   │   ├── repository (Spring Data JPA)
│   │   │   ├── service (couche métier)
│   │   │   ├── web
│   │   │   │   ├── controller (contrôleurs REST)
│   │   │   │   └── dto (Data Transfer Objects)
│   │   │   └── AutolocApiApplication.java
│   │   └── resources
│   │       └── application.properties
│   └── test
└── pom.xml
```

### Entités créées (sans associations)
1. **Vehicule** - Véhicules disponibles à la location
2. **Agence** - Agences de location
3. **Client** - Clients de l'application
4. **Employe** - Employés des agences
5. **Equipement** - Équipements des véhicules
6. **Reservation** - Réservations des clients
7. **Contrat** - Contrats de location
8. **Paiement** - Paiements effectués
9. **Maintenance** - Maintenances des véhicules

### Énumérations
- `StatutVehicule`: DISPONIBLE, LOUE, MAINTENANCE
- `CategorieVehicule`: CITADINE, BERLINE, SUV, UTILITAIRE
- `RoleEmploye`: AGENT, MANAGER
- `StatutReservation`: EN_ATTENTE, CONFIRMEE, ANNULEE, TERMINEE
- `ModePaiement`: CARTE, ESPECES, VIREMENT

### Configuration
Modifier le fichier `src/main/resources/application.properties` pour configurer votre base de données MySQL :
- URL: `jdbc:mysql://localhost:3306/autoloc_db?createDatabaseIfNotExist=true`
- Username: `root`
- Password: (à renseigner)

### Prérequis
- JDK 17 ou supérieur
- MySQL 8.0 ou supérieur
- Maven 3.6 ou supérieur
- IntelliJ IDEA (avec plugin Lombok activé)

### Activation de Lombok dans IntelliJ
1. File → Settings → Build, Execution, Deployment → Compiler → Annotation Processors
2. Cocher "Enable annotation processing"
3. File → Settings → Plugins → Vérifier que le plugin Lombok est installé

### Lancement de l'application
```bash
mvn spring-boot:run
```

Ou depuis IntelliJ : Clic droit sur `AutolocApiApplication.java` → Run

### Vérification
Au démarrage, Hibernate doit créer automatiquement les 9 tables dans la base de données `autoloc_db`.

Les logs SQL sont activés pour vérifier la génération du schéma.

## Prochaines étapes
- **Atelier 2**: Ajout des associations entre entités (relations JPA)
- **Atelier 3**: Création des repositories Spring Data JPA
- **Atelier 4**: Implémentation de la couche service
- **Atelier 5**: Développement des contrôleurs REST
- **Atelier 6**: Création des DTO et mapping

---
**Auteur**: Étudiant ASI 4ème année  
**Date**: Séance 2 - Atelier 1
