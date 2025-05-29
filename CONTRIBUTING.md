# Contributing

## How to run Dockerfile locally

````
docker run -dp 5005:5000 -w /app -v "$(pwd):/app" image-name sh -c "flask run"
````