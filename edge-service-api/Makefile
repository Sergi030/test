FLASK_APP=app

run: env
	@. .venv/bin/activate && python main.py 
env:
	@test -d .venv || python3 -m virtualenv .venv || virtualenv .venv
	@. .venv/bin/activate && pip install -Ur requirements/requirements.txt > /dev/null

dev-env: env
	@test -d .venv || python3 -m virtualenv .venv || virtualenv .venv
	@. .venv/bin/activate && pip install -Ur requirements/requirements-dev.txt > /dev/null

check: dev-env
	@. .venv/bin/activate && python3 -m flake8

clean:
	rm -rf venv
	rm -rf __pycache__
	find -iname "*.pyc" -delete
