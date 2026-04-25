# 🗳️ Advance Voting System

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Node.js](https://img.shields.io/badge/Node.js-✓-green.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-✓-green.svg)
![Biometrics](https://img.shields.io/badge/Security-Biometrics-blueviolet.svg)

A secure, full-stack E-Voting System designed for transparent and tamper-proof elections. It utilizes a **Biometric Facial Recognition Engine** to verify voters in real-time, coupled with a blockchain-like **SHA-256 hash chaining** mechanism to ensure absolute vote integrity. 

Built with a minimalist and extremely fast Vanilla JS frontend, an Express/Node.js backend, and a MongoDB database, the system sports a premium glassmorphic UI with dynamic dark/light themes.

---

## ✨ Key Features

- 👤 **Biometric Authentication**: Uses AI (`face-api.js`) for 1:1 local facial recognition in the browser, ensuring identity verification before a vote can be cast. No actual photos are ever saved to the server.
- 🛡️ **Vote Integrity (Anti-Tamper)**: Every vote generates a unique SHA-256 cryptographic hash based on the voter ID, candidate ID, and timestamp. Any database tampering immediately breaks the hash chain.
- 👥 **Role-Based Access Control (RBAC)**: Distinct User (Voter) and Admin dashboards. Admins exclusively manage elections and candidates.
- 🌗 **Premium UI**: Responsive, glassmorphic design featuring dark/light mode toggles and smooth micro-animations.
- 📊 **Real-time Analytics**: Built with `Socket.io` and `Chart.js` for real-time live election results, turnout tracking, and dynamic pie/bar charts.
- 🧾 **Digital Receipts**: Automated email confirmation receipts sent via Nodemailer once a vote is successfully cast.
- 🔒 **Secure Data**: Passwords encrypted with bcrypt, robust JSON Web Tokens (JWT) for session management, and comprehensive Audit Logging for accountability.

---

## 🛠️ Tech Stack

**Frontend (Client-Side)**
- HTML5, CSS3 (Glassmorphism design system)
- Vanilla JavaScript
- `face-api.js` (for localized biometric processing)
- `Chart.js` (for analytics)

**Backend (Server-Side)**
- Node.js & Express.js
- MongoDB & Mongoose ODM
- `bcryptjs` & `jsonwebtoken` (Auth & Security)
- `crypto` (SHA-256 Hashing)
- `Socket.io` (Real-time updates)
- `Nodemailer` (Email notifications)

---

## 🚀 How the Biometric Engine Works

1. **Registration Phase**: The user looks at their webcam. The browser loads lightweight AI models, detects 68 facial landmarks, and generates a 128-dimensional array (a `faceDescriptor`). This array is securely saved to the database.
2. **Voting Phase**: The server sends the saved array back to the user's browser. The webcam activates, scans the live face, and calculates the Euclidean Distance between the two. If the match confidence is **70% or higher**, the vote is unlocked.

---

## 📦 Installation & Setup

Follow these steps to set up the project locally:

1. **Clone the repository**
   ```bash
   git clone https://github.com/Rish2024/Advance-Voting-System.git
   cd Advance-Voting-System/Backend-Project-main
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Configure Environment Variables**
   Create a `.env` file in the root directory and add your configuration details. Here is an example:
   ```env
   PORT=3000
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_super_secret_jwt_key
   EMAIL_USER=your_email@gmail.com
   EMAIL_PASS=your_app_password
   ```

4. **Start the Application**
   ```bash
   # Start in development mode (auto-restarts on save)
   npm run dev
   
   # Or start normally
   npm start
   ```

---

## 💻 Usage

Once the server is running, visit `http://localhost:3000` in your web browser.

- **Voters**: Register a new account, configure your Face ID, and start voting in active elections.
- **Admins**: Login using the default seeded Admin credentials (`admin@evote.com` / `Admin@123`). From the admin panel, you can create elections, manage candidates, monitor live results, and view secure audit logs.

---

## 🤝 Contributing

Developer contributions are highly encouraged. Please follow standard Git workflow:
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License.

## 📧 Contact

**Author**: Hrishabh
**GitHub**: [@Rish2024](https://github.com/Rish2024)
