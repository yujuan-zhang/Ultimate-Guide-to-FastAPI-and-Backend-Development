# Ultimate-Guide-to-FastAPI-and-Backend-Development
This is the code repository for Ultimate Guide to FastAPI and Backend Development, published by Packt. It contains all the supporting project files necessary to work through the video course from start to finish.


## Run a small chapter example

This is a collection of independent course examples, not one complete app.
Start with `02-Getting Started/8-api-docs.py`, which exposes a shipment endpoint
and a Scalar documentation page.

```bash
git clone https://github.com/yujuan-zhang/Ultimate-Guide-to-FastAPI-and-Backend-Development.git
cd Ultimate-Guide-to-FastAPI-and-Backend-Development
python3 -m venv .venv
source .venv/bin/activate
python -m pip install fastapi uvicorn scalar-fastapi
python -m uvicorn 8-api-docs:app --app-dir "02-Getting Started" --host 127.0.0.1 --port 8000
```

Keep the server running; from another terminal:

```bash
curl http://127.0.0.1:8000/shipment
```

Input: a GET request with no body or parameters. Expected HTTP status: 200.
Expected JSON (key order and whitespace may differ):

```json
{"content":"wooden table","status":"in transit"}
```

Open http://127.0.0.1:8000/docs for Swagger UI or
http://127.0.0.1:8000/scalar for Scalar. Stop the server with Ctrl-C.
This example does not require a database or create output files.

Later chapters have additional dependencies and some are delivered as ZIP
archives. The installation above is for this first example only, not all course
chapters. The first example was verified with Python 3.14, FastAPI 0.142.2, Uvicorn
0.54.0 and scalar-fastapi 1.9.1: the documented module loads and the shipment,
Swagger, Scalar and OpenAPI routes return HTTP 200. Installation/startup time
has not been benchmarked.
