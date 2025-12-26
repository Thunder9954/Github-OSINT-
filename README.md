# **GitHub Advanced Search OSINT Tool** (Beta V3)

<div align="center">

![GitHub Advanced Search OSINT](https://img.shields.io/badge/GitHub-Advanced%20Search%20OSINT-green)
![Version](https://img.shields.io/badge/Version-Beta_V3-blue)
![Python](https://img.shields.io/badge/Python-3.8+-blue)
![Flask](https://img.shields.io/badge/Flask-3.0+-lightgrey)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success)

**The Ultimate GitHub Repository Discovery & Intelligence Platform**

*"Enterprise-grade GitHub OSINT with AI scoring, multi-search, and advanced analytics"*

[![Live Demo](https://img.shields.io/badge/Live_Demo-https://gosint.onrender.com-blueviolet)](https://gosint.onrender.com)
[![Features](https://img.shields.io/badge/Key_Features-7+-brightgreen)](#key-features)
[![Installation](https://img.shields.io/badge/Quick_Setup-5_Minutes-orange)](#installation--setup)

</div>

## 📋 **Table of Contents**

- [🎯 **What is GitHub Advanced Search OSINT?**](#what-is-github-advanced-search-osint)
- [🚀 **Live Demo**](#live-demo)
- [✨ **Key Features**](#key-features)
- [🔍 **Search Types & Capabilities**](#search-types--capabilities)
- [📊 **AI-Powered Scoring & Analytics**](#ai-powered-scoring--analytics)
- [🏗️ **Architecture & Technology Stack**](#architecture--technology-stack)
- [🔧 **Installation & Setup**](#installation--setup)
- [📖 **Quick Start Guide**](#quick-start-guide)
- [👥 **Target Audience**](#target-audience)
- [💾 **Database & Storage**](#database--storage)
- [🔐 **Security & Privacy**](#security--privacy)
- [🛠️ **API & Routes**](#api--routes)
- [🤝 **Contributing**](#contributing)
- [📄 **License**](#license)
- [👨‍💻 **Developer**](#developer)

---

## 🎯 **What is GitHub Advanced Search OSINT?**

**GitHub Advanced Search OSINT** is a production-oriented Flask web application for **advanced GitHub open-source intelligence discovery**. It transforms raw GitHub search into an intelligent, data-driven workflow with enterprise-grade features.

### **Core Value Proposition**
- **Intelligent Repository Discovery**: AI-powered scoring identifies high-quality repositories
- **7 Search Types**: Comprehensive GitHub search across all entity types
- **Advanced Analytics**: Deep insights with interactive visualizations
- **Persistent Management**: Save, bookmark, and track across sessions
- **Production Ready**: Robust architecture with security best practices

### **The Problem It Solves**
Traditional GitHub search lacks intelligence in ranking results. Users spend hours manually evaluating repositories based on stars, forks, activity, and other metrics. Our tool automates this evaluation with an advanced scoring algorithm, providing instant insights into repository quality.

---

## 🚀 **Live Demo**

### **🌐 Access the Live Application**
**Live URL:** [https://gosint.onrender.com](https://gosint.onrender.com)

### **What You Can Test in Demo:**
1. **7 Search Types** - Try all search endpoints
2. **AI Scoring** - See intelligent repository evaluation
3. **Advanced Analytics** - Explore interactive dashboard
4. **Detail Pages** - Deep dive into repositories, code, users
5. **Bookmark System** - Save repositories across sessions

### **Demo Limitations:**
- Rate limited searches
- Bookmark storage limited
- No export functionality
- Search history not persisted

---

## ✨ **Key Features**

### **1) 7 Search Types**
- **Repository Search** - Advanced qualifiers, filters, scoring
- **AI Search** - Gemini-powered intelligent search (configurable)
- **Releases Search** - Find repositories with releases
- **Code Search** - Search within code files with in-browser viewing
- **Issues/PR Search** - Issues and pull requests discovery
- **Users Search** - Profile discovery and analysis
- **Commits Search** - Commit history exploration

### **2) Results UI + Scoring**
- **Visual Score Badges** - Color-coded quality indicators (0-100)
- **Progress Bars** - Visual metric representation
- **Quick Metrics** - Stars, forks, watchers, issues at a glance
- **Bookmark Button** - One-click repository saving
- **Save Query Modal** - Save search criteria for replay

### **3) Advanced Analytics Dashboard**
Accessible from Results page via **Advanced Analytics** button:

#### **Deep Insights**
- Score distribution: min/avg/max
- Stars analysis: min/avg/max
- Forks analysis: min/avg/max
- Quality metrics breakdown

#### **Interactive Charts**
- Language distribution (pie chart)
- Quality score distribution (histogram)
- Update recency buckets (≤7d, ≤30d, ≤90d, >90d)
- Top owners activity chart

#### **Highlights**
- **Best Picks** - Top-ranked repositories
- **Top Starred** - Most popular repositories
- **Recent Updates** - Recently active projects

### **4) Detail Pages**
- **Repository Details** (`/details/repository/<owner>/<repo>`)
- **Releases Details** (`/details/releases/<owner>/<repo>`)
- **Code Details** (`/details/code/<owner>/<repo>/<path:file_path>`) with Highlight.js
- **Issue/PR Details** (`/details/issue/<owner>/<repo>/<int:issue_id>`)
- **Commit Details** (`/details/commit/<owner>/<repo>/<sha>`)
- **User Details** (`/details/user/<username>`)

### **5) Saved Queries (100% Working)**
- **Save Last Search** - One-click save with optional custom name
- **Query Replay** - Re-execute saved queries (`/query/run/<id>`)
- **Duplicate Prevention** - Auto-updates if same query exists
- **Delete with Confirmation** - Safe removal of saved queries

### **6) Bookmarks & History**
- **Persistent Bookmarks** - Save across browser sessions
- **AJAX Bookmarking** - No page reload required
- **Search History** - Track all search activities
- **User-specific Storage** - Isolated per-user databases

### **7) Feedback System**
- **Local Storage** - JSONL format in `feedback.txt`
- **Telegram Integration** - Optional delivery (when configured)
- **Form Validation** - Client and server-side validation
- **Success Feedback** - User confirmation on submission

---

## 🔍 **Search Types & Capabilities**

### **Repository Search**
```python
# Example Qualifiers
language:python stars:>100 forks:50..200 pushed:>2023-01-01
topic:machine-learning is:public archived:false size:>1000
```

### **AI Search (Gemini-powered)**
- Uses Google's Gemini API when configured
- Intelligent query understanding
- Safe fallback to multi-search when AI unavailable
- Configurable model (default: `gemini-2.5-pro`)

### **Releases Search**
- Find repositories with specific releases
- Release version filtering
- Asset download capability
- Release notes preview

### **Code Search**
```python
# Search within code files
in:file extension:py "def authenticate"
in:path test filename:test_*.py "security vulnerability"
```

### **Issues/PR Search**
```python
# Find specific issues and pull requests
is:open is:issue label:bug
author:octocat created:>2023-06-01 state:open
```

### **Users Search**
```python
# Find developers and organizations
location:"San Francisco" followers:>100
language:python repos:>10 type:user
```

### **Commits Search**
```python
# Search commit history
author-name:torvalds committer-date:>2023-01-01
merge:false hash:abc123 message:"security fix"
```

---

## 📊 **AI-Powered Scoring & Analytics**

### **Scoring Algorithm (0-100 Points)**
| Metric | Weight | Calculation | Purpose |
|--------|--------|-------------|---------|
| **⭐ Stars** | 30% | `min(stars/1000, 1) * 30` | Popularity and community trust |
| **🍴 Forks** | 20% | `min(forks/500, 1) * 20` | Community engagement and usage |
| **👁️ Watchers** | 15% | `min(watchers/300, 1) * 15` | Interest and monitoring |
| **⚠️ Issues** | 15% | `max(1 - (issues/100), 0) * 15` | Maintenance quality (fewer issues = better) |
| **📦 Size** | 10% | `max(1 - (size/50000), 0) * 10` | Codebase efficiency (smaller = better) |
| **🕒 Recency** | 10% | `10 - min(days_since_update/30, 10)` | Activity and maintenance frequency |

### **Score Interpretation**
- **90-100**: Excellent - Highly maintained, popular, active
- **70-89**: Good - Well-maintained, reliable
- **50-69**: Average - Acceptable for many use cases
- **30-49**: Poor - Consider alternatives
- **0-29**: Bad - Likely abandoned or problematic

### **Analytics Dashboard Features**
- **Real-time Charts** - Chart.js powered visualizations
- **Metric Comparisons** - Side-by-side repository analysis
- **Trend Analysis** - Update frequency and activity patterns
- **Export Ready** - Structured data for external analysis

---

## 🏗️ **Architecture & Technology Stack**


### **Technology Stack**
- **Backend Framework**: Python Flask 2.3+
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **UI Framework**: Bootstrap 5.3 with Dark Theme
- **Charts**: Chart.js for interactive visualizations
- **Database**: SQLite 3 (lightweight, file-based)
- **API Integration**: GitHub REST API v3
- **Authentication**: Flask-Session (server-side)
- **Code Highlighting**: Highlight.js
- **AI Integration**: Google Gemini API (optional)

### **Dependencies**
```txt
flask==3.0.3
requests==2.32.3
werkzeug==3.0.4
python-dotenv==1.0.1
Flask-Session==0.8.0
gunicorn==22.0.0
```

---

## 🔧 **Installation & Setup**

### **Prerequisites**
- Python 3.8 or higher
- GitHub Personal Access Token
- 100MB free disk space
- Modern web browser

### **Step 1: Clone Repository**
```bash
git clone https://github.com/Thunder9954/GitHub-Advanced-Search-OSINT.git
cd GitHub-Advanced-Search-OSINT
```

### **Step 2: Create Virtual Environment**
```bash
# Windows
python -m venv .venv
.venv\Scripts\activate

# Linux/Mac
python3 -m venv .venv
source .venv/bin/activate
```

### **Step 3: Install Dependencies**
```bash
pip install -r requirements.txt
```

### **Step 4: Configure Environment Variables**
Create a `.env` file in project root:

```env
# Required
APP_ENV=development
SECRET_KEY=replace_this_with_long_random_string

# GitHub Authentication (Required)
GITHUB_TOKEN=your_github_personal_access_token_here
# OR for token rotation:
GITHUB_TOKENS=token1,token2,token3

# Optional AI Integration
GEMINI_API_KEY=your_google_gemini_api_key
GEMINI_MODEL=gemini-2.5-pro  # Default

# Optional Telegram Feedback
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_CHAT_ID=your_telegram_chat_id
```

#### **How to Get GitHub Token:**
1. Go to GitHub → Settings → Developer settings → Personal access tokens
2. Click "Generate new token (classic)"
3. Select scope: `public_repo` (minimum required)
4. Copy token and paste in `.env` file

### **Step 5: Initialize Database**
```bash
python -c "from database import init_db; init_db()"
```

### **Step 6: Run Application**
#### **Development Mode:**
```bash
python main.py
```
Open: `http://127.0.0.1:5000/`

#### **Production Mode (with Gunicorn):**
```bash
APP_ENV=production \
SECRET_KEY="<long-random-secret>" \
GITHUB_TOKEN="<token>" \
gunicorn -w 4 -b 0.0.0.0:5000 main:app
```

---

## 📖 **Quick Start Guide**

### **1. First Time Setup**
1. Register a new account
2. Configure GitHub token in `.env`
3. Explore the search interface

### **2. Basic Search**
1. Navigate to Home page
2. Select search type (Repository, Code, Issues, etc.)
3. Enter keywords and optional qualifiers
4. Click "Search GitHub"

### **3. Using Advanced Features**
- **Save Queries**: Click "Save Query" after search
- **Bookmark Repos**: Click bookmark icon on repository cards
- **View Analytics**: Click "Advanced Analytics" on results page
- **Check Details**: Click any repository name for detailed view

### **4. Managing Your Data**
- **Bookmarks**: Access via `/bookmarks`
- **Search History**: Access via `/history`
- **Saved Queries**: Access via `/queries`
- **Account Stats**: Access via `/account/stats`

---

## 👥 **Target Audience**

| User Type | Primary Use Case | Key Benefits |
|-----------|-----------------|--------------|
| **👨‍💻 Developers** | Library discovery, tool finding | AI scoring identifies quality examples, saves hours |
| **🔐 Security Researchers** | OSINT investigations, vulnerability research | Advanced search for security auditing |
| **🚀 Startups** | Technology evaluation, rapid prototyping | Quick evaluation reduces decision time |
| **🏢 Enterprises** | Risk assessment, competitor analysis | Comprehensive metrics for business decisions |
| **👨‍🎓 Students** | Learning resources, project discovery | Quality assessment ensures reliable examples |
| **👨‍🏫 Educators** | Curriculum development, teaching materials | Find well-documented, maintained projects |
| **👥 Recruiters** | Talent sourcing, skill assessment | Identify developers with specific expertise |

---

## 💾 **Database & Storage**

### **Multi-Database Architecture**
- **Auth DB** (`auth.db`): User authentication and profiles
- **User DBs** (`user_dbs/<username>.db`): Per-user isolated storage
- **Session Storage** (`run/flask_session/`): Server-side sessions

### **Tables Schema**

#### **Auth Database (`auth.db`)**
```sql
CREATE TABLE users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT UNIQUE,
    password TEXT
);
```

#### **User Database (`user_dbs/<username>.db`)**
```sql
-- Bookmarks
CREATE TABLE bookmarks (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT,
    repo_name TEXT NOT NULL,
    repo_url TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Search History
CREATE TABLE search_history (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT,
    search_type TEXT NOT NULL,
    keyword TEXT,
    qualifiers TEXT,
    result_count INTEGER DEFAULT 0,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Saved Queries
CREATE TABLE saved_queries (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT,
    name TEXT,
    search_type TEXT NOT NULL,
    keyword TEXT,
    qualifiers TEXT,
    sort TEXT,
    order_dir TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Cached Results Snapshots
CREATE TABLE search_results (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT,
    search_type TEXT,
    keyword TEXT,
    qualifiers TEXT,
    sort TEXT,
    order_dir TEXT,
    result_count INTEGER DEFAULT 0,
    results_json TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### **File Storage**
- **Feedback**: `feedback.txt` (JSONL format)
- **Session Data**: `run/flask_session/` (encrypted)
- **Static Assets**: `static/` (CSS, JS, images)

---

## 🔐 **Security & Privacy**

### **Authentication Security**
- **Password Hashing**: Werkzeug secure password hashing
- **Session Management**: Server-side sessions with encryption
- **Secure Cookies**: `Secure`, `HttpOnly`, `SameSite=Lax` in production
- **Session Timeout**: Automatic session expiration

### **Data Protection**
- **Token Encryption**: GitHub tokens stored in environment variables only
- **No Sensitive Logging**: Tokens never logged or exposed
- **Input Validation**: All user inputs sanitized
- **SQL Injection Protection**: Parameterized queries

### **API Security**
- **Rate Limiting**: Respects GitHub API rate limits
- **Token Rotation**: Support for multiple GitHub tokens
- **Error Handling**: Safe error messages without data exposure
- **Request Validation**: All API requests validated

### **Production Security Headers**
```python
# Configured in production mode
app.config['SESSION_COOKIE_SECURE'] = True
app.config['SESSION_COOKIE_HTTPONLY'] = True
app.config['SESSION_COOKIE_SAMESITE'] = 'Lax'
```

---

## 🛠️ **API & Routes**

### **Authentication Routes**
- `GET /` - Login page
- `POST /login` - Login authentication
- `GET /register` - Registration page
- `POST /register` - User registration
- `GET /logout` - Logout and session clear

### **Main Application Routes**
- `GET /home` - Home dashboard with search interface
- `POST /search` - Execute GitHub search
- `GET /results` - View search results
- `GET /history` - Search history
- `GET /queries` - Saved queries list
- `POST /query/save` - Save current query
- `GET /query/run/<id>` - Execute saved query
- `POST /query/delete/<id>` - Delete saved query

### **Analytics & Account Routes**
- `GET /account/stats` - Account statistics page
- `GET /api/account/stats` - Account stats JSON API
- `GET /about` - About page

### **Bookmark Routes**
- `GET /bookmarks` - List all bookmarks
- `POST /bookmark` - Add bookmark (AJAX)
- `GET /bookmark/remove` - Remove bookmark

### **Detail Pages**
- `GET /details/repository/<owner>/<repo>` - Repository details
- `GET /details/releases/<owner>/<repo>` - Releases details
- `GET /download/release-asset/<owner>/<repo>/<asset_id>` - Asset download
- `GET /details/code/<owner>/<repo>/<path:file_path>` - Code view with syntax highlighting
- `GET /details/user/<username>` - User profile details
- `GET /details/issue/<owner>/<repo>/<issue_id>` - Issue/PR details
- `GET /details/commit/<owner>/<repo>/<sha>` - Commit details

### **Utility Routes**
- `GET|POST /feedback` - Feedback submission
- `GET /api/check-username` - Username availability check
- `GET /health` - Health check endpoint

---

## 🤝 **Contributing**

### **Ways to Contribute**
1. **Report Bugs**: Create issues with detailed descriptions
2. **Feature Requests**: Suggest new features or improvements
3. **Code Contributions**: Submit pull requests
4. **Documentation**: Improve docs, add examples
5. **Testing**: Test on different environments, report issues

### **Development Workflow**
```bash
# 1. Fork the repository
# 2. Clone your fork
git clone https://github.com/your-username/GitHub-Advanced-Search-OSINT.git

# 3. Create feature branch
git checkout -b feature/your-feature-name

# 4. Make changes and commit
git add .
git commit -m "Add your feature description"

# 5. Push to your fork
git push origin feature/your-feature-name

# 6. Create Pull Request
```

### **Code Standards**
- **Python**: Follow PEP 8 style guide
- **JavaScript**: Use modern ES6+ features
- **HTML/CSS**: Semantic HTML, BEM methodology for CSS
- **Documentation**: Update README and code comments
- **Testing**: Add tests for new features

### **Project Structure Conventions**
- **Modules**: Single responsibility principle
- **Templates**: Reusable components with inheritance
- **Static Files**: Organized by type (css/, js/, img/)
- **Configuration**: Environment-based settings

---

## 📄 **License**

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### **Permissions**
- ✅ Commercial use
- ✅ Modification
- ✅ Distribution
- ✅ Private use
- ✅ Sublicensing

### **Conditions**
- © Include original copyright notice
- © Include license copy in redistributions

### **Limitations**
- ❌ No liability
- ❌ No warranty

---

## 👨‍💻 **Developer**

### **Primary Developer**
**Purn Vadodariya**  
*Full Stack Developer & Cyber Security Analyst*

- **Email**: purn872008@gmail.com
- **LinkedIn**: [Purn Vadodariya](https://linkedin.com/in/purnvadodariya)
- **GitHub**: [@Thunder9954](https://github.com/Thunder9954)
- **Repository**: https://github.com/Thunder9954/GitHub-Advanced-Search-OSINT.git

### **Technical Expertise**
- **Backend**: Python, Flask, Django, FastAPI, Node.js
- **Frontend**: React, Vue.js, HTML5, CSS3, JavaScript
- **Database**: PostgreSQL, MySQL, MongoDB, SQLite
- **DevOps**: Docker, AWS, CI/CD, Git, Linux
- **Security**: OWASP, Penetration Testing, Cryptography

### **Project Philosophy**
> "Building intelligent tools that democratize access to complex data while maintaining enterprise-grade reliability and security."

### **Acknowledgments**
- GitHub for their comprehensive API
- Flask and Python communities
- Open-source contributors worldwide
- Users who provide valuable feedback

---

## 🌟 **Why Choose This Tool?**

### **Competitive Advantages**
1. **Comprehensive Search**: 7 different search types in one tool
2. **Intelligent Scoring**: AI-powered quality assessment
3. **Advanced Analytics**: Deep insights with visualizations
4. **Production Ready**: Robust architecture for real-world use
5. **User-Friendly**: Intuitive interface for all skill levels

### **Use Case Examples**
```python
# Security researcher finding exposed credentials
"password token secret in:file extension:json"

# Developer finding React components
"react component library stars:>1000 language:typescript"

# Startup evaluating backend frameworks
"fastapi django flask comparison stars:>500 forks:>100"

# Student learning machine learning
"machine learning tutorial python jupyter notebook"
```

---

<div align="center">

## **Ready to Transform Your GitHub OSINT Workflow?**

[![Live Demo](https://img.shields.io/badge/LIVE_DEMO-https://gosint.onrender.com-blue?style=for-the-badge&logo=pythonanywhere)](https://gosint.onrender.com)
[![Get Started](https://img.shields.io/badge/GET_STARTED-Install_Now-green?style=for-the-badge&logo=github)](#installation--setup)
[![Email](https://img.shields.io/badge/Contact-purn872008@gmail.com-red?style=for-the-badge&logo=gmail)](mailto:purn872008@gmail.com)

**Join the community of advanced GitHub searchers!**

*"The most comprehensive GitHub OSINT tool available"*

</div>

---

## 📞 **Support & Contact**

### **Getting Help**
- **Live Demo**: [https://gosint.onrender.com](https://gosint.onrender.com)
- **Email Support**: purn872008@gmail.com
- **GitHub Issues**: Report bugs or request features
- **Documentation**: This README and code comments

### **Business Inquiries**
For enterprise support, custom deployments, or consulting:
- **Email**: purn872008@gmail.com
- **LinkedIn**: [Purn Vadodariya](https://linkedin.com/in/purnvadodariya)

### **Stay Updated**
- Star the repository for updates
- Watch for major releases
- Check live demo for new features

---

<div align="center">

### **⭐ Star This Repository**

If you find this tool useful, please consider starring the repository to show your support!

**Try it now:** [https://gosint.onrender.com](https://gosint.onrender.com)

</div>

---

**Copyright © 2024 Purn Vadodariya. All rights reserved.**  

**Live Application:** [https://gosint.onrender.com](https://gosint.onrender.com)  
**Contact Email:** purn872008@gmail.com  
**GitHub Repository:** https://github.com/Thunder9954/GitHub-Advanced-Search-OSINT.git
