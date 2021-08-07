FROM python:3.6.14-alpine3.14

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY app.py .

EXPOSE 8080

CMD [ "python3", "app.py"]
