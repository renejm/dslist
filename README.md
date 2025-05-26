# DSList - Games Catalog API

A Spring Boot REST API for managing a catalog of electronic games.

This application was developed by Rene J. Martins during the DevSuperior's Java Spring Intensive Course in May 2025, taught by Nélio Alves.

## Technologies

- Java 21
- Spring Boot 3
- JPA / Hibernate
- H2 Database (test)
- PostgreSQL (dev/prod)
- Maven

## REST Endpoints

The application provides the following endpoints:

### Games

- `GET /games` - Retrieves a list of all games
- `GET /games/{id}` - Retrieves detailed information about a specific game

### Game Lists (Categories)

- `GET /lists` - Retrieves all game categories/lists
- `GET /lists/{id}/games` - Retrieves all games belonging to a specific category/list
- `POST /lists/{id}/replacement` - Repositions a game within a category/list

## API Documentation

### Get All Games

```
GET /games
```

Returns a list of games with basic information.

### Get Game Details

```
GET /games/{id}
```

Returns detailed information about the game with the specified ID.

### Get All Game Lists

```
GET /lists
```

Returns all available game lists/categories.

### Get Games by List

```
GET /lists/{id}/games
```

Returns all games belonging to the list/category with the specified ID.

### Reposition Game in List

```
POST /lists/{id}/replacement
```

Repositions a game within a list/category.

Request body example:

```json
{
  "sourceIndex": 1,
  "destinationIndex": 3
}
```

## Running the Application

### Prerequisites

- Java 21 or higher
- Maven
- PostgreSQL (for dev/prod environments)

### Setup and Running

1. Clone the repository

2. Configure the database connection in `application-dev.properties` or `application-prod.properties`

3. Build the project:

```
./mvnw clean install
```

4. Run the application:

```
./mvnw spring-boot:run
```

By default, the application will start on port 8080.

## Environment Configuration

The application supports different environments:

- `test`: Uses H2 in-memory database
- `dev`: Development configuration with PostgreSQL
- `prod`: Production configuration

To specify the environment, use the following parameter when starting the application:

```
./mvnw spring-boot:run -Dspring.profiles.active=dev
```

## Docker Support

The application includes Docker support. To run using Docker:

```
docker-compose up
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.
