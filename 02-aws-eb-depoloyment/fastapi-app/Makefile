all: install format check-style build 

install: requirements.txt
	pip install -r requirements.txt

format: install
	black *.py

check-style: format .flake8
	flake8 *.py

build: check-style Dockerfile
	docker build -t prediction-api:0.1 .

run: 
	docker run -it --rm -p 8000:8000 prediction-api:0.1
