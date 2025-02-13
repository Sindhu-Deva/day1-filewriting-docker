# Authentication Microservice

This Docker image provides an authentication microservice with user management functionality. It allows users to sign up, sign in, sign out, and update their profile information. It uses JSON Web Tokens (JWT) for authentication.

## Usage

To run a container from this image, use the following command:

```bash
docker run -p 3003:3003 authentication-microservice
```

The microservice will be accessible at `http://localhost:3003`.

### API Endpoints

- `POST /api/signup`: Sign up a new user.
- `POST /api/signin`: Sign in an existing user.
- `POST /api/signout`: Sign out the currently authenticated user.
- `GET /api/protected`: Example of a protected route that requires authentication.
- `PUT /api/update`: Update the profile information of the authenticated user.

## Environment Variables

This microservice does not require any environment variables to be set.

## Volumes

This microservice does not use any volumes.

## Docker Network

To enable communication between the Authentication microservice and other microservices or applications, ensure that the containers are connected to the same Docker network. You can achieve this by following these steps:

1. Create a Docker network:
  ```bash
  docker network create my-network
  ```

2. Run the Authentication microservice container with the `--network` flag:
  ```bash
  docker run --network my-network -p 3003:3003 authentication-microservice
  ```

3. Run other microservice or application containers on the same network:
  ```bash
  docker run --network my-network -p 4000:4000 ecommerce-ui
  ```

By connecting the containers to the same Docker network, they can communicate with each other using their container names as hostnames.