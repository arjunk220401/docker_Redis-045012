# Redis Docker Setup and Usage

## Introduction
Redis is an open-source, in-memory data structure store that can be used as a database, cache, and message broker. With its high performance and versatility.

Redis is widely used in real-time applications, such as chat applications, gaming leaderboards, and caching.

This project demonstrates how to deploy Redis as a containerized service using Docker, manage its data, and access its CLI for database operations.

## Learning Objectives
Docker: Learn how to deploy and manage Redis using Docker containers.

Redis CLI: Understand how to interact with Redis using its command-line interface.

Container Management: Learn how to start, stop, and manage Redis containers effectively.

## Prerequisites

Docker: Ensure Docker is installed and running on your system. Docker Installation Guide

Optional: Install docker-compose for easier multi-container management. Docker Compose Installation Guide

## Steps to Set Up Redis with Docker

## 1. Pull the Redis Docker Image
   
Download the latest Redis image from Docker Hub.

Command:

docker pull redis

Explanation:

This command fetches the Redis image from the Docker repository.

## 2. Run the Redis Container
   
Start a Redis container in detached mode.

Command:

docker run --name redis-container -d redis

Explanation:

--name redis-container: Names the container as "redis-container".

-d: Runs the container in detached mode, so it operates in the background.

## 3. Verify Running Containers
   
Check if the Redis container is running.

Command:

docker ps

Expected Output:


CONTAINER ID   IMAGE    COMMAND               STATUS          PORTS   NAMES

<container_id> redis    "docker-entrypoint…"  Up X seconds    ...     redis-container

## 4. Access Redis CLI
   
Connect to the Redis CLI to interact with the database.

Command:


docker exec -it redis-container redis-cli

Expected Output:

127.0.0.1:6379>

Example Commands in Redis CLI:

PING Command: Test the connection.

127.0.0.1:6379> PING

PONG

Set and Get Values:

127.0.0.1:6379> SET key "value"

OK

127.0.0.1:6379> GET key

"value"

To exit the Redis CLI, type:


127.0.0.1:6379> exit

## 5. Run a Temporary Redis Container

If you need a temporary Redis CLI instance:

Command:

docker run --rm -it redis redis-cli

Explanation:

--rm: Removes the container automatically after exiting.

-it: Opens an interactive terminal session.

## 6. Stop the Redis Container

To stop the Redis container:

Command:

docker stop redis-container

Expected Output:


redis-container

## 7. Remove the Redis Container

To completely remove the container:


docker rm redis-container

Expected Output:

redis-container

## 8. Verify All Containers

To list all containers (active or inactive):

Command:

docker ps -a


## Conclusion
This project demonstrates how to quickly set up and manage a Redis instance using Docker. 

Redis’s flexibility as a database, cache, and message broker makes it a vital tool for many real-time applications.

## Future Improvements

Data Persistence: Explore Redis persistence using volumes to store data outside the container.

Clustering: Learn how to set up Redis clusters for scalability.

Monitoring: Use tools like RedisInsight or Prometheus for monitoring Redis performance.

Docker Compose: Automate Redis deployments in complex systems with docker-compose.

## References

https://hub.docker.com/_/redis

Official Redis Documentation
