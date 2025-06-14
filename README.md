# NextCourse API

## Running the Application
1. Clone the repository:

2. Create a virtual environment:
```bash
python3 -m venv env
source env/bin/activate  # On Windows use `venv\Scripts\activate`
```
3. Install the required packages:
```bash
pip install -r requirements.txt
```
4. Run the application:
```bash
python run.py
```

## Environment Variables
- `DATABASE_URL`: MySQL connection string. Example: `mysql+pymysql://username:password@host:port/db_name`
- `FLASK_ENV`: Set to `development` for development mode.
- `FLASK_APP`: The entry point of the application. Set to `run.py`.
- `JWT_SECRET_KEY`: Secret key for JWT.
= `REDIS_URL`: Redis connection string. Example: `redis://localhost:6379/0`. Used when `FLASK_ENV` is set to `production`.

## Apply Migration
1. Initialize the migration:
```bash
flask db init
```
2. Create a migration script:
```bash
flask db migrate -m "Initial migration."
```
3. Apply the migration:
```bash
flask db upgrade
```
4. If you need to downgrade:
```bash
flask db downgrade
```
5. Check the current migration version:
```bash
flask db current
```

## Docker
1. Build the Docker image:
```bash
docker build -t nc_api .
```
2. Run the Docker container:
```bash
docker run -d -p 5000:5000 --env-file .env nc_api
```
3. Access the application at `http://localhost:5000`.
4. Stop the Docker container:
```bash
docker ps  # Get the container ID
docker stop <container_id>
```

### Using Docker Compose
1. Build and run the Docker containers:
```bash
docker compose up --build
```
2. Stop the containers:
```bash
docker compose down
```
