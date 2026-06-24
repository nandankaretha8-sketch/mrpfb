# mrpfb

MRPFX FastAPI backend (WordPress-compatible API).

## Railway start command

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
