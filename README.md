# Streamlit Application with Docker and PostgreSQL
# What We Did


## Commands Used

 
### 1: Pull the PostgreSQL Docker Image
```sh
docker pull postgres
```

### 2: Create a Docker Network
```sh
docker network create my_postgres_network
```
This network allows PostgreSQL and the Streamlit app to communicate.

### 3: Run the PostgreSQL Container
```sh
docker run --name my_postgres_container --network my_postgres_network -e POSTGRES_USER=tarak -e POSTGRES_PASSWORD=secret -e POSTGRES_DB=testdb -p 5432:5432 -d postgres
```
This starts a PostgreSQL container with authentication settings.
i
### 4: Access PostgreSQL
```sh
docker exec -it my_postgres_container psql -U tarak -d testdb
```

### 5: Build Docker image:
```bash
docker build -t streamlit-app .
```

### 6: Run the Streamlit Container
```sh
docker run --name my_streamlit_container --network my_postgres_network -p 8501:8501 -d streamlit-app
```
This ensures that the Streamlit app can communicate with PostgreSQL.

## Screenshots

![Screenshot 1](images/Screenshot%202025-04-23%20164611.png)

![Screenshot 2](images/Screenshot%202025-04-23%20164643.png)

![Screenshot 3](images/Screenshot%202025-04-23%20164657.png)

![Screenshot 4](images/Screenshot%202025-04-23%20164725.png)

![Screenshot 5](images/Screenshot%202025-04-23%20164746.png)

![Screenshot 6](images/Screenshot%202025-04-23%20165117.png)