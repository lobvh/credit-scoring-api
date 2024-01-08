all: install format build 

install: requirements.txt
	pip install -r requirements.txt

format: install
	black ./main/*.py

build: format Dockerfile
	docker build -t streamlit-app:0.1 .

run: 
	docker run -it --rm -p 8501:8501 streamlit-app:0.1

