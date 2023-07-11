# GitLab CI/CD Pipelines Testing With Jenkins

![https://docs.gitlab.com/ee/ci/introduction/](<CI-CD Concepts.png>)

[GitLab CI/CD Pipeline Concept](https://docs.gitlab.com/ee/ci/introduction/)

# About

This repository contains a GitLab pipeline configuration file `gitlab-ci.yml` that automates the build, test, and deployment processes for an API. The pipeline consists of the following stages:

## Stages
- **Build:** This stage is responsible for building the necessary artifacts or dependencies required for the API.
- **Test:** This stage executes API tests to ensure the functionality and quality of the code. 
- **Deploy:** This stage handles the deployment of the API to the desired environment.

## Test Stage
The `test` stage is configured to execute API tests using [Newman](https://www.postman.com/newman/), a command-line tool for running [Postman](https://www.postman.com/) collections. 

Newman is a command-line tool provided by Postman that allows you to run Postman collections and execute API tests programmatically. It provides a way to automate API testing and integrate it into CI/CD pipelines.

The purpose of the `newman run` command in the GitLab pipeline is to run the Postman tests programmatically. Here are more details about the command:

```
newman run path/to/your/postman_collection.json --environment path/to/your/postman_environment.json
```

- `newman run`: This command invokes Newman and triggers the execution of Postman tests.
- `path/to/your/postman_collection.json`: This represents the file path to the Postman collection JSON file. The collection file contains all the requests and tests for your API.
- `path/to/your/postman_environment.json`: This represents the file path to the Postman environment JSON file. The environment file holds the environment variables used in the API tests.

By including this command in the pipeline's `test` stage, it ensures that the API tests defined in the Postman collection are executed automatically. The purpose is to validate the behavior and correctness of your API endpoints as part of the continuous integration and deployment process.

## Deploy Stage
The `deploy` stage is responsible for deploying the API to the desired environment. The following action is performed within the `deploy` stage:
- Printing a message to indicate that the API is being deployed.

Please refer to the `gitlab-ci.yml` file in this repository for the detailed pipeline configuration. 

# GitLab Personal Runner

To execute this pipeline, GitLab personal runner was utilized. The personal runner is a machine or virtual environment that runs the CI/CD jobs defined in the pipeline configuration. It enables the seamless execution of the pipeline stages on the runner's environment.

![Runner Deatils](<Runner Details.jpg>)

# CI/CD Pipeline Result

Pipeline job results:

![Pipeline Result](<Pipeline Result.png>)

# License

This repository is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code in this repository for both commercial and non-commercial purposes. Please see the [LICENSE](LICENSE) file for more details.

