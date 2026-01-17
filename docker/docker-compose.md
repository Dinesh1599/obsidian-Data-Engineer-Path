How a docker-compose file is structured:

##  Top Level Structure
```yml
version: "3.9"	
service:   # What image you want to run
networks:  # How the service talks
volumes:   # Where the data lives
configs:   # Config files
secrets:   # Secrets	
```

## Services
 ```yml
	
services:
	app:
	    image: my-app:latest        # OR build:
		build: ./app                # Dockerfile location
	    container_name: my_app
    ports:
      - "8080:8080"
    environment:
      - ENV=production
    env_file:
      - .env
    volumes:
      - ./app:/app
    depends_on:
      - db
    networks:
      - backend
```

### Definition of each of these services

| Key           | Purpose                       |
| ------------- | ----------------------------- |
| `image`       | Image to run                  |
| `build`       | Build image from Dockerfile   |
| `ports`       | Host ↔ container port mapping |
| `environment` | Environment variables         |
| `env_file`    | Load vars from `.env`         |
| `volumes`     | Mount files / persist data    |
| `depends_on`  | Startup order                 |
| `command`     | Override default CMD          |
| `restart`     | Restart policy                |
