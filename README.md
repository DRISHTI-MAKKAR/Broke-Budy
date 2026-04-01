# 💸 BrokeBuddy – AI Finance Assistant

BrokeBuddy is a personal finance web app for students that helps track expenses and provides AI-powered financial advice.

---

## 🚀 Features

* 💰 Track income and expenses
* 📊 View financial summary & balance
* 🤖 AI chatbot for financial advice
* 📅 Category-wise expense tracking
* 🎯 Budget awareness

---

## 🛠️ Tech Stack

* Frontend: HTML, CSS, JavaScript
* Backend: Node.js + Express
* AI: Google Gemini API

---

## 📂 Project Structure

```
Broke Buddy/
│
├── index.html
│
└── backend/
    ├── server.js
    ├── package.json
    ├── node_modules/
    └── .env
```

---

## ⚙️ Setup Instructions

### 1️⃣ Install Node.js

Download and install Node.js from:
https://nodejs.org/

Check installation:

```
node -v
npm -v
```

---

### 2️⃣ Setup Backend

Open terminal and run:

```
cd backend
npm init -y
npm install express cors dotenv
```

---

### 3️⃣ Add API Key

Create a file named `.env` inside `backend/`

```
API_KEY=your_gemini_api_key_here
```

⚠️ Do not share this key publicly.

---

### 4️⃣ Run Server

```
node server.js
```

You should see:

```
🚀 Server running on port 3000
```

---

### 5️⃣ Run Frontend

* Open `index.html` in browser
* OR use Live Server in VS Code

---

## 🧪 How to Use

1. Open the app
2. Add your expenses
3. Open chatbot
4. Ask questions like:

   * “How can I save money?”
   * “Can I afford ₹500 this week?”

---

## ⚠️ Important Notes

* Backend must be running for chatbot to work
* API key should be stored only in `.env`
* Do not expose API key in frontend

---

## 🚀 Future Improvements

* User login system
* Database integration (Supabase)
* Advanced analytics
* Voice chatbot

---

## 👨‍💻 Author

Built for hackathon 🚀
