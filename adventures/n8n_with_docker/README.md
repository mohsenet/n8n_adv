# Run n8n with Docker


#### [1]
In the Docker hub search `n8n` and select the most downloaded image and copy the `Docker Pull Command`.

https://hub.docker.com/r/n8nio/n8n

```bash
docker pull n8nio/n8n
```


#### [2]
Make a docker-compose file

```bash
touch docker-compose.yml
```


#### [3]
Edit your `docker-compose.yml`

```yml
services:
  n8n:
    image: n8nio/n8n
    container_name: n8n
    ports:
      - "5678:5678"
    volumes:
      - n8n_data:/home/node/.n8n
    restart: unless-stopped

volumes:
  n8n_data:
```


#### [4]
Then recreate the container:

```bash
sudo docker-compose down -v
sudo docker-compose up -d
```

#### [5]
Check logs:

```bash
sudo docker-compose logs -f
```

#### [5]
Sample demo to run n8n with Docker:

- [Sample demo on Youtube](https://www.youtube.com/watch?v=dQw4w9WgXcQ)
