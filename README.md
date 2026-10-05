# Ultimate-Guide-to-FastAPI-and-Backend-Development

## What it does

This is the code repository for *Ultimate Guide to FastAPI and Backend
Development*, published by Packt. It contains examples that follow the video
course, from a small HTTP endpoint to backend features such as data validation,
CRUD operations, databases, authentication, background tasks and API testing.

The chapter folders are separate teaching examples, not one application that
starts every service at once. Work through them in course order and use the
entry point for the chapter you are studying. Later examples add components
such as PostgreSQL, Celery and a frontend; some are supplied as ZIP archives.

The first working example below is deliberately small: start the shipment
API, send a GET request, inspect its JSON response, and open the generated
Swagger or Scalar documentation. It needs no database. The root requirements
cover this first lesson, while later chapters need their own dependencies.
The shipment example was checked with the versions listed below. Later
chapters have their own setup instructions.

## Input

Input: a GET request with no body or parameters. Expected HTTP status: 200.
Expected JSON (key order and whitespace may differ):

## Output

HTTP 200 with this JSON:

```json
{"content":"wooden table","status":"in transit"}
```

Swagger is at `http://127.0.0.1:8000/docs`; Scalar is at `http://127.0.0.1:8000/scalar`. This lesson does not save files.

## Try it

### Run a small chapter example

This is a collection of independent course examples, not one complete app.
Start with `02-Getting Started/8-api-docs.py`, which exposes a shipment endpoint
and a Scalar documentation page. Use an installed Python 3.14 interpreter to
match the recorded example environment.

```bash
git clone https://github.com/yujuan-zhang/Ultimate-Guide-to-FastAPI-and-Backend-Development.git
cd Ultimate-Guide-to-FastAPI-and-Backend-Development
python3.14 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m uvicorn 8-api-docs:app --app-dir "02-Getting Started" --host 127.0.0.1 --port 8000
```

Keep the server running; from another terminal:

```bash
curl http://127.0.0.1:8000/shipment
```

```json
{"content":"wooden table","status":"in transit"}
```

Open http://127.0.0.1:8000/docs for Swagger UI or
http://127.0.0.1:8000/scalar for Scalar. Stop the server with Ctrl-C.
This example does not require a database or create output files.

Later chapters have additional dependencies and some are delivered as ZIP
archives. The installation above is for this first example only, not all course
chapters. The root `requirements.txt` pins those three direct dependencies;
transitive dependencies are not fully locked and a fresh installation was not
repeated during this documentation pass. The first example was verified with Python 3.14, FastAPI 0.142.2, Uvicorn
0.54.0 and scalar-fastapi 1.9.1: the documented module loads and the shipment,
Swagger, Scalar and OpenAPI routes return HTTP 200. Installation/startup time
has not been benchmarked.

