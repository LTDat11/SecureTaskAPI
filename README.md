# SecureTaskApi

ASP.NET Core Web API (.NET 8) with PostgreSQL using Entity Framework Core.

---

## 🚀 Tech Stack

- .NET 8
- ASP.NET Core Web API
- Entity Framework Core
- PostgreSQL
- Docker (Colima)

---

## 📦 Requirements

- .NET 8 SDK
- Docker
- Colima (for macOS)

---

## 🐳 Start Docker (Colima)

Start Colima:

```bash
colima start
```

Verify Docker is running:

```bash
docker ps
```

Run PostgreSQL Container:

```bash
docker run --name securetask-postgres \
  -e POSTGRES_PASSWORD=123456 \
  -e POSTGRES_DB=securetaskdb \
  -p 5432:5432 \
  -d postgres
```

Check container:

```bash
docker ps
```

Ensure appsettings.json contains:

```
"ConnectionStrings": {
  "Default": "Host=localhost;Port=5432;Database=securetaskdb;Username=postgres;Password=123456"
}
```

Run Database Migration:

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```
Run Application:

```bash
dotnet run
```

Swagger UI:

```bash
https://localhost:xxxx/swagger
```

Verify Database
Access PostgreSQL inside container:

```bash
docker exec -it securetask-postgres psql -U postgres -d securetaskdb
```

List tables:

```bash
\dt
```

Stop PostgreSQL:
```bash
docker stop securetask-postgres
```


