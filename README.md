# Pokemon Review API

## 📌 Overview
The **Pokemon Review API** is a RESTful API built with **ASP.NET Core** and **Entity Framework Core**. It allows users to manage Pokemon reviews, categories, owners, and more using an **in-memory database** or **SQL Server**.

## 🚀 Features
- CRUD operations for Pokemon, Reviews, Categories, Owners, and Reviewers.
- Uses **AutoMapper** for DTO mapping.
- Implements **Repository Pattern** for data access.
- Supports both **SQL Server** and **In-Memory Database**.
- API documentation via **Swagger**.

## 📂 Project Structure
```
PokemonReviewApp/
│── Controllers/        # API Controllers
│── Data/              # Entity Framework DbContext
│── Dto/               # Data Transfer Objects
│── Interfaces/        # Repository Interfaces
│── Models/            # Entity Models
│── Repository/        # Repository Implementations
│── Program.cs         # Application Startup
│── README.md          # Project Documentation
```

## 🛠 Installation & Setup
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/PokemonReviewApp.git
cd PokemonReviewApp
```

### 2️⃣ Install Dependencies
```bash
dotnet restore
```

### 3️⃣ Run the API
#### ▶ Using In-Memory Database (Default)
```bash
dotnet run
```
#### ▶ Using SQL Server (Modify `Program.cs`)
- Update `Program.cs`:
```csharp
builder.Services.AddDbContext<DataContext>(options =>
{
    options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection"));
});
```
- Configure `appsettings.json` with your **SQL Server** connection string:
```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=PokemonReviewDb;Trusted_Connection=True;"
}
```
- Run the app:
```bash
dotnet run
```

## 🌍 API Endpoints
| Method | Endpoint                  | Description                     |
|--------|---------------------------|---------------------------------|
| GET    | `/api/pokemon`            | Get all Pokemon                |
| GET    | `/api/pokemon/{id}`       | Get Pokemon by ID              |
| GET    | `/api/pokemon/{id}/rating`| Get Pokemon rating             |
| POST   | `/api/pokemon`            | Create a new Pokemon           |
| PUT    | `/api/pokemon/{id}`       | Update Pokemon                 |
| DELETE | `/api/pokemon/{id}`       | Delete Pokemon                 |
| GET    | `/api/categories`         | Get all categories             |
| POST   | `/api/categories`         | Create a new category          |
| GET    | `/api/reviews`            | Get all reviews                |
| GET    | `/api/reviews/{id}`       | Get review by ID               |
| GET    | `/api/reviews/pokemon/{id}` | Get reviews for a Pokemon  |

_(More endpoints available, check **Swagger**)_

## 📜 Swagger API Docs
Once the app is running, open:
```
http://localhost:<port>/swagger/index.html
```

## ✅ Contributing
Feel free to **fork** this repo, **open issues**, and **submit PRs**. Suggestions and improvements are welcome!

## 📄 License
This project is licensed under the **MIT License**.


