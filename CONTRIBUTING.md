## Contributing

Some ideas:

### Run Docker Locally

If you want to run this API locally using Docker:

```
FROM python:3.10
EXPOSE 5000
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["flask", "run", "--host", "0.0.0.0"]
```

Then you can create a Docker image with following command:

```
docker build -t rest-api-flask-python .
```

And run it:

```
docker run -dp 5005:5000 -w /app -v "$(pwd):/app" rest-api-flask-python
```

Another alternative:

```
docker run -dp 5005:5000 -w /app -v "$(pwd):/app" rest-api-flask-python sh -c "flask run"
```
