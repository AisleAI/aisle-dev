# PostgreSQL + pgvector Dev Container / Codespace

This is a PostgreSQL dev container for use with VS Code Remote Containers or GitHub Codespaces.
The devcontainer.json uses a docker-compose.yaml to set up a local PostgreSQL server inside the container.

For use with the local PostgreSQL server,  copy `.env.devcontainer` into `.env`.

For use with an Azure PostgreSQL server,  copy `.env.azure` into `.env` and adjust the host name, user name, and password.

Then run one of the examples in the `examples` directory.

# Aisle Installation



## Fetch and Open in the VSCode Container
```
gh repo clone AisleAI/aisle-dev
cd aisle-dev
code .
```

### Choose "Reopen in Container"
![Screenshot 2024-07-23 at 12 01 22 AM](https://github.com/user-attachments/assets/9357340a-ec23-4d61-888c-9f07502777be)

## Login to Github and Clone Aisle
```
gh auth login
gh repo clone AisleAI/aisle
cd aisle
```

## Create the Python Environment asnd Install Packages
```
python -m venv venv
source venv/bin/activate 

pip install -r requirements.txt
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
