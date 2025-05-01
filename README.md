# 🌐 Community Learning Hub

An educational web application where users can discover curated content, earn credits for meaningful engagement, and unlock premium resources. Includes a full admin/moderator panel and a feed sourced from Twitter and Reddit.

---

## ✨ Features

### 👤 User Features
- **JWT Authentication**: Secure register/login system.
- **Credit Points System**:
  - Earn credits by watching content, saving/sharing posts, or engaging daily.
  - Spend credits on premium events/resources.
  - View a detailed transaction history.
- **Feed Aggregator**:
  - Educational content from Twitter and Reddit.
  - Save, share, and report posts.
  - Preview posts with metadata (title, source, link).

### 🛡️ Admin/Moderator Panel
- Review reported content.
- Monitor top users and most saved/shared content.
- View system-wide statistics.
- Update or delete user profiles/content manually.

---

## 🛠 Tech Stack

| Layer       | Technology              |
|------------|--------------------------|
| Frontend    | React.js + Tailwind CSS |
| Backend     | Node.js + Express.js    |
| Database    | MongoDB Atlas           |
| Auth        | JWT (JSON Web Tokens)   |
| APIs Used   | Reddit API, Twitter API |
| Hosting     | Firebase (Frontend), Google Cloud Run (Backend) |

---

## 🧑‍💻 Instructions to Run Locally

### Prerequisites
- Node.js ≥ v16
- MongoDB Atlas account
- Twitter Developer API key
- Git

---

### 1. Clone the Project

```bash
git clone https://github.com/your-username/community-learning-hub.git
cd community-learning-hub
2. Backend Setup
bash
Copy
Edit
cd server
npm install
Create a .env file in server/ with the following variables:

env
Copy
Edit
PORT=5000
MONGO_URI=your_mongodb_atlas_uri
JWT_SECRET=your_jwt_secret
TWITTER_BEARER_TOKEN=your_twitter_api_key
Start the server:

bash
Copy
Edit
npm start
3. Frontend Setup
bash
Copy
Edit
cd ../client
npm install
npm start
Your app will be live at http://localhost:3000.

🚀 Deployment
🔁 Backend: Google Cloud Run
In server/, create a Dockerfile:

Dockerfile
Copy
Edit
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]
Deploy:

bash
Copy
Edit
gcloud run deploy community-learning-backend \
  --source . \
  --region us-central1 \
  --set-env-vars MONGO_URI=...,JWT_SECRET=...,TWITTER_BEARER_TOKEN=... \
  --allow-unauthenticated
💻 Frontend: Firebase Hosting
From client/:

bash
Copy
Edit
npm install -g firebase-tools
firebase login
firebase init hosting
Select dist or build as the public directory.

Build and deploy:

bash
Copy
Edit
npm run build
firebase deploy

