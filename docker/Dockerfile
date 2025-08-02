FROM python:3.11-slim
RUN apt-get update && \
    apt-get install -y python3-poetry && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY pyproject.toml config/gunicorn_conf.py src /app/
RUN poetry install --no-root
EXPOSE 5000
CMD ["poetry", "run", "gunicorn", "-c", "gunicorn_conf.py", "my_app.details_app:app"]