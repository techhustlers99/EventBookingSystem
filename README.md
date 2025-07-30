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

---

## ⚙️ Functionality & Business Logic

### 1. 👤 User Authentication & Roles

| Role            | Capabilities                          |
|-----------------|----------------------------------------|
| Guest           | View public event listings             |
| Registered User | Book events, view bookings, cancel     |
| Admin           | Create/edit/delete events, view stats  |

- Auth uses **JWT Tokens** (with ASP.NET Identity).
- Roles are enforced via `[Authorize(Roles = "Admin")]` in backend.

---

### 2. 📆 Event Listing & Filtering

- Users can browse events and filter by:
  - 📍 Location
  - 🏷 Category
  - 📅 Date Range
- Each event has a detailed page (`/events/:id`) showing:
  - Description, Date/Time, Venue, Image, Remaining Seats

---

### 3. 🎟 Ticket Booking Flow

1. **User books an event**
2. System checks seat availability
3. Booking is saved to DB (linked to User & Event)
4. A **unique QR token** is generated
5. Confirmation email sent to user (with QR code)

- Prevents overbooking using server-side seat checks
- QR codes are stored in `Bookings` table (as tokens)

---

### 4. 📲 QR Code Check-In System

- QR generated with `QRCoder` and embedded in email
- At event, staff can **scan the QR code**
- System checks token validity and booking status
- Booking status is updated to **"Checked-In"**

---

### 5. 🛠 Admin Features

| Feature           | Description                       |
|------------------|-----------------------------------|
| Add/Edit Events   | Through protected API endpoints   |
| Delete Events     | Soft delete or permanent          |
| View Bookings     | List/filter by event or user      |
| Export Attendees  | Optional CSV export               |

- Admin UI is protected in the frontend via route guards

---

### 6. 📬 Email Notifications

| Trigger              | Email Sent                      |
|----------------------|----------------------------------|
| Successful Booking   | QR Code + Event Details         |
| Cancellation         | Booking cancel confirmation     |

- Implemented with **SendGrid** or **MailKit SMTP**
- Email templates include venue, date, and ticket info

---

### 7. 🔐 Security Measures

| Area          | Protection Mechanism                  |
|---------------|----------------------------------------|
| Auth          | JWT with expiration and claims         |
| API Access    | CORS (only frontend origin allowed)    |
| DB Access     | EF Core ORM, no raw SQL                |
| HTTPS         | Enforced via Azure/Vercel              |
| Secrets       | Stored in env or Azure Key Vault       |
| Admin APIs    | Role-based authorization (`[Authorize]`) |

---

## 🧠 Future Enhancements

- 💳 Payment Gateway (Stripe/Razorpay)
- 📅 Google Calendar Sync
- ⭐ Event Ratings & Reviews
- 📊 Admin Dashboard with Charts
- 🔔 Real-Time Notifications

