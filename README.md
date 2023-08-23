# Add Docker to Your Spring Boot Application

This example app shows how to package a Spring Boot application with Docker. See [Add Docker to Your Spring Boot Application][blog-post] to see how it was built.

## Prerequisite

- **Java 11**: If you don't have Java 11, you can install OpenJDK. Instructions are found on the [OpenJDK website](https://openjdk.java.net/install/).
- **Docker** - We recommend [Docker Desktop](https://www.docker.com/products/docker-desktop)
- **Okta Developer Account**: Go to [the Okta website](https://developer.okta.com/signup/) and sign up for a free developer account, if you haven't already.

> [Okta](https://developer.okta.com/) has Authentication and User Management APIs that reduce development time with instant-on, scalable user infrastructure. Okta's REST API and makes it easy for developers to authenticate, manage, and secure users + roles in any application.

* [Getting Started](#getting-started)
* [Create OIDC App](#create-a-new-oidc-app-in-okta)
* [Configure the Resource Server](#configure-the-resource-server)
* [Run the Resource Server](#run-the-resource-server)
* [Help](#help)
* [License](#license)

## Getting Started

To install this example application, run the following commands:

```bash
git clone https://github.com/oktadeveloper/spring-boot-docker-example.git
```

## Create a New OIDC App in Okta

Before you begin, you'll need a free Okta developer account. Install the [Okta CLI](https://cli.okta.com) and run `okta register` to sign up for a new account. If you already have an account, run `okta login`.

Then, run `okta apps create`. Select the default app name, or change it as you see fit. Choose **Web** and press **Enter**.

Select **Okta Spring Boot Starter**. Accept the default Redirect URI values provided for you. That is, a Login Redirect of `http://localhost:8080/login/oauth2/code/okta` and a Logout Redirect of `http://localhost:8080`.

The Okta CLI will create an OIDC Web App in your Okta Org. It will add the redirect URIs you specified and grant access to the Everyone group. You will see output like the following when it's finished:

```shell
Okta application configuration has been written to:
  /path/to/app/src/main/resources/application.properties
```

Open `src/main/resources/application.properties` to see the issuer and credentials for your app.

```properties
okta.oauth2.issuer=https://dev-133337.okta.com/oauth2/default
okta.oauth2.client-id=0oab8eb55Kb9jdMIr5d6
okta.oauth2.client-secret=NEVER-SHOW-SECRETS
```

You can also use the Okta Admin Console to create your app. See [Create a Spring Boot App](https://developer.okta.com/docs/guides/sign-into-web-app/springboot/create-okta-application/) for more information.

## Run the Application

To run the Spring Boot application

```bash
./mvnw spring-boot:run
```

See the [blog post] for details on building the Docker container and managing your configuration.

## Help

Please post any questions as comments on the [blog post] or post them to Stack Overflow with the `okta` tag.

## License

Apache 2.0, see [LICENSE](LICENSE).

[blog-post]: https://developer.okta.com/blog/2019/12/27/spring-boot-deploy-docker
