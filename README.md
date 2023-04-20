# C# CRUD Rest API using .NET 7, ASP.NET, Entity Framework, Postgres, Docker and Docker Compose

## Stack
  - .NET 7
  - ASP.NET (Framework for building web apps)
  - Entity Framework (ORM)
  - Postgres (Database) (Server up and running required if Docker is not used)
  - Docker (Containerization)
  - Docker Compose (To run the database and the application)

### Running the app
  ```dotnet run --urls=http://localhost:5000```

### To test the application, open a browser and go to the following URL:
- http://localhost:5000/weatherforecast

## Postgre

### Adding of Postgres connection string in appsetting.json:
```
"ConnectionStrings": {
  "DefaultConnection": "Host=localhost;Port=5432;Database=postgres;Username=postgres;Password=root"
}
```

### User table creation script:
```
CREATE TABLE "Users" (
  "Id" SERIAL PRIMARY KEY,
  "Name" VARCHAR(50) NOT NULL,
  "Email" VARCHAR(255) NOT NULL
);
```

## Swagger (Open API)

### To test the Users endpoints, open a browser and go to the following URL:
- http://localhost:5000/swagger/index.html


### Users list endpoint:
- http://localhost:5000/api/users


---

### *Postman is recommended to get and manipulate users

### Create an user:
POST request to http://localhost:5000/api/users

json body data format:
```
{
  "name": "string",
  "email": "string"
}
```

### Get an user:
GET request to http://localhost:5000/api/users/{id}

### Update an user:
PUT request to http://localhost:5000/api/users/{id}

json body data format:
```
{
  "name": "string",
  "email": "string"
}
```

### Delete an user:
DELETE request to http://localhost:5000/api/users/{id}


---

## Docker

### Building and running the Postgre server Docker image:
```docker compose up -d db``` (To run Postgre inside Docker container. Local Postgre server, if exist, must be stopped first)

### Accesing to Postgre to create User table (Use provided script):
```docker exec -it db psql -U postgres``` (To enter to Postgre dockerized server) Use it to create de User table in the containerized Postgre server.

### Buildind the App Docker image:
```docker compose build```
### Running the app container:
```docker compose up csharp_app```
