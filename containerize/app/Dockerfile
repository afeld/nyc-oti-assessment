# "Docker best practices including … image size"
FROM python:3.10-alpine

WORKDIR /usr/src/app

# "Docker best practices including security": don't run as root
# https://wiki.alpinelinux.org/wiki/Setting_up_a_new_user#Creating_a_new_user
ARG USER=containerizer
RUN adduser -D ${USER}
USER ${USER}

# add Python packages to PATH
ENV PATH="/home/${USER}/.local/bin:${PATH}"
COPY src/requirements.txt ./
# "Docker best practices including … image size": since a `pip install` only happens once per build, disable the cache
RUN pip install --no-cache-dir --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# "use gunicorn for the production server service"
CMD gunicorn --bind 0.0.0.0 'server:app'
