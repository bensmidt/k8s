FROM python:3.10-slim

RUN apt-get update
RUN apt-get install -y gcc python3-dev

WORKDIR /app

COPY requirements.txt /app/

RUN pip install --upgrade pip 
RUN pip install -r requirements.txt

COPY . /app/

CMD gunicorn --workers 10 --bind 0.0.0.0:5000 --log-level DEBUG main:app

