# "Docker best practices including … image size"
FROM python:3.10-alpine

WORKDIR /usr/src/app

COPY src/requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# "use gunicorn for the production server service"
CMD gunicorn -w 4 -b 0.0.0.0 'server:app'
