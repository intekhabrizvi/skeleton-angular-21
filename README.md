# Angular 21 Skeleton

A secure Angular 21 development setup. This angular skeleton comes with pre-installed...

- tailwind css
- spartan/ui


## Quick start

1. Clone the repo (if not done yet) and go inside the folder

2. Start the container (change the container name or other details if needed)

```bash
docker compose up -d; docker compose logs -f;
```

The first-time startup will take 5 or more minutes, depending on your internet connection.

3. Visit the following URLs to verify the working

```bash
http://127.0.0.1:4200/
```

### if this is your first time starting the container, then execute the steps below as well.

4. Correct the node_modules permission (add the correct container name)

```bash
docker exec -it frontend /bin/sh -c "chown -R 1000:1000 /app/"
```

5. Stop the container

```bash
docker compose down
```

6. Edit the `docker-compose.yaml` file. Find the line `#user: "${UID}:${GID}"` and remove the `#` from the beginning. Save the file.

7. Start the container. This is your secure container for Angular 21 development.

```bash
docker compose up -d; docker compose logs -f;
```

## Install additional npm packages

To install any additional node packages, execute the `npm install` command as usual. Example

```bash
docker exec -it frontend npm install tailwindcss @tailwindcss/postcss postcss
```

## Delete the node_module and fresh install everything

1. Start the container (if not running)

```bash
docker compose up -d;
```

2. Stop the container with the delete volume flag
```bash
docker compose down -v
```

3. Start the container again. This will reinstall all the node packages listed inside the `package-lock.json` file

```bash
docker compose up -d; docker compose logs -f;
```

4. Follow all the steps again from `step no 4` from the `Quick Start` section.
