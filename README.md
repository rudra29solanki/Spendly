# Spendly

An expense tracker app.

---

## 1. What libraries were installed in this project yet?

Here are the libraries declared in `requirements.txt`:

| Library | Version | Purpose |
|---|---|---|
| `flask` | 3.1.3 | Web framework — routing, request handling, templating |
| `werkzeug` | 3.1.6 | WSGI toolkit (Flask's underlying HTTP utilities, password hashing, etc.) |
| `pytest` | 8.3.5 | Test runner |
| `pytest-flask` | 1.3.0 | Pytest plugin with Flask-specific fixtures (`client`, `live_server`) |

That's it for declared dependencies. If you want to check what's actually installed inside `venv/`, or look for a `Pipfile.lock` / `poetry.lock` for transitive deps, that can be done separately.

---

## 2. What does this project do?

**Spendly** is a personal-finance / expense-tracking web app built with Flask. From what's already in the repo:

### What's working now
- A Flask app (`app.py`) with three live routes: landing page, register, login.
- A styled landing page (`templates/landing.html`) — hero, three feature cards, CTA, plus a mock "monthly spending" card.
- Login and register pages (templates exist).
- Static CSS/JS in `static/`.

### What it's intended to do (from the route stubs)
- **User accounts:** register, login, logout, profile.
- **Expenses:** add, edit, delete individual expenses, each with a category, amount, date, description.
- **Filtering by time period** (last week, last month, custom range).
- **Category breakdowns and monthly summaries** (shown in the mock card and "Understand your patterns" feature).

### Stack at a glance
- **Backend:** Flask + SQLite (likely, given the `database/` folder).
- **Frontend:** Jinja2 templates + plain CSS/JS.
- **Testing:** pytest + pytest-flask.

### Status
This is clearly a **step-by-step tutorial / learning project** — `database/db.py` is empty with comments saying "Students will write this file in Step 1," and most routes are placeholders that return strings like `"Add expense — coming in Step 7"`. The skeleton is in place but the actual expense-tracking logic hasn't been implemented yet — the project is in its early stages.

---

## 3. What tech stack does this project use?

### Backend
- **Python 3** + **Flask 3.1.3** — web framework, routing, templating
- **Werkzeug 3.1.6** — WSGI layer, password hashing (`generate_password_hash`, `check_password_hash`)
- **SQLite** — database (inferred from `database/db.py` scaffolding and the `expense_tracker.db` entry in `.gitignore`; no SQLAlchemy, raw `sqlite3`)

### Frontend
- **Jinja2** — server-side templating (bundled with Flask)
- **HTML5** + **plain CSS** (`static/css/style.css`) + **vanilla JavaScript** (`static/js/main.js`) — no React/Vue/framework, no Tailwind/Bootstrap
- Currency symbol ₹ in the mock UI suggests an **Indian-rupee** target audience

### Tooling
- **pytest 8.3.5** + **pytest-flask 1.3.0** — testing
- **venv** — Python virtual environment (in `.gitignore`)
- **Git** — version control

### Intentionally not used
- No ORM (raw SQL via `sqlite3`)
- No CSS framework
- No JS framework / no build step / no Node
- No Docker, no CI config, no env-management beyond a single `.env` placeholder
- No API layer — server-rendered pages only

It's a deliberately minimal, beginner-friendly stack — typical of a tutorial-style project where the focus is learning Flask + SQL fundamentals, not a production deployment setup.
