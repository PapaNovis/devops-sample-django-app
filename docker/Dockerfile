FROM python:3.8.18-slim-bullseye
WORKDIR /app

ARG UID=1000
ARG GID=1000
ARG USER=def
ARG GROUP=def

RUN addgroup --system --gid ${GID} ${GROUP} && \
    adduser --system --no-create-home $USER --uid ${UID} --ingroup ${GROUP}

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

COPY --chmod=755 docker/entrypoint.sh /entrypoint.sh

ENV APP_PORT=8000
ENV APP_WORKERS=3
ENV GUNICORN_CMD_ARGS="--bind=0.0.0.0:${APP_PORT} --workers ${APP_WORKERS}"
USER ${UID}

ENTRYPOINT [ "/entrypoint.sh" ]
CMD ["gunicorn", "parrotsite.wsgi:application"]