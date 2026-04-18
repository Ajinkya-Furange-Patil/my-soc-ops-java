# Copilot Instructions for Soc Ops

**Soc Ops** is a Social Bingo game for in-person mixers built with FastAPI, Jinja2 templates, HTMX, and Python.

## ✅ Development Checklist (Required Before Commit)

```bash
ruff check .              # ✅ Lint (no errors)
python -m pytest          # ✅ Tests pass
uvicorn app.main:app --reload --port 8000  # ✅ Build runs
```

## Quick Start

```bash
uvicorn app.main:app --reload --port 8000  # Dev server (http://localhost:8000)
python -m pytest                            # Run tests
ruff check .                                # Lint code
```

## Project Structure

```
app/main.py              # FastAPI routes & HTMX endpoints
app/models.py            # Pydantic models (GameState, BingoSquare)
app/game_logic.py        # Board generation & bingo detection
app/game_service.py      # GameSession management (cookie-based state)
app/data.py              # Question bank
app/templates/           # Jinja2 templates + HTMX components
app/static/css/          # Custom utility classes (Tailwind-like)
tests/                   # pytest tests (API & game logic)
```

## Architecture

- **Backend**: FastAPI (async) + Jinja2 templates + HTMX (no JS framework)
- **State**: `GameSession` objects persisted via signed cookies (`itsdangerous`)
- **Session ID**: UUID stored in `request.session["session_id"]`
- **Frontend**: Custom CSS utility classes (no external CSS framework)
- **Game Logic**: `Board.generate()` creates 5×5 board; `Board.check_win()` detects 5-in-a-row

## Key Patterns

**Routes**: Return `templates.TemplateResponse(request, "path.html", {"session": session})`

**Game Session**: Use `session = _get_game_session(request)` to get/create session

**HTMX**: Trigger updates with `hx-post="/endpoint" hx-swap="outerHTML"`

**CSS**: Compose utility classes (e.g., `class="flex p-4 gap-2 bg-accent"`)

## Code Style & Standards

- **Python 3.13+** with type hints (required on all functions)
- **Linter**: ruff (E, F, I, N, W rules; line length: 88)
- **Testing**: pytest with `TestClient` from `fastapi.testclient`
- **Naming**: snake_case for functions, PascalCase for classes

## Guides & References

- **CSS Utilities**: [.github/instructions/css-utilities.instructions.md](.github/instructions/css-utilities.instructions.md)
- **Frontend Design**: [.github/instructions/frontend-design.instructions.md](.github/instructions/frontend-design.instructions.md)
- **Workshop**: [workshop/](../workshop/) (full tutorial with 5 parts)
- **FastAPI Docs**: https://fastapi.tiangolo.com/
- **HTMX**: https://htmx.org/
