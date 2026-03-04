# Frontend – Social Matching Application

A Tinder-like social matching frontend built with **React, TypeScript, and Tailwind CSS**.  
Users can sign up, complete their profile, discover other users, send/accept requests, and chat in real time.

---
[Backend Repo Link](https://github.com/Hrithik06/gittogether)
---
## 🚀 Tech Stack

- **React.js**
- **TypeScript**
- **Tailwind CSS**
- **Socket.IO Client**
- **Zod** – form validation
- **AWS S3 Presigned URLs** – profile image uploads

---

## 🧭 Application Routes

### 🔐 Authentication
- `/signup` – User registration
- `/login` – User login

After signup, users are redirected to `/profile-edit` to complete their profile.

---

### 🧑‍💼 Navigation
- Navbar
  - Left: Company logo + name
  - Right: User avatar
    - Dropdown:
      - Profile → `/profile-edit`
      - Logout

---

### 👤 Profile
- `/profile-edit`
  - Update personal details
  - Upload profile image using S3 presigned URLs
- Profile completeness is enforced
  - Incomplete profiles cannot send requests (toast notification shown)

---

### 🏠 Feed
- Home page displays user cards (Tinder-style)
- Actions:
  - ✔️ Interested
  - ❌ Ignore
- Users can swipe or click buttons
- Automatically loads next user
- Excludes:
  - Logged-in user
  - Existing connections
  - Previously interacted users

---

### 🔁 Requests & Connections
- `/requests`
  - View incoming connection requests
  - Accept or reject requests
- `/connections`
  - View accepted connections
  - Option to message connected users

---

### 💬 Messaging
- Real-time chat using **Socket.IO**
- Only available between accepted connections
- Chat history persists across sessions

---

### 📨 Contact Us
- `/contact-us`
- Available only to logged-in users
- Backend fetches sender details from JWT

---

### 🧠 UX Enhancements
- Multi-select skill search
- Selected skills displayed as pills
- Toast notifications for errors & validations
- Footer pages:
  - Terms & Conditions
  - Privacy Policy

---

## 🧾 Validation Strategy

- **Zod** used for:
  - Signup/Login forms
  - Profile edit form
- Prevents invalid data before hitting backend

---

## ▶️ Running Locally

```bash
pnpm install
pnpm run dev
```

---

## 📌 Notes

* Authentication is handled via **HTTP-only cookies**
* Image uploads are done directly to S3 using presigned URLs
* Frontend and backend are deployed on a single EC2 instance in production
