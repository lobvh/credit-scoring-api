FROM python:3.12-slim

RUN pip install pipenv

WORKDIR /app

COPY ["Pipfile", "Pipfile.lock", "./"]

#Install it as part of the system not venv inside of system
RUN pipenv install --system --deploy

COPY ./model ./model

COPY ["main.py", "./"]

EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]

