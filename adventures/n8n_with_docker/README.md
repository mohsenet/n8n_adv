# Run n8n with Docker


#### [1]
Make a docker-compose file

```bash
touch docker-compose.yml
```


#### [2]
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


#### [3]
Then recreate the container:

```bash
sudo docker-compose down -v
sudo docker-compose up -d
```

#### [4]
Check logs:

```bash
sudo docker-compose logs -f
```
