# C# CRUD Rest API using .NET 7, ASP.NET, Entity Framework, Postgres, Docker and Docker Compose

  - .NET 7
  - ASP.NET (Framework for building web apps)
  - Entity Framework (ORM)
  - Postgres (Database)
  - Docker (Containerization)
  - Docker Compose (To run the database and the application)

### Running the app
  ```dotnet run --urls=http://localhost:5000```

### To test the application, open a browser and go to the following URL:
- http://localhost:5000/weatherforecast

### Adding of Postgres connection string in appsetting.json:
```
"ConnectionStrings": {
  "DefaultConnection": "Host=localhost;Port=5432;Database=postgres;Username=postgres;Password=root"
}
```

### To test the Users endpoints, open a browser and go to the following URL:
- http://localhost:5000/swagger/index.html
