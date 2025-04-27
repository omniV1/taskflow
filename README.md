# TaskFlow

**TaskFlow** is a full-stack web-based task management application designed to help individuals and teams organize, track, and manage tasks efficiently. Built with a Vite-powered React frontend and a Spring Boot backend, it provides a scalable, secure, and user-friendly solution for task productivity.

---

## 🚀 Features

- ✅ JWT-based user authentication and role-based access control
- ✅ CRUD operations on tasks (Create, Read, Update, Delete)
- ✅ Filter and sort tasks by category, due date, or priority
- ✅ Responsive UI with Vite + React + TypeScript
- ✅ Spring Boot + MySQL backend
- ✅ Password hashing using BCrypt
- ✅ Heroku/AWS-ready cloud deployment setup

---

## 📁 Project Structure

```
taskflow/
├── backend/       # Spring Boot app
│   └── src/...    # Java source files
├── frontend/      # Vite + React app
│   └── src/...    # React + TypeScript components
└── README.md
```

---

## ⚙️ Technologies

**Frontend**
- React + Vite
- TypeScript
- Axios, React Router DOM

**Backend**
- Java + Spring Boot
- Spring Security + JWT
- Spring Data JPA
- MySQL

**DevOps**
- Maven
- Git & GitHub
- Heroku Cloud Deployment

---

## 🛠 Setup Instructions

### 🔧 Backend Setup
```bash
cd backend
./mvnw spring-boot:run
```

Make sure to configure `application.properties` with your MySQL connection and JWT secret.

### ⚛️ Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

Ensure your Vite proxy is set to `http://localhost:8080` in `vite.config.ts`.

### 🗄️ Database & Prisma Local Setup

1. Ensure Postgres is installed & running
   - Install with your system package manager (e.g., `brew install postgresql` or `sudo apt-get install postgresql`), or use Docker Compose:
     ```bash
     docker-compose up -d db
     ```

2. Copy & configure your `.env` file:
   ```bash
   cp .env.example .env
   ```
   Edit `.env` and set:
   ```dotenv
   DATABASE_URL="postgresql://postgres:postgres@localhost:5432/taskflow_dev?schema=public"
   JWT_SECRET="your-secret-key-change-this-in-production"
   ```

3. Apply migrations & generate the Prisma client:
   ```bash
   npx prisma migrate dev
   npx prisma generate
   ```

4. (Optional) Launch Prisma Studio for UI data browsing:
   ```bash
   npx prisma studio
   ```

#### Handy NPM scripts

You can add these under the `scripts` section in your `package.json`:
```jsonc
{
  "scripts": {
    "migrate:dev": "prisma migrate dev",
    "db:push":     "prisma db push",
    "generate":    "prisma generate",
    "studio":      "prisma studio"
  }
}
```

---

## 🧪 Testing
- Backend: JUnit tests in `src/test/java`
- Frontend: Coming soon with Vitest / React Testing Library

---

## 📌 License
This project is licensed under the MIT License.

---

## 📫 Contact
Created by **Michael Smart** — [GitHub](https://github.com/riiansmart) | [LinkedIn](https://www.linkedin.com/in/michael-smart-47576a264/)

## 🎉 After Merge: Quick Start

After merging into `main`, teammates can get going with:

```bash
# 1. Pull latest changes & install deps
git pull origin main
cd frontend
npm install

# 2. Ensure Postgres is running
#    (system service or `docker-compose up -d db`)

# 3. Apply existing migrations
npx prisma migrate deploy

# 4. Generate the client
npx prisma generate

# 5. Open Prisma Studio
npx prisma studio
```
