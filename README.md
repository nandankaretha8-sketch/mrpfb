# mrpfb

MRPFX FastAPI backend (WordPress-compatible API).

## Railway

Start command is defined in `railway.toml`. Railway/Railpack cannot auto-detect this app because the entrypoint is `app/main.py`, not `main.py` at the repo root.

Manual override (if needed): **Settings → Deploy → Custom Start Command**

```bash
gunicorn app.main:app -k uvicorn.workers.UvicornWorker --bind 0.0.0.0:$PORT
```

## Local development

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
uvicorn app.main:app --reload --port 8000
```

Copy environment variables from `.env.example` into Railway project settings. Do not commit `.env`.
