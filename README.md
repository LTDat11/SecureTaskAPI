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
Compose V1.

```bash
docker-compose up -d
```
Compose V2.

```bash
docker compose up -d
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
https://localhost:7125/swagger
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

## Setup ENV

Generate JWT Secret Key:
```bash
openssl rand -base64 32
```

Copy output and past to .env

Create .env file in root project following below format

```
JWT_KEY=YOUR_GENERATED_SECRET
JWT_ISSUER=SecureTaskApi
JWT_AUDIENCE=SecureTaskApiUser

DATABASE_URL=Host=localhost;Port=5432;Database=securetaskdb;Username=postgres;Password=YourPassWord
```


