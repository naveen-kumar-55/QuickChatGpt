# QuickChatGpt 🚀

A modern, full-stack AI chatbot and image generation platform built with **React 19**, **Vite**, **Tailwind CSS**, **Node.js**, **Express**, and **MongoDB**, powered by **Google Gemini 2.0 Flash** and **ImageKit AI**.

---

## 🌟 Features

- 💬 **Intelligent AI Chat**: Real-time conversational AI powered by Google Gemini (`gemini-2.0-flash`).
- 🎨 **AI Image Generation**: On-the-fly image synthesis using ImageKit AI media generation.
- 💳 **Credit & Subscription System**: Built-in credit balance tracking per user (1 credit / message, 2 credits / image).
- 💰 **Stripe Payment Gateway**: Seamless credit top-ups with Stripe checkout and webhook listeners.
- 🔐 **User Authentication**: Secure user registration, login, password hashing with bcrypt, and JWT sessions.
- 📝 **Markdown & Code Highlighting**: Rich responses featuring syntax highlighting via PrismJS and formatted markdown output.
- ⚡ **Modern Stack**: Fast Vite build system, Tailwind CSS v4 styling, and Express.js REST API.
- ☁️ **Deployment Ready**: Pre-configured with `vercel.json` for serverless deployment on Vercel.

---

## 🛠️ Tech Stack

### Frontend (`client/`)
- **React 19**
- **Vite**
- **Tailwind CSS v4**
- **React Router DOM v7**
- **Axios** (API requests)
- **React Markdown** & **PrismJS** (Rich chat rendering & syntax highlighting)
- **React Hot Toast** (Notifications)

### Backend (`server/`)
- **Node.js** & **Express 5**
- **MongoDB** & **Mongoose** (Database ORM)
- **Google Gemini API** (via OpenAI-compatible SDK)
- **ImageKit SDK** (Image generation & media storage)
- **Stripe SDK** (Payments & webhook handling)
- **JSON Web Tokens (JWT)** & **Bcrypt.js** (Auth security)

---

## 📁 Project Structure

```text
QuickChatGpt/
├── client/                      # Frontend React Application
│   ├── public/                  # Static assets & favicon
│   ├── src/
│   │   ├── assets/              # Icons & images
│   │   ├── components/          # Reusable UI components
│   │   ├── context/             # Global App & Auth state
│   │   ├── pages/               # Application routes & views
│   │   ├── App.jsx              # Main App entry component
│   │   └── main.jsx             # React DOM root
│   ├── .env.example             # Frontend environment variables template
│   ├── package.json
│   ├── vercel.json
│   └── vite.config.js
│
├── server/                      # Backend Express Application
│   ├── configs/                 # DB, ImageKit & Gemini/OpenAI setup
│   ├── controllers/             # Request handlers (auth, chat, credit, webhook)
│   ├── middlewares/             # Auth JWT middleware
│   ├── models/                  # Mongoose models (User, Chat, Transaction)
│   ├── routes/                  # API route endpoints
│   ├── .env.example             # Backend environment variables template
│   ├── package.json
│   ├── server.js                # Express entry point
│   └── vercel.json
│
├── .gitignore                   # Root gitignore
└── README.md                    # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have installed:
- [Node.js](https://nodejs.org/) (v18.x or later recommended)
- [MongoDB](https://www.mongodb.com/) (Local instance or MongoDB Atlas cluster)
- [Git](https://git-scm.com/)

---

### 1. Clone the Repository

```bash
git clone https://github.com/naveen-kumar-55/QuickChatGpt.git
cd QuickChatGpt
```

---

### 2. Configure Backend (`server/`)

1. Navigate to the server folder:
   ```bash
   cd server
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file from `.env.example`:
   ```bash
   cp .env.example .env
   ```

4. Populate your `.env` configuration:
   ```env
   PORT=3000
   JWT_SECRET=your_jwt_secret_key
   MONGODB_URI=your_mongodb_connection_string
   GEMINI_API_KEY=your_gemini_api_key

   IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
   IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
   IMAGEKIT_URL_ENDPOINT=your_imagekit_url_endpoint

   STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
   STRIPE_SECRET_KEY=your_stripe_secret_key
   STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
   ```

5. Start the backend development server:
   ```bash
   npm run server
   ```
   Server will run on `http://localhost:3000`.

---

### 3. Configure Frontend (`client/`)

1. Navigate to the client folder (in a new terminal):
   ```bash
   cd client
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create `.env` file from `.env.example`:
   ```bash
   cp .env.example .env
   ```

4. Configure the API endpoint:
   ```env
   VITE_SERVER_URL=http://localhost:3000
   ```

5. Start Vite development server:
   ```bash
   npm run dev
   ```
   Open the browser URL shown in the terminal (typically `http://localhost:5173`).

---

## 📡 API Endpoints

| Method | Endpoint | Description | Auth Required |
| --- | --- | --- | --- |
| **POST** | `/api/user/register` | Register new user | No |
| **POST** | `/api/user/login` | User login | No |
| **GET** | `/api/user/data` | Get authenticated user info & credit balance | Yes |
| **POST** | `/api/chat/create` | Create a new chat session | Yes |
| **GET** | `/api/chat/list` | Get list of user chats | Yes |
| **POST** | `/api/message/text` | Send prompt to Gemini AI | Yes |
| **POST** | `/api/message/image` | Generate AI image via ImageKit | Yes |
| **POST** | `/api/credit/stripe` | Create Stripe checkout session for credits | Yes |
| **POST** | `/api/stripe` | Stripe webhook listener | Stripe Signature |

---

## 🛡️ License

This project is licensed under the [ISC License](LICENSE).
