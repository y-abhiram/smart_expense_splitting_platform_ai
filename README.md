# SplitMint — Smart Expense Splitting Platform

![Status](https://img.shields.io/badge/status-production--ready-success)
![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

**A production-grade expense splitting and group management platform** that simplifies shared finances with intelligent balance calculations and minimal settlements.

[Live Demo](#) · [Report Bug](https://github.com/y-abhiram/Smart-Expense-Splitting-Platform/issues) · [Request Feature](https://github.com/y-abhiram/Smart-Expense-Splitting-Platform/issues)

---

## 🎥 [📹 Watch Demo Video](https://github.com/y-abhiram/smart_expense_splitting_platform/blob/main/demo.mp4)

> Watch the full demo to see SplitMint in action - from authentication to expense tracking, filtering, and settlements!

---

## 🎯 Overview

SplitMint is a web application designed to manage shared expenses across groups. Built with vanilla JavaScript and powered by Supabase, it provides:

- Real-time balance tracking across multiple participants
- Flexible expense splitting (equal, custom amounts, percentages)
- Minimal settlement transactions using greedy algorithm
- Secure authentication with persistent data storage
- Advanced filtering and search across expense history

---

## ✨ Features

### 🔐 Authentication & Security
- Secure registration/login via Supabase Auth
- Email verification workflow
- Row-Level Security (RLS) ensuring data isolation per user

### 👥 Group Management
- Create expense groups (up to 4 participants per group)
- Edit group names and participant details
- Color-coded participants for visual clarity

### 💰 Expense Tracking
- **Three split modes**:
  - Equal split across all participants
  - Custom amount per participant
  - Percentage-based distribution
- Full edit and delete capabilities

### 📊 Balance Calculations
- Greedy algorithm for minimal settlement paths
- Real-time balance updates
- Visual indicators showing who owes and who receives

### 🔍 Filtering & Search
- Full-text search across expense descriptions
- Filter by participant, date range, and amount range
- Combined filter support

### 🤖 MintSense - Natural Language Parser
- Convert natural language into structured expenses
- Example: *"Paid 1200 for dinner with Alex and Priya on 2026-04-02"*

### 📤 Data Export
- CSV export with complete transaction history
- Includes expenses, balances, and settlement suggestions

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Frontend** | Vanilla JavaScript (ES6+), CSS3, HTML5 |
| **Backend** | Supabase (PostgreSQL + Auth + RLS) |
| **Hosting** | Vercel |

### Why Vanilla JavaScript?

- No build step - Deploy in seconds
- Maximum performance - No framework overhead
- Small bundle size - Total: ~59KB
- Future-proof - Web standards never deprecate

---

## 🚀 Getting Started

### Prerequisites

See [requirements.txt](requirements.txt) for complete requirements.

**Quick checklist:**
- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+)
- Supabase account ([free tier](https://supabase.com))
- Git installed
- Python 3 / Node.js / PHP (any one for local server)

---

### Installation & Setup

#### Step 1: Clone the Repository

```bash
git clone https://github.com/y-abhiram/Smart-Expense-Splitting-Platform.git
cd Smart-Expense-Splitting-Platform
```

#### Step 2: Set Up Supabase Backend

**2.1 Create Supabase Project**

1. Go to [supabase.com](https://supabase.com) and sign up/login
2. Click **"New Project"**
3. Fill in project details:
   - **Name**: SplitMint (or any name)
   - **Database Password**: Choose a strong password
   - **Region**: Select closest to your location
4. Click **"Create new project"** and wait 2-3 minutes

**2.2 Run Database Migration**

1. In Supabase dashboard, navigate to **SQL Editor** (left sidebar)
2. Click **"New query"**
3. Open `supabase.sql` file from this repository
4. Copy ALL contents and paste into Supabase SQL Editor
5. Click **"Run"** or press `Ctrl+Enter`
6. You should see: "Success. No rows returned"

**2.3 Get Supabase Credentials**

1. In Supabase dashboard, go to **Settings** → **API**
2. Copy these values:
   - **Project URL**: `https://xyz.supabase.co`
   - **Anon public key**: `eyJhbGciOi...` (very long string)

#### Step 3: Start Local Server

Choose one option:

**Option A: Python (Recommended)**
```bash
python3 -m http.server 5173
```

**Option B: Node.js**
```bash
npx serve -p 5173
```

**Option C: PHP**
```bash
php -S localhost:5173
```

#### Step 4: Connect Supabase

1. Open `http://localhost:5173`
2. Click **"Configure Backend"** (top right)
3. Paste your **Supabase URL**
4. Paste your **Anon public key**
5. Click **"Save"**

#### Step 5: Create Account & Start Using

1. **Register**: Fill name, email, password → Click "Register"
2. **Verify**: Check email inbox (spam folder too) → Click verification link
3. **Login**: Enter email and password → Click "Login"
4. **Start**: Create groups, add expenses, track balances!

---

### Troubleshooting

| Problem | Solution |
|---------|----------|
| Backend banner won't go away | Click "Save" after entering credentials, clear cache |
| "Supabase library not loaded" | Check internet connection, refresh page |
| "Invalid credentials" | Double-check URL and key, ensure no extra spaces |
| Email not received | Check spam folder, verify email settings in Supabase |
| Port 5173 in use | Use different port: `python3 -m http.server 8080` |

---

## 🌐 Deployment

### Deploy to Vercel (Recommended)

**Option 1: One-Click Deploy**

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/y-abhiram/Smart-Expense-Splitting-Platform)

**Option 2: Manual Deploy**
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy from project directory
cd Smart-Expense-Splitting-Platform
vercel

# Follow the prompts to deploy
```

### Deploy to Netlify

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
cd Smart-Expense-Splitting-Platform
netlify deploy --prod

# Follow the prompts
```

### Deploy to GitHub Pages

```bash
# Initialize git repository (if not already done)
git init
git add .
git commit -m "Initial commit: SplitMint expense manager"

# Create GitHub repository and push
git remote add origin https://github.com/y-abhiram/Smart-Expense-Splitting-Platform.git
git branch -M main
git push -u origin main

# Enable GitHub Pages:
# 1. Go to repository Settings → Pages
# 2. Source: main branch
# 3. Save
```

Access your app at: `https://y-abhiram.github.io/Smart-Expense-Splitting-Platform`

### Post-Deployment Configuration

After deployment, users need to configure Supabase:
1. Visit your deployed app
2. Click "Configure Backend"
3. Enter Supabase credentials
4. Start using the app

---

## 📁 Project Structure

```
splitmint/
├── index.html          # Main HTML structure (7.6KB)
│                       # - Authentication forms
│                       # - Group management UI
│                       # - Expense tracking interface
│                       # - Modals and overlays
│
├── styles.css          # Complete styling (7.9KB)
│                       # - CSS variables for theming
│                       # - Responsive layouts
│                       # - Animations
│
├── app.js              # Application logic (43KB)
│                       # - Supabase client
│                       # - Authentication
│                       # - CRUD operations
│                       # - Balance calculations
│                       # - Settlement algorithm
│                       # - UI rendering
│
├── supabase.sql        # Database schema (2.5KB)
│                       # - Tables
│                       # - RLS policies
│                       # - Constraints
│
├── requirements.txt    # Prerequisites
├── README.md           # Documentation
└── vercel.json         # Deployment config
```

---

## 🏗️ Database Schema

```sql
groups (id, owner_id, name, created_at)
  │
  ├─► participants (id, group_id, name, color, owner_id)
  │     │
  │     └─► expense_participants (expense_id, participant_id, amount)
  │
  └─► expenses (id, group_id, amount, description, date, payer_id, split_mode)
```

**Key Features:**
- Row-Level Security (RLS) ensures users only access their own data
- Cascade deletion prevents orphaned records
- UUID primary keys for security

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 🙏 Acknowledgments

- **[Supabase](https://supabase.com)** - PostgreSQL, authentication, and RLS
- **[Vercel](https://vercel.com)** - Deployment and CDN
- **[MDN Web Docs](https://developer.mozilla.org)** - Web standards documentation

---

## 📧 Contact & Links

**Project Repository**: [github.com/y-abhiram/Smart-Expense-Splitting-Platform](https://github.com/y-abhiram/Smart-Expense-Splitting-Platform)

**Live Demo**: [splitmint.vercel.app](#)

**Issues & Feature Requests**: [GitHub Issues](https://github.com/y-abhiram/Smart-Expense-Splitting-Platform/issues)

---

<div align="center">

### ⭐ Star this repo if you find it useful!

**Built with vanilla JavaScript, modern web standards, and attention to detail**

[Report Bug](https://github.com/y-abhiram/Smart-Expense-Splitting-Platform/issues) · [Request Feature](https://github.com/y-abhiram/Smart-Expense-Splitting-Platform/issues) · [Contribute](https://github.com/y-abhiram/Smart-Expense-Splitting-Platform/pulls)

</div>
