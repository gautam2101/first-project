# install Apache Airflow

Step 1: Clone the Project from GitHub

Open your terminal (Git Bash, PowerShell, or CMD) and run:

git clone https://github.com/gautam2101/first-project.git
cd first-project


This downloads the project folder and moves you inside it.

Step 2: Verify Docker Compose File

Make sure the folder contains a file named docker-compose.yml. This file is required to start Airflow with Docker.

If the file is named differently (e.g., abc.yml), note the filename for the next steps.

Step 3: Initialize Airflow Database

Run the following command to initialize the Airflow environment:

docker-compose up airflow-init


If your compose file has a different name, use:

docker-compose -f abc.yml up airflow-init

Step 4: Start Airflow Containers

Start all Airflow containers in detached mode:

docker-compose up -d


Or if the compose file is named differently:

docker-compose -f abc.yml up -d

Step 5: Access Airflow UI

Open your web browser and go to:

http://localhost:8080


You should see the Airflow dashboard.

Step 6: Create an Admin User (if needed)

If no user exists or login is required, create an admin user:

docker-compose run --rm webserver airflow users create \
    --username admin \
    --firstname Admin \
    --lastname User \
    --role Admin \
    --email admin@example.com \
    --password admin

Step 7: Stop Airflow

When done, stop and remove containers with:

docker-compose down
