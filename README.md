# Web Test Driver

Sample project to run load testing of a website using the Locus project. https://docs.locust.io/en/stable/index.html


# Dev Environment Setup

Create a local python dev environment

```bash
conda create -n webtestdriver python=3.8

activate webtestdriver

python -m pip install requirements.txt
python -m pip install requirements-dev.txt
```

# Load Testing a Website

Run from command line. 

```bash
locust -f main.py
```

Try to run headlest. This doesn't work yet.

```bash
locust -f main.py -H <hostname> -u 10000 -r 10 -t 300 --headless
```

# Run Docker 

Build docker image

```bash
docker build --pull --rm -f "dockerfile.dev" -t webtestdriver:latest "."
```

Run Docker image. 

```bash
docker run --rm -it  webtestdriver:latest
```

Run Docker image and map the serving port to a different port
```bash
docker run --rm -it -p 8098:8089  webtestdriver:latest
```

# References

- Locus Project https://docs.locust.io/en/stable/index.html