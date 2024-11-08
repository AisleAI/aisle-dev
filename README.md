# Aisle Development Environment
forked from [pamelafox/pgvector-playground](https://github.com/pamelafox/pgvector-playground)

# Dev Container Python + PostgreSQL + pgvector

This is a PostgreSQL dev container for use with VS Code Remote Containers or GitHub Codespaces.
The devcontainer.json uses a docker-compose.yaml to set up a local PostgreSQL server inside the container.

# Aisle Installation

## Fetch and Open in the VSCode Container
```
gh repo clone AisleAI/aisle-dev
cd aisle-dev
code .
```

### Choose "Reopen in Container"
![Screenshot 2024-07-23 at 12 01 22 AM](https://github.com/user-attachments/assets/9357340a-ec23-4d61-888c-9f07502777be)

## Login to Github
```
# From within a terminal in the VSCode container
gh auth login
```

![Screenshot 2024-07-23 at 12 21 49 AM](https://github.com/user-attachments/assets/854f1d3a-f3aa-40ae-8105-221258372cfd)
<img width="602" alt="Screenshot 2024-07-23 at 12 22 22 AM" src="https://github.com/user-attachments/assets/84fef2d5-ddf0-4ea1-992c-a0716117434a">

## Clone Aisle
```
gh repo clone AisleAI/aisle
cd aisle
```

## Create the Python Environment asnd Install Packages
```
python -m venv venv
source venv/bin/activate 

pip install -r requirements.txt
cp .env.example .env
```

## Migrate
```
python manage.py migrate
```

## Run the Server
[http://127.0.0.1:8000/](http://127.0.0.1:8000/)
```
python manage.py runserver
```
