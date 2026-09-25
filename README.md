# Enterprise-Resource-Planning-ERP-System
Enterprise Resource Planning (ERP) System is an integrated business management solution that streamlines HR, inventory, sales, accounting, purchasing, and reporting. It centralizes data, automates workflows, improves productivity, supports decision-making, and provides real-time business insights through a secure and user-friendly platform.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Enterprise Resource Planning System</title>

<style>
/* ERP SYSTEM  */

:root {
    --primary: #2563eb;
    --primary-dark: #1d4ed8;
    --bg: #f4f7fb;
    --card: #ffffff;
    --text: #1e293b;
    --muted: #64748b;
    --border: #e2e8f0;
    --sidebar: #0f172a;
    --sidebar-text: #cbd5e1;
    --sidebar-hover: #1e293b;
    --success: #16a34a;
    --danger: #dc2626;
    --warning: #d97706;
    --info: #0284c7;
    --input: #ffffff;
    --shadow: 0 4px 18px rgba(0,0,0,0.08);
}

[data-theme="dark"] {
    --primary: #60a5fa;
    --primary-dark: #3b82f6;
    --bg: #0f172a;
    --card: #1e293b;
    --text: #f1f5f9;
    --muted: #94a3b8;
    --border: #334155;
    --sidebar: #020617;
    --sidebar-text: #cbd5e1;
    --sidebar-hover: #1e293b;
    --input: #0f172a;
    --shadow: 0 4px 20px rgba(0,0,0,0.35);
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background: var(--bg);
    color: var(--text);
    transition: background 0.25s, color 0.25s;
}

button,
input,
select {
    font-family: inherit;
}

button {
    cursor: pointer;
}

/* =========================================================
   LOGIN / REGISTER
   ========================================================= */

.auth-container {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background:
        radial-gradient(circle at top left, rgba(37,99,235,0.25), transparent 35%),
        radial-gradient(circle at bottom right, rgba(14,165,233,0.2), transparent 35%),
        var(--bg);
    padding: 20px;
}

.auth-box {
    width: 100%;
    max-width: 440px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 18px;
    padding: 35px;
    box-shadow: var(--shadow);
}

.logo {
    width: 70px;
    height: 70px;
    margin: auto;
    background: var(--primary);
    color: white;
    border-radius: 18px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 28px;
    font-weight: bold;
}

.auth-box h1 {
    text-align: center;
    margin-top: 18px;
}

.auth-subtitle {
    text-align: center;
    color: var(--muted);
    margin: 8px 0 25px;
}

.form-group {
    margin-bottom: 15px;
}

.form-group label {
    display: block;
    margin-bottom: 7px;
    font-weight: 600;
}

input,
select {
    width: 100%;
    padding: 12px 13px;
    border: 1px solid var(--border);
    border-radius: 8px;
    background: var(--input);
    color: var(--text);
    outline: none;
}

input:focus,
select:focus {
    border-color: var(--primary);
}

.btn {
    border: none;
    padding: 11px 17px;
    border-radius: 8px;
    font-weight: 600;
    transition: 0.2s;
}

.btn-primary {
    background: var(--primary);
    color: white;
}

.btn-primary:hover {
    background: var(--primary-dark);
}

.btn-success {
    background: var(--success);
    color: white;
}

.btn-danger {
    background: var(--danger);
    color: white;
}

.btn-warning {
    background: var(--warning);
    color: white;
}

.btn-secondary {
    background: #64748b;
    color: white;
}

.btn-full {
    width: 100%;
}

.auth-switch {
    text-align: center;
    margin-top: 22px;
    color: var(--muted);
}

.auth-switch button {
    background: none;
    border: none;
    color: var(--primary);
    font-weight: bold;
}

.demo-login {
    margin-top: 20px;
    padding: 12px;
    border-radius: 8px;
    background: rgba(37,99,235,0.1);
    color: var(--text);
    font-size: 13px;
}

.password-note {
    color: var(--muted);
    font-size: 12px;
    margin-top: 5px;
}

/* =========================================================
   APP
   ========================================================= */

#app {
    display: none;
    min-height: 100vh;
}

.layout {
    display: flex;
    min-height: 100vh;
}

.sidebar {
    width: 250px;
    background: var(--sidebar);
    color: var(--sidebar-text);
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
    overflow-y: auto;
    z-index: 100;
}

.brand {
    padding: 22px;
    font-size: 20px;
    font-weight: bold;
    color: white;
    border-bottom: 1px solid rgba(255,255,255,0.08);
}

.brand span {
    color: #60a5fa;
}

.user-info {
    padding: 18px;
    border-bottom: 1px solid rgba(255,255,255,0.08);
}

.user-avatar {
    width: 42px;
    height: 42px;
    background: var(--primary);
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
    float: left;
    margin-right: 12px;
}

.user-name {
    font-weight: bold;
    color: white;
}

.user-role {
    color: #94a3b8;
    font-size: 12px;
    margin-top: 4px;
}

.nav {
    padding: 12px;
}

.nav button {
    width: 100%;
    text-align: left;
    background: transparent;
    color: var(--sidebar-text);
    border: none;
    padding: 12px;
    border-radius: 8px;
    margin-bottom: 4px;
    font-size: 14px;
}

.nav button:hover,
.nav button.active {
    background: var(--sidebar-hover);
    color: white;
}

.nav-section {
    color: #64748b;
    font-size: 11px;
    text-transform: uppercase;
    margin: 20px 10px 8px;
}

.sidebar-bottom {
    padding: 12px;
    position: sticky;
    bottom: 0;
    background: var(--sidebar);
}

.main {
    margin-left: 250px;
    width: calc(100% - 250px);
}

.topbar {
    height: 70px;
    background: var(--card);
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 25px;
    position: sticky;
    top: 0;
    z-index: 50;
}

.page-title {
    font-size: 20px;
    font-weight: bold;
}

.top-actions {
    display: flex;
    gap: 10px;
    align-items: center;
}

.theme-toggle {
    border: 1px solid var(--border);
    background: var(--card);
    color: var(--text);
    border-radius: 20px;
    padding: 8px 14px;
}

.content {
    padding: 25px;
}

/* =========================================================
   CARDS
   ========================================================= */

.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 18px;
    margin-bottom: 25px;
}

.stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 20px;
    border-radius: 12px;
    box-shadow: var(--shadow);
}

.stat-card .icon {
    font-size: 25px;
}

.stat-title {
    color: var(--muted);
    font-size: 13px;
    margin-top: 12px;
}

.stat-value {
    font-size: 27px;
    font-weight: bold;
    margin-top: 5px;
}

.section {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    margin-bottom: 20px;
    box-shadow: var(--shadow);
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 18px;
    gap: 10px;
}

.section-header h2 {
    font-size: 18px;
}

/* =========================================================
   TABLE
   ========================================================= */

.table-container {
    overflow-x: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
}

th,
td {
    padding: 12px;
    text-align: left;
    border-bottom: 1px solid var(--border);
    font-size: 14px;
}

th {
    color: var(--muted);
    font-size: 12px;
    text-transform: uppercase;
}

tr:hover {
    background: rgba(148,163,184,0.05);
}

.badge {
    display: inline-block;
    padding: 5px 9px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: bold;
}

.badge-success {
    background: rgba(22,163,74,0.15);
    color: var(--success);
}

.badge-danger {
    background: rgba(220,38,38,0.15);
    color: var(--danger);
}

.badge-warning {
    background: rgba(217,119,6,0.15);
    color: var(--warning);
}

.badge-info {
    background: rgba(2,132,199,0.15);
    color: var(--info);
}

/* =========================================================
   FORMS
   ========================================================= */

.form-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
}

.form-actions {
    margin-top: 10px;
    display: flex;
    gap: 10px;
}

/* =========================================================
   REPORTS
   ========================================================= */

.progress {
    height: 9px;
    background: var(--border);
    border-radius: 10px;
    overflow: hidden;
}

.progress-bar {
    height: 100%;
    background: var(--primary);
}

.report-item {
    margin-bottom: 18px;
}

.report-label {
    display: flex;
    justify-content: space-between;
    margin-bottom: 7px;
    font-size: 13px;
}

/* =========================================================
   NOTIFICATION
   ========================================================= */

.toast {
    position: fixed;
    right: 25px;
    bottom: 25px;
    background: var(--card);
    border: 1px solid var(--border);
    box-shadow: var(--shadow);
    padding: 14px 18px;
    border-radius: 10px;
    display: none;
    z-index: 999;
}

.toast.show {
    display: block;
}

/* =========================================================
   MOBILE
   ========================================================= */

.mobile-menu {
    display: none;
}

@media(max-width: 1000px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }

    .form-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media(max-width: 700px) {
    .sidebar {
        transform: translateX(-100%);
        transition: 0.25s;
    }

    .sidebar.open {
        transform: translateX(0);
    }

    .main {
        margin-left: 0;
        width: 100%;
    }

    .mobile-menu {
        display: block;
        border: none;
        background: transparent;
        font-size: 22px;
        color: var(--text);
    }

    .cards {
        grid-template-columns: 1fr;
    }

    .form-grid {
        grid-template-columns: 1fr;
    }

    .content {
        padding: 15px;
    }

    .topbar {
        padding: 0 15px;
    }
}

/* =========================================================
   LOGIN THEME BUTTON
   ========================================================= */

.auth-theme {
    position: fixed;
    top: 20px;
    right: 20px;
}

.hidden {
    display: none !important;
}


/* =========================================================
   ENHANCED VISUALS, ANIMATIONS & COLORFUL SUBTOPICS
   ========================================================= */

:root {
    --heading-color: #7c3aed;
    --heading-secondary: #0891b2;
    --accent-pink: #db2777;
    --accent-orange: #ea580c;
    --accent-green: #059669;
}

[data-theme="dark"] {
    --heading-color: #a78bfa;
    --heading-secondary: #22d3ee;
    --accent-pink: #f472b6;
    --accent-orange: #fb923c;
    --accent-green: #34d399;
}

@keyframes fadeUpERP {
    from { opacity: 0; transform: translateY(18px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes slideInERP {
    from { opacity: 0; transform: translateX(-18px); }
    to { opacity: 1; transform: translateX(0); }
}

@keyframes floatERP {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-5px); }
}

@keyframes pulseERP {
    0%, 100% { box-shadow: 0 0 0 0 rgba(37,99,235,.15); }
    50% { box-shadow: 0 0 0 10px rgba(37,99,235,0); }
}

@keyframes shimmerERP {
    0% { background-position: -300px 0; }
    100% { background-position: 300px 0; }
}

.auth-box {
    animation: fadeUpERP .65s ease both;
}

.logo {
    animation: floatERP 3s ease-in-out infinite, pulseERP 2.5s infinite;
}

.sidebar .brand {
    background: linear-gradient(110deg, transparent 25%, rgba(255,255,255,.08) 50%, transparent 75%);
    background-size: 300px 100%;
    animation: shimmerERP 5s linear infinite;
}

.page:not(.hidden) {
    animation: fadeUpERP .4s ease both;
}

.stat-card {
    transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
}

.stat-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 30px rgba(37,99,235,.14);
    border-color: var(--primary);
}

.stat-card:nth-child(1) .icon { color: var(--primary); }
.stat-card:nth-child(2) .icon { color: var(--accent-orange); }
.stat-card:nth-child(3) .icon { color: var(--accent-green); }
.stat-card:nth-child(4) .icon { color: var(--accent-pink); }

.section {
    transition: transform .25s ease, box-shadow .25s ease;
}

.section:hover {
    box-shadow: 0 10px 28px rgba(0,0,0,.10);
}

.section-header h2 {
    background: linear-gradient(90deg, var(--heading-color), var(--heading-secondary), var(--accent-pink));
    background-size: 200% auto;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: headingGradientERP 6s linear infinite;
}

@keyframes headingGradientERP {
    to { background-position: 200% center; }
}

.nav-section:nth-of-type(1) { color: #60a5fa; }
.nav-section:nth-of-type(2) { color: #34d399; }
.nav-section:nth-of-type(3) { color: #fbbf24; }

.btn {
    position: relative;
    overflow: hidden;
    transition: transform .2s ease, box-shadow .2s ease, filter .2s ease;
}

.btn:hover {
    transform: translateY(-2px);
    filter: brightness(1.05);
    box-shadow: 0 7px 18px rgba(37,99,235,.18);
}

.btn:active {
    transform: scale(.97);
}

.nav button {
    transition: transform .2s ease, background .2s ease, color .2s ease;
}

.nav button:hover {
    transform: translateX(4px);
}

tbody tr {
    transition: background .2s ease, transform .2s ease;
}

tbody tr:hover {
    transform: translateX(2px);
}

.info-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 18px;
    margin-bottom: 20px;
}

.info-card {
    padding: 20px;
    border-radius: 14px;
    background: linear-gradient(135deg, var(--card), rgba(37,99,235,.06));
    border: 1px solid var(--border);
    transition: transform .25s ease, box-shadow .25s ease;
}

.info-card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow);
}

.info-card h3 {
    margin-bottom: 8px;
    color: var(--heading-color);
}

.info-card p {
    color: var(--muted);
    line-height: 1.6;
    font-size: 13px;
}

.feature-list {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
}

.feature-item {
    padding: 13px;
    border: 1px solid var(--border);
    border-radius: 10px;
    color: var(--text);
    background: rgba(148,163,184,.04);
}

.feature-item strong { color: var(--heading-secondary); }

.forgot-link {
    display: block;
    text-align: right;
    margin: 9px 0 2px;
    border: none;
    background: transparent;
    color: var(--accent-pink);
    font-size: 13px;
    font-weight: 700;
}

.forgot-link:hover { text-decoration: underline; }

.security-note {
    margin: 12px 0 18px;
    padding: 11px;
    border-left: 4px solid var(--warning);
    background: rgba(217,119,6,.09);
    color: var(--muted);
    font-size: 12px;
    line-height: 1.5;
    border-radius: 6px;
}

.about-hero {
    padding: 28px;
    border-radius: 16px;
    margin-bottom: 20px;
    color: white;
    background: linear-gradient(135deg, #2563eb, #7c3aed, #db2777);
    background-size: 200% 200%;
    animation: heroGradientERP 8s ease infinite;
}

@keyframes heroGradientERP {
    0%,100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.about-hero h2 {
    font-size: 27px;
    margin-bottom: 8px;
}

.about-hero p { line-height: 1.7; opacity: .94; }

.timeline {
    border-left: 3px solid var(--primary);
    padding-left: 20px;
}

.timeline-item {
    position: relative;
    margin-bottom: 18px;
    animation: slideInERP .5s ease both;
}

.timeline-item::before {
    content: "";
    position: absolute;
    left: -29px;
    top: 4px;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--accent-pink);
    border: 3px solid var(--card);
    box-shadow: 0 0 0 2px var(--accent-pink);
}

.timeline-item strong { color: var(--heading-color); }

@media(max-width: 1000px) {
    .info-grid { grid-template-columns: 1fr 1fr; }
}

@media(max-width: 700px) {
    .info-grid, .feature-list { grid-template-columns: 1fr; }
    .about-hero h2 { font-size: 22px; }
}

</style>
</head>

<body>

<!-- =======================================================
     LOGIN
     ======================================================= -->

<div id="loginScreen" class="auth-container">

    <button class="theme-toggle auth-theme" onclick="toggleTheme()" id="authThemeBtn">
        🌙 Dark
    </button>

    <div class="auth-box">

        <div class="logo">ERP</div>

        <h1>ERP System</h1>
        <p class="auth-subtitle">
            Enterprise Resource Planning
        </p>

        <div id="loginForm">

            <div class="form-group">
                <label>Username</label>
                <input id="loginUsername"
                       type="text"
                       placeholder="Enter username">
            </div>

            <div class="form-group">
                <label>Password</label>
                <input id="loginPassword"
                       type="password"
                       placeholder="Enter password">
            </div>

            <button class="forgot-link" onclick="showForgotPassword()">
                Forgot Password?
            </button>

            <button class="btn btn-primary btn-full"
                    onclick="login()">
                Login
            </button>

            <div class="demo-login">
                <strong>Demo Admin</strong><br>
                Username: admin<br>
                Password: Admin@123
            </div>

            <div class="auth-switch">
                Don't have an account?
                <button onclick="showRegister()">
                    Create an Account
                </button>
            </div>

        </div>

        <!-- FORGOT PASSWORD -->

        <div id="forgotPasswordForm" class="hidden">

            <h2 style="margin-bottom:10px;">Reset Password</h2>
            <p class="auth-subtitle" style="margin-top:0;">Reset your demo account password</p>

            <div class="security-note">
                Demo mode: this reset is performed locally in your browser.
                A real production ERP should use verified email/OTP recovery.
            </div>

            <div class="form-group">
                <label>Username</label>
                <input id="resetUsername" type="text" placeholder="Enter your username">
            </div>

            <div class="form-group">
                <label>Registered Email</label>
                <input id="resetEmail" type="email" placeholder="Enter your registered email">
            </div>

            <div class="form-group">
                <label>New Password</label>
                <input id="resetPassword" type="password" placeholder="Create new password">
            </div>

            <div class="form-group">
                <label>Confirm New Password</label>
                <input id="resetConfirm" type="password" placeholder="Confirm new password">
            </div>

            <button class="btn btn-warning btn-full" onclick="resetPassword()">
                Reset Password
            </button>

            <div class="auth-switch">
                Remembered your password?
                <button onclick="showLogin()">Back to Login</button>
            </div>

            <div class="auth-switch" style="margin-top:10px;">
                Don't have an account?
                <button onclick="showRegister()">Create Account</button>
            </div>

        </div>

        <!-- REGISTER -->

        <div id="registerForm" class="hidden">

            <h2 style="margin-bottom:18px;">Create Account</h2>

            <div class="form-group">
                <label>Full Name</label>
                <input id="regName"
                       type="text"
                       placeholder="Enter full name">
            </div>

            <div class="form-group">
                <label>Email</label>
                <input id="regEmail"
                       type="email"
                       placeholder="Enter email">
            </div>

            <div class="form-group">
                <label>Username</label>
                <input id="regUsername"
                       type="text"
                       placeholder="Create username">
            </div>

            <div class="form-group">
                <label>Password</label>
                <input id="regPassword"
                       type="password"
                       placeholder="Create password">

                <div class="password-note">
                    Minimum 6 characters.
                </div>
            </div>

            <div class="form-group">
                <label>Confirm Password</label>
                <input id="regConfirm"
                       type="password"
                       placeholder="Confirm password">
            </div>

            <button class="btn btn-success btn-full"
                    onclick="registerUser()">
                Create Account
            </button>

            <div class="auth-switch">
                Already have an account?
                <button onclick="showLogin()">
                    Back to Login
                </button>
            </div>

        </div>

    </div>
</div>


<!-- =======================================================
     MAIN APPLICATION
     ======================================================= -->

<div id="app">

<div class="layout">

    <!-- SIDEBAR -->

    <aside class="sidebar" id="sidebar">

        <div class="brand">
            <span>ERP</span> System
        </div>

        <div class="user-info">

            <div class="user-avatar" id="userAvatar">
                A
            </div>

            <div class="user-name" id="sidebarUser">
                Admin
            </div>

            <div class="user-role">
                Administrator
            </div>

            <div style="clear:both;"></div>

        </div>

        <div class="nav">

            <div class="nav-section">
                Main
            </div>

            <button class="active"
                    onclick="showPage('dashboard',this)">
                📊 Dashboard
            </button>

            <button onclick="showPage('employees',this)">
                👥 HR Management
            </button>

            <button onclick="showPage('inventory',this)">
                📦 Inventory
            </button>

            <button onclick="showPage('customers',this)">
                👤 Customers
            </button>

            <button onclick="showPage('sales',this)">
                💰 Sales
            </button>

            <div class="nav-section">
                Finance
            </div>

            <button onclick="showPage('accounting',this)">
                🧾 Accounting
            </button>

            <button onclick="showPage('procurement',this)">
                🛒 Procurement
            </button>

            <div class="nav-section">
                Administration
            </div>

            <button onclick="showPage('reports',this)">
                📈 Reports
            </button>

            <button onclick="showPage('users',this)">
                🔐 Users
            </button>

            <button onclick="showPage('audit',this)">
                📋 Audit Logs
            </button>

            <button onclick="showPage('about',this)">
                ℹ️ About ERP
            </button>

        </div>

        <div class="sidebar-bottom">

            <button class="btn btn-secondary btn-full"
                    onclick="logout()">
                🚪 Logout
            </button>

        </div>

    </aside>


    <!-- MAIN -->

    <main class="main">

        <header class="topbar">

            <div style="display:flex;align-items:center;gap:12px;">

                <button class="mobile-menu"
                        onclick="toggleSidebar()">
                    ☰
                </button>

                <div class="page-title" id="pageTitle">
                    Dashboard
                </div>

            </div>

            <div class="top-actions">

                <button class="theme-toggle"
                        onclick="toggleTheme()"
                        id="themeBtn">
                    🌙 Dark
                </button>

                <span id="topUser"></span>

            </div>

        </header>


        <div class="content">


            <!-- =================================================
                 DASHBOARD
                 ================================================= -->

            <section id="dashboardPage" class="page">

                <div class="cards">

                    <div class="stat-card">
                        <div class="icon">👥</div>
                        <div class="stat-title">
                            Employees
                        </div>
                        <div class="stat-value"
                             id="employeeCount">
                            0
                        </div>
                    </div>

                    <div class="stat-card">
                        <div class="icon">📦</div>
                        <div class="stat-title">
                            Products
                        </div>
                        <div class="stat-value"
                             id="productCount">
                            0
                        </div>
                    </div>

                    <div class="stat-card">
                        <div class="icon">👤</div>
                        <div class="stat-title">
                            Customers
                        </div>
                        <div class="stat-value"
                             id="customerCount">
                            0
                        </div>
                    </div>

                    <div class="stat-card">
                        <div class="icon">💰</div>
                        <div class="stat-title">
                            Total Sales
                        </div>
                        <div class="stat-value"
                             id="salesTotal">
                            ₹0
                        </div>
                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>ERP Overview</h2>
                        <button class="btn btn-primary"
                                onclick="refreshDashboard()">
                            Refresh
                        </button>
                    </div>

                    <p style="color:var(--muted);">
                        Welcome to the Enterprise Resource Planning
                        dashboard. Manage your organization from one
                        centralized system.
                    </p>

                </div>


                <div class="info-grid">

                    <div class="info-card">
                        <h3>⚡ Smart Operations</h3>
                        <p>Connect HR, inventory, sales, procurement and finance workflows in one centralized ERP workspace.</p>
                    </div>

                    <div class="info-card">
                        <h3>🔐 Security & Audit</h3>
                        <p>Track important actions with audit logs and keep your demo environment organized with user accounts.</p>
                    </div>

                    <div class="info-card">
                        <h3>📊 Business Insights</h3>
                        <p>Use dashboards, KPIs, sales totals and accounting summaries to understand operational performance.</p>
                    </div>

                </div>

                <div class="section">

                    <div class="section-header">
                        <h2>ERP Features</h2>
                    </div>

                    <div class="feature-list">
                        <div class="feature-item">👥 <strong>HR Management</strong> — Employee records and salary information.</div>
                        <div class="feature-item">📦 <strong>Inventory Control</strong> — Products, stock levels and availability.</div>
                        <div class="feature-item">💰 <strong>Sales Management</strong> — Customers, invoices and sales transactions.</div>
                        <div class="feature-item">🧾 <strong>Accounting</strong> — Income, expenses and balance tracking.</div>
                        <div class="feature-item">🛒 <strong>Procurement</strong> — Supplier and purchase order tracking.</div>
                        <div class="feature-item">📈 <strong>Reporting</strong> — KPIs, analytics and business summaries.</div>
                    </div>

                </div>

                <div class="section">

                    <div class="section-header">
                        <h2>Recent Sales</h2>
                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>Invoice</th>
                                    <th>Customer</th>
                                    <th>Amount</th>
                                    <th>Date</th>
                                </tr>
                            </thead>

                            <tbody id="recentSalesTable">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 HR
                 ================================================= -->

            <section id="employeesPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>Employee Management</h2>
                    </div>

                    <div class="form-grid">

                        <div class="form-group">
                            <label>Name</label>
                            <input id="empName"
                                   placeholder="Employee name">
                        </div>

                        <div class="form-group">
                            <label>Department</label>
                            <input id="empDept"
                                   placeholder="Department">
                        </div>

                        <div class="form-group">
                            <label>Position</label>
                            <input id="empPosition"
                                   placeholder="Position">
                        </div>

                        <div class="form-group">
                            <label>Email</label>
                            <input id="empEmail"
                                   placeholder="Email">
                        </div>

                        <div class="form-group">
                            <label>Salary</label>
                            <input id="empSalary"
                                   type="number"
                                   placeholder="Salary">
                        </div>

                    </div>

                    <div class="form-actions">
                        <button class="btn btn-primary"
                                onclick="addEmployee()">
                            Add Employee
                        </button>
                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>Employees</h2>

                        <input style="max-width:250px;"
                               placeholder="Search employees..."
                               onkeyup="searchTable(this,'employeesTable')">
                    </div>

                    <div class="table-container">

                        <table id="employeesTable">

                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Name</th>
                                    <th>Department</th>
                                    <th>Position</th>
                                    <th>Email</th>
                                    <th>Salary</th>
                                    <th>Action</th>
                                </tr>
                            </thead>

                            <tbody id="employeeTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 INVENTORY
                 ================================================= -->

            <section id="inventoryPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>Add Product</h2>
                    </div>

                    <div class="form-grid">

                        <div class="form-group">
                            <label>Product Name</label>
                            <input id="productName"
                                   placeholder="Product name">
                        </div>

                        <div class="form-group">
                            <label>Category</label>
                            <input id="productCategory"
                                   placeholder="Category">
                        </div>

                        <div class="form-group">
                            <label>Price</label>
                            <input id="productPrice"
                                   type="number"
                                   placeholder="Price">
                        </div>

                        <div class="form-group">
                            <label>Stock</label>
                            <input id="productStock"
                                   type="number"
                                   placeholder="Stock">
                        </div>

                    </div>

                    <div class="form-actions">

                        <button class="btn btn-primary"
                                onclick="addProduct()">
                            Add Product
                        </button>

                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>Inventory</h2>
                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Product</th>
                                    <th>Category</th>
                                    <th>Price</th>
                                    <th>Stock</th>
                                    <th>Status</th>
                                    <th>Action</th>
                                </tr>
                            </thead>

                            <tbody id="productTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 CUSTOMERS
                 ================================================= -->

            <section id="customersPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>Add Customer</h2>
                    </div>

                    <div class="form-grid">

                        <div class="form-group">
                            <label>Name</label>
                            <input id="customerName"
                                   placeholder="Customer name">
                        </div>

                        <div class="form-group">
                            <label>Email</label>
                            <input id="customerEmail"
                                   placeholder="Email">
                        </div>

                        <div class="form-group">
                            <label>Phone</label>
                            <input id="customerPhone"
                                   placeholder="Phone">
                        </div>

                        <div class="form-group">
                            <label>Company</label>
                            <input id="customerCompany"
                                   placeholder="Company">
                        </div>

                    </div>

                    <div class="form-actions">

                        <button class="btn btn-primary"
                                onclick="addCustomer()">
                            Add Customer
                        </button>

                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>Customers</h2>
                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Name</th>
                                    <th>Email</th>
                                    <th>Phone</th>
                                    <th>Company</th>
                                    <th>Action</th>
                                </tr>
                            </thead>

                            <tbody id="customerTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 SALES
                 ================================================= -->

            <section id="salesPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>Create Sale</h2>
                    </div>

                    <div class="form-grid">

                        <div class="form-group">
                            <label>Customer (Manual)</label>
                            <input id="saleCustomerManual"
                                   type="text"
                                   placeholder="Type customer name">
                        </div>

                        <div class="form-group">
                            <label>Product (Manual)</label>
                            <input id="saleProductManual"
                                   type="text"
                                   placeholder="Type product name">
                        </div>

                        <div class="form-group">
                            <label>Quantity</label>
                            <input id="saleQuantity"
                                   type="number"
                                   value="1"
                                   min="1"
                                   oninput="updateManualSaleTotal()">
                        </div>

                        <div class="form-group">
                            <label>Unit Price (₹)</label>
                            <input id="saleUnitPrice"
                                   type="number"
                                   min="0"
                                   step="0.01"
                                   placeholder="Type price"
                                   oninput="updateManualSaleTotal()">
                        </div>

                        <div class="form-group">
                            <label>Total (₹)</label>
                            <input id="saleTotal"
                                   readonly
                                   value="0">
                        </div>

                    </div>

                    <div class="form-actions">

                        <button class="btn btn-success"
                                onclick="createSale()">
                            Create Sale
                        </button>

                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>Sales History</h2>
                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>Invoice</th>
                                    <th>Customer</th>
                                    <th>Product</th>
                                    <th>Quantity</th>
                                    <th>Total</th>
                                    <th>Date</th>
                                    <th>Action</th>
                                </tr>
                            </thead>

                            <tbody id="salesTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 ACCOUNTING
                 ================================================= -->

            <section id="accountingPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>Add Transaction</h2>
                    </div>

                    <div class="form-grid">

                        <div class="form-group">
                            <label>Description</label>
                            <input id="transactionDescription"
                                   placeholder="Description">
                        </div>

                        <div class="form-group">
                            <label>Type</label>
                            <select id="transactionType">
                                <option value="Income">Income</option>
                                <option value="Expense">Expense</option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label>Amount</label>
                            <input id="transactionAmount"
                                   type="number"
                                   placeholder="Amount">
                        </div>

                    </div>

                    <div class="form-actions">

                        <button class="btn btn-primary"
                                onclick="addTransaction()">
                            Add Transaction
                        </button>

                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>Transactions</h2>
                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Description</th>
                                    <th>Type</th>
                                    <th>Amount</th>
                                    <th>Date</th>
                                    <th>Action</th>
                                </tr>
                            </thead>

                            <tbody id="transactionTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 PROCUREMENT
                 ================================================= -->

            <section id="procurementPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>Create Purchase Order</h2>
                    </div>

                    <div class="form-grid">

                        <div class="form-group">
                            <label>Supplier</label>
                            <input id="purchaseSupplier"
                                   placeholder="Supplier">
                        </div>

                        <div class="form-group">
                            <label>Product</label>
                            <input id="purchaseProduct"
                                   placeholder="Product">
                        </div>

                        <div class="form-group">
                            <label>Quantity</label>
                            <input id="purchaseQuantity"
                                   type="number"
                                   placeholder="Quantity">
                        </div>

                        <div class="form-group">
                            <label>Amount</label>
                            <input id="purchaseAmount"
                                   type="number"
                                   placeholder="Amount">
                        </div>

                    </div>

                    <div class="form-actions">

                        <button class="btn btn-primary"
                                onclick="addPurchase()">
                            Create Purchase
                        </button>

                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>Purchase Orders</h2>
                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>PO Number</th>
                                    <th>Supplier</th>
                                    <th>Product</th>
                                    <th>Quantity</th>
                                    <th>Amount</th>
                                    <th>Date</th>
                                    <th>Action</th>
                                </tr>
                            </thead>

                            <tbody id="purchaseTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 REPORTS
                 ================================================= -->

            <section id="reportsPage"
                     class="page hidden">

                <div class="section">
                    <div class="section-header">
                        <div>
                            <h2>Export Business Data</h2>
                            <p style="color:var(--muted);margin-top:6px;">Download the current ERP business data as a PDF report.</p>
                        </div>
                        <div class="form-actions" style="margin-top:0;">
                            <button class="btn btn-primary" onclick="downloadReportsPDF()">📄 Export Data as PDF</button>
                            <button class="btn btn-secondary" onclick="window.print()">🖨️ Print Report</button>
                        </div>
                    </div>
                </div>

                <div class="cards">

                    <div class="stat-card">
                        <div class="stat-title">
                            Total Income
                        </div>

                        <div class="stat-value"
                             id="reportIncome">
                            ₹0
                        </div>
                    </div>

                    <div class="stat-card">
                        <div class="stat-title">
                            Total Expenses
                        </div>

                        <div class="stat-value"
                             id="reportExpense">
                            ₹0
                        </div>
                    </div>

                    <div class="stat-card">
                        <div class="stat-title">
                            Net Balance
                        </div>

                        <div class="stat-value"
                             id="reportBalance">
                            ₹0
                        </div>
                    </div>

                    <div class="stat-card">
                        <div class="stat-title">
                            Total Orders
                        </div>

                        <div class="stat-value"
                             id="reportOrders">
                            0
                        </div>
                    </div>

                </div>


                <div class="section">

                    <div class="section-header">
                        <h2>Business Analytics</h2>
                    </div>

                    <div class="report-item">

                        <div class="report-label">
                            <span>Sales Performance</span>
                            <span id="salesPercent">0%</span>
                        </div>

                        <div class="progress">
                            <div class="progress-bar"
                                 id="salesProgress"
                                 style="width:0%;">
                            </div>
                        </div>

                    </div>


                    <div class="report-item">

                        <div class="report-label">
                            <span>Inventory Utilization</span>
                            <span id="inventoryPercent">0%</span>
                        </div>

                        <div class="progress">
                            <div class="progress-bar"
                                 id="inventoryProgress"
                                 style="width:0%;">
                            </div>
                        </div>

                    </div>


                    <div class="report-item">

                        <div class="report-label">
                            <span>Customer Growth</span>
                            <span id="customerPercent">0%</span>
                        </div>

                        <div class="progress">
                            <div class="progress-bar"
                                 id="customerProgress"
                                 style="width:0%;">
                            </div>
                        </div>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 USERS
                 ================================================= -->

            <section id="usersPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>System Users</h2>
                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>Name</th>
                                    <th>Email</th>
                                    <th>Username</th>
                                    <th>Role</th>
                                </tr>
                            </thead>

                            <tbody id="usersTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 AUDIT
                 ================================================= -->

            <section id="auditPage"
                     class="page hidden">

                <div class="section">

                    <div class="section-header">
                        <h2>Audit Logs</h2>

                        <button class="btn btn-danger"
                                onclick="clearAudit()">
                            Clear Logs
                        </button>

                    </div>

                    <div class="table-container">

                        <table>

                            <thead>
                                <tr>
                                    <th>Date</th>
                                    <th>User</th>
                                    <th>Action</th>
                                    <th>Details</th>
                                </tr>
                            </thead>

                            <tbody id="auditTableBody">
                            </tbody>

                        </table>

                    </div>

                </div>

            </section>


            <!-- =================================================
                 ABOUT ERP
                 ================================================= -->

            <section id="aboutPage" class="page hidden">

                <div class="about-hero">
                    <h2>Enterprise Resource Planning System</h2>
                    <p>A single-file ERP project designed to demonstrate how business departments can work together through a centralized digital platform.</p>
                </div>

                <div class="info-grid">
                    <div class="info-card"><h3>🎯 Purpose</h3><p>Centralize operational information and provide a simple interface for learning ERP concepts.</p></div>
                    <div class="info-card"><h3>🏢 Departments</h3><p>HR, Inventory, Customers, Sales, Accounting, Procurement, Reporting and Administration.</p></div>
                    <div class="info-card"><h3>💻 Technology</h3><p>HTML, CSS and JavaScript with browser localStorage/sessionStorage for this demonstration.</p></div>
                </div>

                <div class="section">
                    <div class="section-header"><h2>System Information</h2></div>
                    <div class="feature-list">
                        <div class="feature-item">🌓 <strong>Theme System</strong> — Dark and light modes with saved preference.</div>
                        <div class="feature-item">🔑 <strong>Account System</strong> — Login, registration and demo password recovery.</div>
                        <div class="feature-item">📱 <strong>Responsive UI</strong> — Designed for desktop, tablet and mobile screens.</div>
                        <div class="feature-item">✨ <strong>Animations</strong> — Page transitions, hover effects, gradients and motion.</div>
                        <div class="feature-item">🗂️ <strong>Local Data</strong> — Demo records persist in the browser.</div>
                        <div class="feature-item">🧪 <strong>Project Ready</strong> — Suitable as a front-end academic ERP demonstration.</div>
                    </div>
                </div>

                <div class="section">
                    <div class="section-header"><h2>ERP Workflow</h2></div>
                    <div class="timeline">
                        <div class="timeline-item"><strong>1. Create users</strong><br><span style="color:var(--muted);">Register an account or use the demo administrator.</span></div>
                        <div class="timeline-item"><strong>2. Configure operations</strong><br><span style="color:var(--muted);">Add employees, products and customers.</span></div>
                        <div class="timeline-item"><strong>3. Process business</strong><br><span style="color:var(--muted);">Create sales, purchases and accounting transactions.</span></div>
                        <div class="timeline-item"><strong>4. Analyze results</strong><br><span style="color:var(--muted);">Review dashboard KPIs, reports and audit activity.</span></div>
                    </div>
                </div>

            </section>


        </div>
    </main>

</div>
</div>


<div id="toast" class="toast"></div>


<script>

/* =========================================================
   DATABASE
   ========================================================= */

const DB_KEY = "ERP_DATABASE";
const USERS_KEY = "ERP_USERS";
const SESSION_KEY = "ERP_LOGGED_USER";
const THEME_KEY = "ERP_THEME";

let db;


/* =========================================================
   DEFAULT DATABASE
   ========================================================= */

function initializeDatabase() {

    const existing = localStorage.getItem(DB_KEY);

    if (existing) {

        db = JSON.parse(existing);

        if (!db.employees) db.employees = [];
        if (!db.products) db.products = [];
        if (!db.customers) db.customers = [];
        if (!db.sales) db.sales = [];
        if (!db.transactions) db.transactions = [];
        if (!db.purchases) db.purchases = [];
        if (!db.audit) db.audit = [];

        saveDB();

        return;
    }

    db = {

        employees: [
            {
                id: 1,
                name: "Admin Employee",
                department: "Management",
                position: "Administrator",
                email: "admin@erp.com",
                salary: 75000
            }
        ],

        products: [
            {
                id: 1,
                name: "Laptop",
                category: "Electronics",
                price: 65000,
                stock: 20
            },
            {
                id: 2,
                name: "Monitor",
                category: "Electronics",
                price: 15000,
                stock: 35
            },
            {
                id: 3,
                name: "Keyboard",
                category: "Accessories",
                price: 2500,
                stock: 50
            }
        ],

        customers: [
            {
                id: 1,
                name: "ABC Technologies",
                email: "contact@abc.com",
                phone: "9876543210",
                company: "ABC Technologies"
            }
        ],

        sales: [],

        transactions: [],

        purchases: [],

        audit: []

    };

    saveDB();
}


/* =========================================================
   USERS
   ========================================================= */

function initializeUsers() {

    let users = JSON.parse(
        localStorage.getItem(USERS_KEY) || "[]"
    );

    if (!users.some(u => u.username === "admin")) {

        users.push({
            name: "Administrator",
            email: "admin@erp.com",
            username: "admin",
            password: "Admin@123",
            role: "Administrator"
        });

    }

    localStorage.setItem(
        USERS_KEY,
        JSON.stringify(users)
    );
}


/* =========================================================
   SAVE DATABASE
   ========================================================= */

function saveDB() {

    localStorage.setItem(
        DB_KEY,
        JSON.stringify(db)
    );

}


/* =========================================================
   THEME
   ========================================================= */

function initializeTheme() {

    const savedTheme =
        localStorage.getItem(THEME_KEY) || "light";

    document.documentElement.setAttribute(
        "data-theme",
        savedTheme
    );

    updateThemeButtons();
}


function toggleTheme() {

    const current =
        document.documentElement.getAttribute("data-theme")
        || "light";

    const next =
        current === "dark" ? "light" : "dark";

    document.documentElement.setAttribute(
        "data-theme",
        next
    );

    localStorage.setItem(
        THEME_KEY,
        next
    );

    updateThemeButtons();
}


function updateThemeButtons() {

    const theme =
        document.documentElement.getAttribute("data-theme")
        || "light";

    const buttons =
        document.querySelectorAll(".theme-toggle");

    buttons.forEach(button => {

        if (theme === "dark") {
            button.innerHTML = "☀️ Light";
        } else {
            button.innerHTML = "🌙 Dark";
        }

    });

}


/* =========================================================
   AUTH
   ========================================================= */

function showRegister() {

    document.getElementById("loginForm")
        .classList.add("hidden");

    document.getElementById("forgotPasswordForm")
        .classList.add("hidden");

    document.getElementById("registerForm")
        .classList.remove("hidden");

}


function showLogin() {

    document.getElementById("registerForm")
        .classList.add("hidden");

    document.getElementById("forgotPasswordForm")
        .classList.add("hidden");

    document.getElementById("loginForm")
        .classList.remove("hidden");

}



function showForgotPassword() {

    document.getElementById("loginForm").classList.add("hidden");
    document.getElementById("registerForm").classList.add("hidden");
    document.getElementById("forgotPasswordForm").classList.remove("hidden");

}


function resetPassword() {

    const username = document.getElementById("resetUsername").value.trim();
    const email = document.getElementById("resetEmail").value.trim();
    const password = document.getElementById("resetPassword").value;
    const confirm = document.getElementById("resetConfirm").value;

    if (!username || !email || !password || !confirm) {
        showToast("Please complete all reset fields.");
        return;
    }

    if (password.length < 6) {
        showToast("Password must contain at least 6 characters.");
        return;
    }

    if (password !== confirm) {
        showToast("Passwords do not match.");
        return;
    }

    let users = JSON.parse(localStorage.getItem(USERS_KEY) || "[]");

    const userIndex = users.findIndex(u =>
        u.username.toLowerCase() === username.toLowerCase() &&
        u.email.toLowerCase() === email.toLowerCase()
    );

    if (userIndex === -1) {
        showToast("Username and registered email do not match.");
        return;
    }

    users[userIndex].password = password;

    localStorage.setItem(USERS_KEY, JSON.stringify(users));

    addAudit(username, "Password Reset", "Password changed through demo recovery");

    document.getElementById("resetUsername").value = "";
    document.getElementById("resetEmail").value = "";
    document.getElementById("resetPassword").value = "";
    document.getElementById("resetConfirm").value = "";

    showLogin();
    showToast("Password reset successfully. Please login.");

}


function registerUser() {

    const name =
        document.getElementById("regName").value.trim();

    const email =
        document.getElementById("regEmail").value.trim();

    const username =
        document.getElementById("regUsername").value.trim();

    const password =
        document.getElementById("regPassword").value;

    const confirm =
        document.getElementById("regConfirm").value;


    if (!name || !email || !username ||
        !password || !confirm) {

        showToast("Please fill all fields.");
        return;
    }


    if (password.length < 6) {

        showToast(
            "Password must contain at least 6 characters."
        );

        return;
    }


    if (password !== confirm) {

        showToast(
            "Passwords do not match."
        );

        return;
    }


    let users = JSON.parse(
        localStorage.getItem(USERS_KEY) || "[]"
    );


    if (
        users.some(
            u => u.username.toLowerCase()
            === username.toLowerCase()
        )
    ) {

        showToast("Username already exists.");
        return;

    }


    if (
        users.some(
            u => u.email.toLowerCase()
            === email.toLowerCase()
        )
    ) {

        showToast("Email already exists.");
        return;

    }


    users.push({

        name,
        email,
        username,
        password,
        role: "User"

    });


    localStorage.setItem(
        USERS_KEY,
        JSON.stringify(users)
    );


    addAudit(
        username,
        "Account Created",
        "New user registered"
    );


    document.getElementById("regName").value = "";
    document.getElementById("regEmail").value = "";
    document.getElementById("regUsername").value = "";
    document.getElementById("regPassword").value = "";
    document.getElementById("regConfirm").value = "";


    showLogin();

    showToast(
        "Account created successfully. Please login."
    );

}


function login() {

    const username =
        document.getElementById("loginUsername")
        .value.trim();

    const password =
        document.getElementById("loginPassword")
        .value;


    const users = JSON.parse(
        localStorage.getItem(USERS_KEY) || "[]"
    );


    const user = users.find(
        u =>
            u.username === username &&
            u.password === password
    );


    if (!user) {

        showToast(
            "Invalid username or password."
        );

        return;
    }


    sessionStorage.setItem(
        SESSION_KEY,
        JSON.stringify(user)
    );


    addAudit(
        user.username,
        "Login",
        "User logged into ERP system"
    );


    openApplication(user);

}


function openApplication(user) {

    document.getElementById("loginScreen")
        .style.display = "none";

    document.getElementById("app")
        .style.display = "block";


    document.getElementById("sidebarUser")
        .textContent = user.name;

    document.getElementById("topUser")
        .textContent = user.username;

    document.getElementById("userAvatar")
        .textContent =
        user.name.charAt(0).toUpperCase();


    refreshAll();

}


function logout() {

    const user =
        JSON.parse(
            sessionStorage.getItem(SESSION_KEY)
        );

    if (user) {

        addAudit(
            user.username,
            "Logout",
            "User logged out"
        );

    }


    sessionStorage.removeItem(
        SESSION_KEY
    );


    document.getElementById("app")
        .style.display = "none";

    document.getElementById("loginScreen")
        .style.display = "flex";


    showLogin();

}


/* =========================================================
   NAVIGATION
   ========================================================= */

function showPage(page, button) {

    document.querySelectorAll(".page")
        .forEach(p => p.classList.add("hidden"));


    const pageElement =
        document.getElementById(page + "Page");

    if (pageElement) {
        pageElement.classList.remove("hidden");
    }


    document.querySelectorAll(".nav button")
        .forEach(b => b.classList.remove("active"));


    if (button) {
        button.classList.add("active");
    }


    const titles = {

        dashboard: "Dashboard",
        employees: "HR Management",
        inventory: "Inventory",
        customers: "Customers",
        sales: "Sales",
        accounting: "Accounting",
        procurement: "Procurement",
        reports: "Reports",
        users: "Users",
        audit: "Audit Logs",
        about: "About ERP"

    };


    document.getElementById("pageTitle")
        .textContent = titles[page] || "ERP";


    if (window.innerWidth <= 700) {

        document.getElementById("sidebar")
            .classList.remove("open");

    }

}


function toggleSidebar() {

    document.getElementById("sidebar")
        .classList.toggle("open");

}


/* =========================================================
   EMPLOYEES
   ========================================================= */

function addEmployee() {

    const name =
        document.getElementById("empName").value.trim();

    const department =
        document.getElementById("empDept").value.trim();

    const position =
        document.getElementById("empPosition").value.trim();

    const email =
        document.getElementById("empEmail").value.trim();

    const salary =
        Number(document.getElementById("empSalary").value);


    if (!name || !department || !position) {

        showToast(
            "Please enter employee details."
        );

        return;
    }


    db.employees.push({

        id: getNextId(db.employees),

        name,
        department,
        position,
        email,
        salary

    });


    saveDB();


    addAudit(
        getCurrentUser(),
        "Employee Added",
        name
    );


    document.getElementById("empName").value = "";
    document.getElementById("empDept").value = "";
    document.getElementById("empPosition").value = "";
    document.getElementById("empEmail").value = "";
    document.getElementById("empSalary").value = "";


    renderEmployees();

    refreshDashboard();

    showToast(
        "Employee added successfully."
    );

}


function renderEmployees() {

    const tbody =
        document.getElementById("employeeTableBody");

    tbody.innerHTML = "";


    db.employees.forEach(emp => {

        tbody.innerHTML += `

        <tr>

            <td>${emp.id}</td>

            <td>${escapeHTML(emp.name)}</td>

            <td>${escapeHTML(emp.department)}</td>

            <td>${escapeHTML(emp.position)}</td>

            <td>${escapeHTML(emp.email || "-")}</td>

            <td>₹${formatNumber(emp.salary || 0)}</td>

            <td><button class="btn btn-danger btn-small" onclick="removeEmployee(${emp.id})">Remove</button></td>

        </tr>

        `;

    });

}


/* =========================================================
   PRODUCTS
   ========================================================= */

function addProduct() {

    const name =
        document.getElementById("productName")
        .value.trim();

    const category =
        document.getElementById("productCategory")
        .value.trim();

    const price =
        Number(
            document.getElementById("productPrice")
            .value
        );

    const stock =
        Number(
            document.getElementById("productStock")
            .value
        );


    if (!name) {

        showToast(
            "Please enter product name."
        );

        return;
    }


    db.products.push({

        id: getNextId(db.products),

        name,
        category,
        price,
        stock

    });


    saveDB();


    addAudit(
        getCurrentUser(),
        "Product Added",
        name
    );


    document.getElementById("productName").value = "";
    document.getElementById("productCategory").value = "";
    document.getElementById("productPrice").value = "";
    document.getElementById("productStock").value = "";


    renderProducts();

    refreshDashboard();

    showToast(
        "Product added successfully."
    );

}


function renderProducts() {

    const tbody =
        document.getElementById("productTableBody");

    tbody.innerHTML = "";


    db.products.forEach(product => {

        let status;

        if (product.stock <= 0) {

            status =
                `<span class="badge badge-danger">Out of Stock</span>`;

        } else if (product.stock <= 10) {

            status =
                `<span class="badge badge-warning">Low Stock</span>`;

        } else {

            status =
                `<span class="badge badge-success">Available</span>`;

        }


        tbody.innerHTML += `

        <tr>

            <td>${product.id}</td>

            <td>${escapeHTML(product.name)}</td>

            <td>${escapeHTML(product.category || "-")}</td>

            <td>₹${formatNumber(product.price)}</td>

            <td>${product.stock}</td>

            <td>${status}</td>

            <td><button class="btn btn-danger btn-small" onclick="removeProduct(${product.id})">Remove</button></td>

        </tr>

        `;

    });


    updateSaleProductList();

}


/* =========================================================
   CUSTOMERS
   ========================================================= */

function addCustomer() {

    const name =
        document.getElementById("customerName")
        .value.trim();

    const email =
        document.getElementById("customerEmail")
        .value.trim();

    const phone =
        document.getElementById("customerPhone")
        .value.trim();

    const company =
        document.getElementById("customerCompany")
        .value.trim();


    if (!name) {

        showToast(
            "Please enter customer name."
        );

        return;
    }


    db.customers.push({

        id: getNextId(db.customers),

        name,
        email,
        phone,
        company

    });


    saveDB();


    addAudit(
        getCurrentUser(),
        "Customer Added",
        name
    );


    document.getElementById("customerName").value = "";
    document.getElementById("customerEmail").value = "";
    document.getElementById("customerPhone").value = "";
    document.getElementById("customerCompany").value = "";


    renderCustomers();

    refreshDashboard();

    showToast(
        "Customer added successfully."
    );

}


function renderCustomers() {

    const tbody =
        document.getElementById("customerTableBody");

    tbody.innerHTML = "";


    db.customers.forEach(customer => {

        tbody.innerHTML += `

        <tr>

            <td>${customer.id}</td>

            <td>${escapeHTML(customer.name)}</td>

            <td>${escapeHTML(customer.email || "-")}</td>

            <td>${escapeHTML(customer.phone || "-")}</td>

            <td>${escapeHTML(customer.company || "-")}</td>

            <td><button class="btn btn-danger btn-small" onclick="removeCustomer(${customer.id})">Remove</button></td>

        </tr>

        `;

    });


    updateSaleCustomerList();

}


/* =========================================================
   SALES
   ========================================================= */

function updateSaleCustomerList() {

    const select =
        document.getElementById("saleCustomer");

    if (!select) return;


    select.innerHTML =
        `<option value="">Select Customer</option>`;


    db.customers.forEach(customer => {

        select.innerHTML += `

        <option value="${customer.id}">
            ${escapeHTML(customer.name)}
        </option>

        `;

    });

}


function updateSaleProductList() {

    const select =
        document.getElementById("saleProduct");

    if (!select) return;


    select.innerHTML =
        `<option value="">Select Product</option>`;


    db.products.forEach(product => {

        select.innerHTML += `

        <option value="${product.id}">
            ${escapeHTML(product.name)}
            - ₹${formatNumber(product.price)}
            (Stock: ${product.stock})
        </option>

        `;

    });

}


function updateSalePrice() {

    const productId =
        Number(
            document.getElementById("saleProduct").value
        );

    const quantity =
        Number(
            document.getElementById("saleQuantity").value
        ) || 1;


    const product =
        db.products.find(
            p => p.id === productId
        );


    const total =
        product
        ? product.price * quantity
        : 0;


    document.getElementById("saleTotal")
        .value = total;

}


function updateManualSaleTotal() {
    const quantity = Number(document.getElementById("saleQuantity")?.value) || 0;
    const price = Number(document.getElementById("saleUnitPrice")?.value) || 0;
    const totalEl = document.getElementById("saleTotal");
    if (totalEl) totalEl.value = (quantity * price).toFixed(2);
}

function createSale() {
    const customerName = document.getElementById("saleCustomerManual").value.trim();
    const productName = document.getElementById("saleProductManual").value.trim();
    const quantity = Number(document.getElementById("saleQuantity").value);
    const unitPrice = Number(document.getElementById("saleUnitPrice").value);

    if (!customerName) {
        showToast("Please type the customer name.");
        return;
    }
    if (!productName) {
        showToast("Please type the product name.");
        return;
    }
    if (!quantity || quantity <= 0) {
        showToast("Enter a valid quantity.");
        return;
    }
    if (unitPrice < 0 || !Number.isFinite(unitPrice)) {
        showToast("Enter a valid unit price.");
        return;
    }

    const matchingProduct = db.products.find(
        p => String(p.name).trim().toLowerCase() === productName.toLowerCase()
    );

    if (matchingProduct && matchingProduct.stock < quantity) {
        showToast("Insufficient stock for this inventory product.");
        return;
    }

    const total = unitPrice * quantity;
    if (matchingProduct) matchingProduct.stock -= quantity;

    const saleId = getNextId(db.sales);
    const sale = {
        id: saleId,
        invoice: "INV-" + new Date().getFullYear() + "-" + String(saleId).padStart(4, "0"),
        customerId: null,
        customerName,
        productId: matchingProduct ? matchingProduct.id : null,
        productName,
        quantity,
        unitPrice,
        total,
        date: new Date().toLocaleString()
    };

    db.sales.push(sale);
    db.transactions.push({
        id: getNextId(db.transactions),
        description: "Sale " + sale.invoice,
        type: "Income",
        amount: total,
        date: new Date().toLocaleString()
    });

    saveDB();
    addAudit(getCurrentUser(), "Sale Created", sale.invoice + " - " + customerName + " - " + productName);

    renderSales();
    renderProducts();
    renderTransactions();
    refreshDashboard();
    refreshReports();

    document.getElementById("saleCustomerManual").value = "";
    document.getElementById("saleProductManual").value = "";
    document.getElementById("saleQuantity").value = 1;
    document.getElementById("saleUnitPrice").value = "";
    document.getElementById("saleTotal").value = "0";

    showToast("Sale created successfully.");
}

function renderSales() {

    const tbody =
        document.getElementById("salesTableBody");

    if (!tbody) return;

    tbody.innerHTML = "";


    db.sales.forEach(sale => {

        tbody.innerHTML += `

        <tr>

            <td>${escapeHTML(sale.invoice)}</td>

            <td>${escapeHTML(sale.customerName)}</td>

            <td>${escapeHTML(sale.productName)}</td>

            <td>${sale.quantity}</td>

            <td>₹${formatNumber(sale.total)}</td>

            <td>${escapeHTML(sale.date)}</td>

            <td><button class="btn btn-danger btn-small" onclick="removeSale(${sale.id})">Remove</button></td>

        </tr>

        `;

    });

}


/* =========================================================
   ACCOUNTING
   ========================================================= */

function addTransaction() {

    const description =
        document.getElementById(
            "transactionDescription"
        ).value.trim();

    const type =
        document.getElementById(
            "transactionType"
        ).value;

    const amount =
        Number(
            document.getElementById(
                "transactionAmount"
            ).value
        );


    if (!description || !amount) {

        showToast(
            "Enter transaction details."
        );

        return;
    }


    db.transactions.push({

        id: getNextId(db.transactions),

        description,

        type,

        amount,

        date: new Date().toLocaleString()

    });


    saveDB();


    addAudit(
        getCurrentUser(),
        "Transaction Added",
        description
    );


    document.getElementById(
        "transactionDescription"
    ).value = "";

    document.getElementById(
        "transactionAmount"
    ).value = "";


    renderTransactions();

    refreshReports();

    showToast(
        "Transaction added successfully."
    );

}


function renderTransactions() {

    const tbody =
        document.getElementById(
            "transactionTableBody"
        );

    if (!tbody) return;

    tbody.innerHTML = "";


    db.transactions.forEach(transaction => {

        const badge =
            transaction.type === "Income"
            ? "badge-success"
            : "badge-danger";


        tbody.innerHTML += `

        <tr>

            <td>${transaction.id}</td>

            <td>${escapeHTML(transaction.description)}</td>

            <td>
                <span class="badge ${badge}">
                    ${transaction.type}
                </span>
            </td>

            <td>₹${formatNumber(transaction.amount)}</td>

            <td>${escapeHTML(transaction.date)}</td>

            <td><button class="btn btn-danger btn-small" onclick="removeTransaction(${transaction.id})">Remove</button></td>

        </tr>

        `;

    });

}


/* =========================================================
   PROCUREMENT
   ========================================================= */

function addPurchase() {

    const supplier =
        document.getElementById(
            "purchaseSupplier"
        ).value.trim();

    const product =
        document.getElementById(
            "purchaseProduct"
        ).value.trim();

    const quantity =
        Number(
            document.getElementById(
                "purchaseQuantity"
            ).value
        );

    const amount =
        Number(
            document.getElementById(
                "purchaseAmount"
            ).value
        );


    if (!supplier || !product || !quantity) {

        showToast(
            "Enter purchase details."
        );

        return;
    }


    const purchase = {

        id: getNextId(db.purchases),

        po:
            "PO-" +
            new Date().getFullYear() +
            "-" +
            String(
                getNextId(db.purchases)
            ).padStart(4,"0"),

        supplier,

        product,

        quantity,

        amount,

        date: new Date().toLocaleString()

    };


    db.purchases.push(purchase);


    if (amount) {

        db.transactions.push({

            id: getNextId(db.transactions),

            description:
                "Purchase " + purchase.po,

            type: "Expense",

            amount,

            date: new Date().toLocaleString()

        });

    }


    saveDB();


    addAudit(
        getCurrentUser(),
        "Purchase Created",
        purchase.po
    );


    document.getElementById(
        "purchaseSupplier"
    ).value = "";

    document.getElementById(
        "purchaseProduct"
    ).value = "";

    document.getElementById(
        "purchaseQuantity"
    ).value = "";

    document.getElementById(
        "purchaseAmount"
    ).value = "";


    renderPurchases();

    renderTransactions();

    refreshReports();


    showToast(
        "Purchase order created."
    );

}


function renderPurchases() {

    const tbody =
        document.getElementById(
            "purchaseTableBody"
        );

    if (!tbody) return;

    tbody.innerHTML = "";


    db.purchases.forEach(purchase => {

        tbody.innerHTML += `

        <tr>

            <td>${escapeHTML(purchase.po)}</td>

            <td>${escapeHTML(purchase.supplier)}</td>

            <td>${escapeHTML(purchase.product)}</td>

            <td>${purchase.quantity}</td>

            <td>₹${formatNumber(purchase.amount || 0)}</td>

            <td>${escapeHTML(purchase.date)}</td>

            <td><button class="btn btn-danger btn-small" onclick="removePurchase(${purchase.id})">Remove</button></td>

        </tr>

        `;

    });

}


/* =========================================================
   REPORTS
   ========================================================= */


function clearPurchaseForm() {
    ["purchaseSupplier","purchaseProduct","purchaseQuantity","purchaseAmount"].forEach(id => {
        const el = document.getElementById(id);
        if (el) el.value = "";
    });
    showToast("Purchase order form cleared.");
}

function removeEmployee(id) {
    const item = db.employees.find(x => x.id === id);
    if (!item || !confirm("Remove this employee?")) return;
    db.employees = db.employees.filter(x => x.id !== id);
    saveDB();
    addAudit(getCurrentUser(), "Employee Removed", item.name);
    renderEmployees(); refreshDashboard();
    showToast("Employee removed.");
}

function removeProduct(id) {
    const item = db.products.find(x => x.id === id);
    if (!item || !confirm("Remove this product?")) return;
    db.products = db.products.filter(x => x.id !== id);
    saveDB();
    addAudit(getCurrentUser(), "Product Removed", item.name);
    renderProducts(); refreshDashboard(); updateSaleProductList();
    showToast("Product removed.");
}

function removeCustomer(id) {
    const item = db.customers.find(x => x.id === id);
    if (!item || !confirm("Remove this customer? Existing sales will be kept.")) return;
    db.customers = db.customers.filter(x => x.id !== id);
    saveDB();
    addAudit(getCurrentUser(), "Customer Removed", item.name);
    renderCustomers(); refreshDashboard();
    showToast("Customer removed.");
}

function removeSale(id) {
    const item = db.sales.find(x => x.id === id);
    if (!item || !confirm("Remove this sale and restore its stock?")) return;
    const product = db.products.find(x => x.id === item.productId);
    if (product) product.stock += Number(item.quantity || 0);
    db.sales = db.sales.filter(x => x.id !== id);
    db.transactions = db.transactions.filter(t => t.description !== "Sale " + item.invoice);
    saveDB();
    addAudit(getCurrentUser(), "Sale Removed", item.invoice);
    renderSales(); renderProducts(); renderTransactions(); refreshDashboard(); refreshReports();
    showToast("Sale removed and stock restored.");
}

function removeTransaction(id) {
    const item = db.transactions.find(x => x.id === id);
    if (!item || !confirm("Remove this accounting transaction?")) return;
    db.transactions = db.transactions.filter(x => x.id !== id);
    saveDB();
    addAudit(getCurrentUser(), "Transaction Removed", item.description);
    renderTransactions(); refreshReports(); refreshDashboard();
    showToast("Transaction removed.");
}

function removePurchase(id) {
    const item = db.purchases.find(x => x.id === id);
    if (!item || !confirm("Remove this purchase order?")) return;
    db.purchases = db.purchases.filter(x => x.id !== id);
    db.transactions = db.transactions.filter(t => t.description !== "Purchase " + item.po);
    saveDB();
    addAudit(getCurrentUser(), "Purchase Removed", item.po);
    renderPurchases(); renderTransactions(); refreshReports(); refreshDashboard();
    showToast("Purchase order removed.");
}

function pdfEscape(value) {
    return String(value).replace(/\\/g, "\\\\").replace(/\(/g, "\\(").replace(/\)/g, "\\)").replace(/[^\x20-\x7E]/g, "?");
}

function downloadReportsPDF() {
    const income = db.transactions.filter(t => t.type === "Income").reduce((a,t) => a + Number(t.amount || 0), 0);
    const expense = db.transactions.filter(t => t.type !== "Income").reduce((a,t) => a + Number(t.amount || 0), 0);
    const balance = income - expense;
    const lines = [
        "ERP SYSTEM - BUSINESS REPORT",
        "Generated: " + new Date().toLocaleString(),
        "",
        "SUMMARY",
        "Employees: " + db.employees.length,
        "Customers: " + db.customers.length,
        "Products: " + db.products.length,
        "Sales Orders: " + db.sales.length,
        "Purchase Orders: " + db.purchases.length,
        "Transactions: " + db.transactions.length,
        "",
        "FINANCIAL SUMMARY",
        "Income: INR " + income.toFixed(2),
        "Expenses: INR " + expense.toFixed(2),
        "Balance: INR " + balance.toFixed(2),
        "",
        "RECENT SALES"
    ];
    db.sales.slice(-12).reverse().forEach(s => lines.push((s.invoice || "Sale") + " | " + (s.customerName || "") + " | INR " + Number(s.total || 0).toFixed(2)));
    lines.push("", "PURCHASE ORDERS");
    db.purchases.slice(-12).reverse().forEach(p => lines.push((p.po || "PO") + " | " + (p.supplier || "") + " | INR " + Number(p.amount || 0).toFixed(2)));

    const perPage = 42, pages = [];
    for (let i = 0; i < lines.length; i += perPage) pages.push(lines.slice(i, i + perPage));
    if (!pages.length) pages.push(["ERP SYSTEM - BUSINESS REPORT"]);

    const objects = [];
    objects[1] = "<< /Type /Catalog /Pages 2 0 R >>";
    const pageNums = [];
    const firstPageObj = 4;
    pages.forEach((page, pi) => {
        const pageObj = firstPageObj + pi * 2;
        const contentObj = pageObj + 1;
        pageNums.push(pageObj + " 0 R");
        let content = "BT /F1 10 Tf 40 760 Td 14 TL\n";
        page.forEach((line, li) => {
            if (li === 0) content += "/F1 14 Tf (" + pdfEscape(line) + ") Tj /F1 10 Tf T*\n";
            else content += "(" + pdfEscape(line) + ") Tj T*\n";
        });
        content += "ET";
        objects[pageObj] = "<< /Type /Page /Parent 2 0 R /MediaBox [0 0 595 842] /Resources << /Font << /F1 3 0 R >> >> /Contents " + contentObj + " 0 R >>";
        objects[contentObj] = "<< /Length " + content.length + " >>\nstream\n" + content + "\nendstream";
    });
    objects[2] = "<< /Type /Pages /Kids [" + pageNums.join(" ") + "] /Count " + pages.length + " >>";
    objects[3] = "<< /Type /Font /Subtype /Type1 /BaseFont /Helvetica >>";

    let pdf = "%PDF-1.4\n%\xE2\xE3\xCF\xD3\n";
    const offsets = [0];
    for (let i = 1; i < objects.length; i++) {
        offsets[i] = pdf.length;
        pdf += i + " 0 obj\n" + objects[i] + "\nendobj\n";
    }
    const xref = pdf.length;
    pdf += "xref\n0 " + objects.length + "\n0000000000 65535 f \n";
    for (let i = 1; i < objects.length; i++) pdf += String(offsets[i]).padStart(10, "0") + " 00000 n \n";
    pdf += "trailer\n<< /Size " + objects.length + " /Root 1 0 R >>\nstartxref\n" + xref + "\n%%EOF";
    const blob = new Blob([new Uint8Array([...pdf].map(c => c.charCodeAt(0)))], {type: "application/pdf"});
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a"); a.href = url; a.download = "ERP_Business_Report.pdf"; a.click();
    setTimeout(() => URL.revokeObjectURL(url), 1000);
    addAudit(getCurrentUser(), "Report Downloaded", "ERP Business Report PDF");
    showToast("PDF report downloaded.");
}

function refreshReports() {

    let income = 0;
    let expense = 0;


    db.transactions.forEach(t => {

        if (t.type === "Income") {

            income += Number(t.amount);

        } else {

            expense += Number(t.amount);

        }

    });


    const balance =
        income - expense;


    document.getElementById(
        "reportIncome"
    ).textContent =
        "₹" + formatNumber(income);


    document.getElementById(
        "reportExpense"
    ).textContent =
        "₹" + formatNumber(expense);


    document.getElementById(
        "reportBalance"
    ).textContent =
        "₹" + formatNumber(balance);


    document.getElementById(
        "reportOrders"
    ).textContent =
        db.sales.length;


    const salesPercent =
        Math.min(
            100,
            db.sales.length * 10
        );


    const inventoryTotal =
        db.products.reduce(
            (sum,p) =>
                sum + Number(p.stock || 0),
            0
        );


    const inventoryPercent =
        Math.min(
            100,
            inventoryTotal
                ? Math.round(
                    db.products.length /
                    Math.max(inventoryTotal,1)
                    * 100
                )
                : 0
        );


    const customerPercent =
        Math.min(
            100,
            db.customers.length * 10
        );


    document.getElementById(
        "salesPercent"
    ).textContent =
        salesPercent + "%";


    document.getElementById(
        "salesProgress"
    ).style.width =
        salesPercent + "%";


    document.getElementById(
        "inventoryPercent"
    ).textContent =
        inventoryPercent + "%";


    document.getElementById(
        "inventoryProgress"
    ).style.width =
        inventoryPercent + "%";


    document.getElementById(
        "customerPercent"
    ).textContent =
        customerPercent + "%";


    document.getElementById(
        "customerProgress"
    ).style.width =
        customerPercent + "%";

}


/* =========================================================
   USERS
   ========================================================= */

function renderUsers() {

    const tbody =
        document.getElementById(
            "usersTableBody"
        );

    if (!tbody) return;


    const users = JSON.parse(
        localStorage.getItem(USERS_KEY) || "[]"
    );


    tbody.innerHTML = "";


    users.forEach(user => {

        tbody.innerHTML += `

        <tr>

            <td>${escapeHTML(user.name)}</td>

            <td>${escapeHTML(user.email)}</td>

            <td>${escapeHTML(user.username)}</td>

            <td>
                <span class="badge badge-info">
                    ${escapeHTML(user.role)}
                </span>
            </td>

        </tr>

        `;

    });

}


/* =========================================================
   AUDIT LOGS
   ========================================================= */

function addAudit(user, action, details) {

    if (!db) return;


    db.audit.unshift({

        date: new Date().toLocaleString(),

        user: user || "System",

        action,

        details

    });


    if (db.audit.length > 500) {

        db.audit =
            db.audit.slice(0,500);

    }


    saveDB();

}


function renderAudit() {

    const tbody =
        document.getElementById(
            "auditTableBody"
        );

    if (!tbody) return;


    tbody.innerHTML = "";


    db.audit.forEach(log => {

        tbody.innerHTML += `

        <tr>

            <td>${escapeHTML(log.date)}</td>

            <td>${escapeHTML(log.user)}</td>

            <td>${escapeHTML(log.action)}</td>

            <td>${escapeHTML(log.details)}</td>

        </tr>

        `;

    });

}


function clearAudit() {

    if (
        !confirm(
            "Are you sure you want to clear all audit logs?"
        )
    ) {
        return;
    }


    db.audit = [];

    saveDB();

    renderAudit();

    showToast(
        "Audit logs cleared."
    );

}


/* =========================================================
   DASHBOARD
   ========================================================= */

function refreshDashboard() {

    document.getElementById(
        "employeeCount"
    ).textContent =
        db.employees.length;


    document.getElementById(
        "productCount"
    ).textContent =
        db.products.length;


    document.getElementById(
        "customerCount"
    ).textContent =
        db.customers.length;


    const totalSales =
        db.sales.reduce(
            (sum,sale) =>
                sum + Number(sale.total || 0),
            0
        );


    document.getElementById(
        "salesTotal"
    ).textContent =
        "₹" + formatNumber(totalSales);


    const tbody =
        document.getElementById(
            "recentSalesTable"
        );


    tbody.innerHTML = "";


    db.sales.slice(0,8).forEach(sale => {

        tbody.innerHTML += `

        <tr>

            <td>${escapeHTML(sale.invoice)}</td>

            <td>${escapeHTML(sale.customerName)}</td>

            <td>₹${formatNumber(sale.total)}</td>

            <td>${escapeHTML(sale.date)}</td>

        </tr>

        `;

    });

}


/* =========================================================
   SEARCH
   ========================================================= */

function searchTable(input, tableId) {

    const filter =
        input.value.toLowerCase();

    const table =
        document.getElementById(tableId);

    if (!table) return;


    const rows =
        table.getElementsByTagName("tr");


    for (
        let i = 1;
        i < rows.length;
        i++
    ) {

        const text =
            rows[i].textContent.toLowerCase();


        rows[i].style.display =
            text.includes(filter)
            ? ""
            : "none";

    }

}


/* =========================================================
   UTILITIES
   ========================================================= */

function getNextId(array) {

    if (!array.length) {
        return 1;
    }

    return (
        Math.max(
            ...array.map(
                item => Number(item.id) || 0
            )
        ) + 1
    );

}


function formatNumber(number) {

    return Number(number || 0)
        .toLocaleString("en-IN");

}


function escapeHTML(value) {

    return String(value ?? "")
        .replace(/&/g,"&amp;")
        .replace(/</g,"&lt;")
        .replace(/>/g,"&gt;")
        .replace(/"/g,"&quot;")
        .replace(/'/g,"&#039;");

}


function getCurrentUser() {

    const user =
        JSON.parse(
            sessionStorage.getItem(
                SESSION_KEY
            ) || "null"
        );


    return user
        ? user.username
        : "System";

}


function showToast(message) {

    const toast =
        document.getElementById("toast");

    toast.textContent = message;

    toast.classList.add("show");


    setTimeout(
        () => toast.classList.remove("show"),
        2500
    );

}


/* =========================================================
   REFRESH EVERYTHING
   ========================================================= */

function refreshAll() {

    initializeDatabase();

    renderEmployees();

    renderProducts();

    renderCustomers();

    renderSales();

    renderTransactions();

    renderPurchases();

    renderUsers();

    renderAudit();

    refreshDashboard();

    refreshReports();

}


/* =========================================================
   ENTER KEY LOGIN
   ========================================================= */

document.addEventListener(
    "keydown",
    function(event) {

        if (
            event.key === "Enter" &&
            document.getElementById(
                "loginScreen"
            ).style.display !== "none"
        ) {

            const loginForm =
                document.getElementById(
                    "loginForm"
                );

            if (
                !loginForm.classList.contains(
                    "hidden"
                )
            ) {

                login();

            }

        }

    }
);


/* =========================================================
   INITIALIZE
   ========================================================= */

initializeTheme();

initializeDatabase();

initializeUsers();


const existingSession =
    JSON.parse(
        sessionStorage.getItem(
            SESSION_KEY
        ) || "null"
    );


if (existingSession) {

    openApplication(
        existingSession
    );

}

</script>

</body>
</html>s
