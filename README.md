# Dockerizing Flask with Postgres, Gunicorn, and Nginx

This is the boilerplate projet for run the Flask application in the Docker environment. Inspired by [this](https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/) article.

Technologies:

- Python
- Flask
- Docker
- Postgres
- Gunicorn
- Nginx

## Prerequisites

You will need [docker](https://docs.docker.com/engine/installation/) and [docker-compose](https://docs.docker.com/compose/install/).

## Usage

### Development

Uses the default Flask development server.

1. Rename `.env.dev.sample` to `.env.dev`.
2. Update the environment variables in the `docker-compose.yml` and `.env.dev` files.
3. Build the images and run the containers:

   ```bash
   $ docker-compose up -d --build
   ```

   Test it out at http://localhost:5000. The `web` folder is mounted into the container and your code changes apply automatically.

### Production

Uses **gunicorn** + **nginx**.

1. Rename `.env.prod.sample` to `.env.prod` and `.env.prod.db.sample` to `.env.prod.db`. Update the environment variables.
2. Build the images and run the containers:

   ```bash
   $ docker-compose -f docker-compose.prod.yml up -d --build
   ```

   Test it out at http://localhost:1337. No mounted folders. To apply changes, the image must be re-built.

## License

See [LICENSE](LICENSE) file.

## Contact

Please report issues or questions [here](https://github.com/nbbrdn/flask-on-docker/issues).
