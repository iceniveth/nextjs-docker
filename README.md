# With Docker

This examples shows how to use Docker with Next.js based on the [deployment documentation](https://nextjs.org/docs/deployment#docker-image). Additionally, it contains instructions for deploying to Google Cloud Run. However, you can use any container-based deployment host.

## Setup

- [Install Docker](https://docs.docker.com/get-docker/) on your machine.
- Create an `.env.local` file with empty content.

### Docker

- Build the image: `docker build -t nextjsproject -f Dockerfile.dev .`.
- Run the container: `docker run --rm --env-file=.env.local -v "$(pwd):/app" -p 3333:3333 nextjsproject`.
- Open [http://localhost:3333](http://localhost:3333) on the browser to see the result.

### Docker Compose

- Build and run the container: `docker-compose up`
- Open [http://localhost:3333](http://localhost:3333) on the browser to see the result.

## Deployment

- Build the image: `docker build -t nextjsproject.prod -f Dockerfile.prod .`.
- Run the container: `docker run --rm -p 3333:3333 --name nextjsproject-prod-container nextjsproject.prod`.

> Closing the terminal doesn't stops the server from running on port 3333. To stop, run: `docker stop nextjsproject-prod-container`.
