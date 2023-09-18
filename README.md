# Selenium-testing-time-benchmark

This is a super-repository for comparing writing unit tests between JUnit + Selenium and SeleniumJupiter on SpringBoot page.

# Requirements

- Java (to run JUnit 5, Selenium, Webdriver Manager, SeleniumJupiter)
- Docker (For easy startup)
- Sedative pills for working with Java

---



# Before starting up
For downloading the submodules:
```bash
git submodule update --init --recursive
```

If you want to ***easly*** start the PetClinic backend you need to create docker image.

```bash
cd spring-petclinic
./mvnw package
./mvnw spring-boot:build-image
```

Now the Java is building the image. Once the Docker image is built, you can run it using Docker. The image will be named something like `docker.io/library/spring-petclinic:0.0.1-SNAPSHOT`. You can find the exact name in the output of the previous command. If you ran to any problems check your JAVA_PATH, or can you run Java at all.

Replace `<image-name>` in the following command with the name of your Docker image:

```bash
docker run -p 8080:8080 <image-name>
```

Or you can use ***docker images*** for checking the images that your docker already has.

The repo has a submodule for petclinic so if the version changes you might need to update the **docker-compose.yaml** following this structure:

```docker
image: spring-petclinic:3.1.0-SNAPSHOT
```

`<REPOSITORY>:<TAG>`

---



# How to run

In the folder with docker-compose.yaml run:

```bash
docker compose up
```

When the pet clinic goes up, you can start testing the page as you see fit.

To run the tests, open up your IDE (preferably IntelliJ), resolve the dependencies, install necessary plugins to run the tests (Like JUnit for IntelliJ).

If you are getting an error regaring some method called toImmutableList()) then one of your dependencies is using Guava 19.0 or older than 21.0. Delete it, other dependencies use newer version.
