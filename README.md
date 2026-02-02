<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Full-Stack AI Security Scanner

**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-security-audit)

**Author:** Rahul Allamraju  
**Date:** February 2, 2026

---

## 📋 Table of Contents
- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Environment Setup](#environment-setup)
- [Running the Application](#running-the-application)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)

---

## Overview

A comprehensive full-stack web application that performs AI-powered security vulnerability scanning on Python code. The application features a modern React frontend, Node.js backend API, and integrates Google's Gemini AI for intelligent code analysis.

### What This Project Does

- **AI-Powered Scanning**: Uses Google Gemini 2.5 Flash to analyze code for security vulnerabilities
- **Three Scan Modes**: 
  - **Quick Scan**: Fast regex-based pattern matching for common vulnerabilities
  - **AI Scan**: Deep analysis using Gemini AI
  - **Hybrid Scan**: Combines both approaches for comprehensive results
- **Interactive Web Interface**: Modern, responsive UI with real-time results
- **Severity Classification**: Vulnerabilities categorized as CRITICAL, HIGH, MEDIUM, or LOW
- **Detailed Reports**: Includes vulnerability descriptions, impacts, and fix recommendations

## Tech Stack

### Frontend
- **React 18** - UI framework
- **TypeScript** - Type-safe development
- **Vite** - Fast build tool and dev server
- **Tailwind CSS** - Utility-first styling
- **Axios** - HTTP client
- **Lucide React** - Icon library
- **React Dropzone** - File upload handling

### Backend
- **Node.js v25.5.0** - Runtime environment
- **Express** - Web framework
- **Multer** - File upload middleware
- **CORS** - Cross-origin resource sharing
- **dotenv** - Environment variable management

### AI & Security
- **Python 3.14** - Scanner implementation
- **Google Gemini 2.5 Flash** - AI model for code analysis
- **google-genai 1.61.0** - Official Gemini SDK
- **python-dotenv** - Environment configuration

## Features

### Security Detection Capabilities
- SQL Injection vulnerabilities
- Hardcoded credentials and secrets
- Weak cryptographic algorithms
- Command injection risks
- Path traversal vulnerabilities
- Insecure deserialization
- XML external entity (XXE) attacks
- Server-side request forgery (SSRF)
- Cross-site scripting (XSS) patterns
- Insecure random number generation
- Debug mode detection
- Eval() usage detection

### User Experience
- Drag-and-drop file upload
- Real-time vulnerability detection
- Expandable vulnerability cards
- Statistics overview dashboard
- Results filtering by severity
- JSON export functionality
- Responsive design for all devices

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** v25.5.0 or higher ([Download](https://nodejs.org/))
- **Python** 3.14 or higher ([Download](https://www.python.org/))
- **npm** (comes with Node.js)
- **Google Gemini API Key** ([Get one here](https://makersuite.google.com/app/apikey))

---

## 🔧 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/rahulallamraju/security-scanner.git
cd security-scanner
```

### 2. Install Node.js Dependencies

#### Backend
```bash
cd backend
npm install
cd ..
```

#### Frontend
```bash
cd frontend
npm install
cd ..
```

### 3. Set Up Python Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate

# Install Python dependencies
pip install google-genai python-dotenv
```

---

## Environment Setup

### 1. Create Environment Files

Create a `.env` file in the **root directory**:

```bash
GOOGLE_API_KEY=your_gemini_api_key_here
```

Create a `.env` file in the **backend directory**:

```bash
PORT=5000
GOOGLE_API_KEY=your_gemini_api_key_here
```

### 2. Get Your Gemini API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy the key and paste it in both `.env` files

---

## ▶️ Running the Application

### Start the Backend Server

```bash
cd backend
node server.js
```

The backend will start on **http://localhost:5000**

Expected output:
```
🚀 Security Scanner API running on http://localhost:5000
📊 Environment: development
🔑 Gemini API: Configured ✓
```

### Start the Frontend Development Server

Open a **new terminal** window:

```bash
cd frontend
npm run dev
```

The frontend will start on **http://localhost:3001** (or another port if 3000 is in use)

Expected output:
```
VITE v5.x.x  ready in xxx ms

➜  Local:   http://localhost:3001/
➜  Network: use --host to expose
```

---

## 🎯 Usage

### Web Interface

1. **Open your browser** and navigate to `http://localhost:3001`

2. **Choose a Scan Mode:**
   - **Quick Scan** (⚡): Fast regex-based scanning (offline)
   - **AI Scan** (🤖): Deep AI-powered analysis
   - **Hybrid Scan** (🔄): Combines both methods

3. **Upload a File:**
   - Click the upload area or drag-and-drop a `.py` file
   - Or paste code directly into the editor

4. **Review Results:**
   - View detected vulnerabilities organized by severity
   - Click on cards to expand and see detailed information
   - Export results as JSON if needed

### Command Line (Python Scanner)

You can also use the scanner directly from the command line:

```bash
# Activate virtual environment
source venv/bin/activate

# Scan a file
python scanner/scanner.py vulnerable.py

# Scan code directly
python scanner/scanner.py --code "import os; os.system('ls')"
```

---

## 📁 Project Structure

```
security-scanner/
├── backend/                    # Node.js Express API
│   ├── server.js              # Main server file
│   ├── routes/
│   │   └── scan.js            # API routes
│   ├── controllers/
│   │   └── scanController.js  # Business logic
│   └── utils/
│       ├── basicScanner.js    # Regex-based scanner
│       └── aiScanner.js       # AI scanner wrapper
│
├── frontend/                   # React TypeScript app
│   ├── src/
│   │   ├── components/        # React components
│   │   │   ├── VulnerabilityCard.tsx
│   │   │   ├── ScanModeSelector.tsx
│   │   │   ├── FileUpload.tsx
│   │   │   ├── ResultsDashboard.tsx
│   │   │   └── ...
│   │   ├── api/
│   │   │   └── api.ts         # API client
│   │   ├── types/
│   │   │   └── index.ts       # TypeScript types
│   │   └── App.tsx            # Main app component
│   └── package.json
│
├── scanner/                    # Python AI scanner
│   ├── scanner.py             # Main scanner logic
│   ├── requirements.txt       # Python dependencies
│   └── __init__.py
│
├── venv/                       # Python virtual environment
├── vulnerable.py               # Test file with vulnerabilities
├── .env                        # Environment variables (root)
└── README.md                   # This file
```

---

## 🔌 API Documentation

### Endpoints

#### Health Check
```
GET /health
Response: { "status": "ok", "geminiConfigured": true }
```

#### Basic Scan
```
POST /scan/basic
Content-Type: multipart/form-data
Body: file (Python file)
Response: { vulnerabilities: [...], scanType: "basic", ... }
```

#### AI Scan
```
POST /scan/ai
Content-Type: multipart/form-data
Body: file (Python file)
Response: { vulnerabilities: [...], scanType: "ai", ... }
```

#### Hybrid Scan
```
POST /scan/hybrid
Content-Type: multipart/form-data
Body: file (Python file)
Response: { vulnerabilities: [...], scanType: "hybrid", ... }
```

---

## 🎓 Development Journey

### Original CLI Project

This project started as a command-line Python security scanner using Google's Gemini API. The original implementation focused on:
- Connecting to Gemini API
- Building vulnerability detection prompts
- Adding severity ratings with color coding
- Scanning real Python files

### Full-Stack Evolution

The project evolved into a complete full-stack application with:
- Modern React frontend with TypeScript
- RESTful API backend with Express
- Three scanning modes for different use cases
- Professional UI/UX with Tailwind CSS
- Real-time vulnerability reporting

### Technical Challenges Solved

1. **Gemini API Integration**: Migrated from deprecated `google.generativeai` to `google-genai` package
2. **Model Compatibility**: Fixed model name from `gemini-2.0-flash-exp` to `gemini-2.5-flash`
3. **JSON Parsing**: Improved prompt engineering to ensure valid JSON responses
4. **Virtual Environment**: Configured backend to use Python venv for consistent dependencies
5. **Monorepo Structure**: Organized code into clean backend/frontend/scanner separation

---

## 🚀 Next Steps

Future enhancements planned:
- Support for multiple programming languages (JavaScript, Java, etc.)
- Database integration for scan history
- User authentication and project management
- CI/CD pipeline integration
- Scheduled automated scans
- PDF report generation
- Webhook notifications for critical findings


---

## Acknowledgments

- **NextWork** for the project inspiration and structure
- **Google Gemini AI** for powering the intelligent code analysis
- **React** and **Vite** communities for excellent tooling


