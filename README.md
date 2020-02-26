# Tools

- JDK 1.8 or greater.
- Maven
- Docker

# Running tests with Docker

Create a shared volume for persisting the maven artifacts:

```bash
$ docker volume create --name maven-repo
```

Run tests:

```bash
$ docker run -it --rm -v maven-repo:/root/.m2 -v $PWD:/app maven:3.6-jdk-11 mvn -f /app/pom.xml clean test
```

# Running tests without Docker

Build the project source:

```bash
$ mvn clean package
```

Run tests:

```bash
$ mvn test
```
