FROM python:3.10

WORKDIR /usr/src/app

COPY src/requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# "use gunicorn for the production server service"
CMD gunicorn -w 4 -b 0.0.0.0 'server:app'
