# 🎫 Event Booking System

A full-stack web application to manage events, bookings, and user access. Built with React.js frontend, .NET 8 backend, PostgreSQL database, and deployed using Azure & Vercel.

---

## 🏗️ Architecture Overview

**Tech Stack:**
- 🔧 Backend: ASP.NET Core 8 (Web API)
- ⚛️ Frontend: React.js (Vite, Axios, Tailwind)
- 🗃️ Database: PostgreSQL (local or cloud)
- ☁️ Cloud: Azure App Service (API), Vercel (Frontend)
- 🔐 Auth: JWT-based with role-based access
- 📦 CI/CD: Azure DevOps Pipelines

---

## 📂 Project Structure

```
event-booking-system/
├── client/         # React app
├── server/         # .NET Web API
└── azure-pipelines.yml
```

---

## 🚀 Features

- 👥 User Registration & Login (JWT Auth)
- 🗓️ Browse, Search, and Filter Events
- 📥 Book/Cancel Tickets
- 🎟️ QR Code Generation for Bookings
- 📬 Email Confirmation
- 🛠️ Admin Panel (Create/Edit Events)
- 🧾 Role-based Access Control

---

## 🔧 Local Setup Instructions

### 1. Clone Repo

```bash
git clone https://github.com/your-username/event-booking-system.git
cd event-booking-system
```

### 2. Backend Setup (.NET 8)

```bash
cd server
dotnet restore
dotnet ef database update
dotnet run
```

✅ Make sure `appsettings.json` has your PostgreSQL connection string.

### 3. Frontend Setup (React + Vite)

```bash
cd client
npm install
npm run dev
```

✅ Configure `.env`:
```env
VITE_API_URL=http://localhost:5000/api
```

---

## ☁️ Deployment

### Backend (Azure App Service)

- Push code to Azure DevOps
- Use `azure-pipelines.yml` for CI/CD
- Connect App Service to deploy artifacts

### Frontend (Vercel)

- Import `client/` from GitHub
- Set `VITE_API_URL` in Vercel environment
- Auto deploy on commit

---

## 🔐 Security

- JWT Token-based auth (ASP.NET Identity)
- HTTPS enforced
- CORS configured for frontend domain
- Role-based access (`Admin`, `User`)
- Input validation using DataAnnotations
- Optional: Rate Limiting & Key Vault

---

## 🧠 Future Enhancements

- Payment Gateway Integration
- User-to-user messaging
- Calendar Sync (Google/Outlook)
- Admin analytics dashboard

---

## 🤝 Contributing

Pull requests are welcome! Please open an issue first to discuss your idea.

---

## 📄 License

MIT License. Free to use for personal and commercial projects.

---

## 📬 Contact

**Author:** Tech Hustlers  
**Email:** techhustlers@gmail.com 
**LinkedIn:** [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)
