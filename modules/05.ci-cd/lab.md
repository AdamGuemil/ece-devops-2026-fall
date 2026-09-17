
# Lab

Continuous Integration & Continuous Delivery (Deployment) (CI/CD)

## Objectives

1. Part 1. Continuous Integration with GitHub Actions
2. Part 2. Continuous Delivery (Deployment) with Render

## Before starting

Before starting configuring CI/CD to a software project, you need to have its repository on GitHub.

> Note. Skip the following steps if you already have a repository on GitHub containing the application from the previous [Continuous Testing lab](../04.continuous-testing/lab.md).

1. Create a Git repository for the User API project imported from [../03.continuous-testing/lab/](../03.continuous-testing/lab/), and commit all the files. 
2. Create a remote repository on GitHub, link it with the local one, and push the changes.

## Part 1. Continuous Integration with GitHub Actions

1. Read the [introduction to GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/introduction-to-github-actions).

2. Create a CI workflow for the Node.js using this [documentation](https://docs.github.com/en/actions/guides/building-and-testing-nodejs). 

> Note. Don't forget to commit and push your workflow configuration in the `.github/workflows` folder **under the root** of you Git repository.

Does your workflow work? Is there any problem with the connection to Redis?

3. Improve your Workflow to connect Node.js application to Redis using this documentation:
  - [About service containers](https://docs.github.com/en/actions/guides/about-service-containers)
  - [Creating Redis service containers](https://docs.github.com/en/actions/guides/creating-redis-service-containers)

4. Practice a regular workflow of the software development life cycle, for example for completing the [Lab 3 instructions](../03.continuous-testing/lab.md). 

Create a pull request to the `master` branch:

- create a new branch and publish it to your remote GitHub repository
- make any change in your source code, commit and push it
- make a **Pull Request** on GitHub
- wait for GitHub Actions to test it (observe the process on GitHub -> Actions page)
- review the commit and Merge this Pull Request into the `master` branch

5. Explore the GitHub Actions log on GitHub (under the "Actions" tab).

## Part 2. Continuous Delivery (Deployment) with Render and Upstash

1. Create an account on [Render](https://render.com/) and on [Upstash](https://upstash.com/).
2. Create a redis database on [Upstash](https://console.upstash.com/redis). Once created, you will have informations displayed such as the database url.
3. Create an app on [Render](https://dashboard.render.com/web/new) and configure it. You can follow [this guide](https://render.com/docs/your-first-deploy) to help you.
> Note that the `REDIS_URL` must be defined in your Render environment variables to let Render connect to the Redis database once your application is deployed. Be carefull, you need to set the Redis url starting with `rediss://` and not `redis://`.
4. Configure the workflow to deploy to Render using [this guide](https://render.com/docs/your-first-deploy).
4. Practice a regular workflow of the software development life cycle like in Part 2.
5. Test your public domain on Render.

## Bonus tasks

1. Integrate Swagger UI using this package - https://www.npmjs.com/package/express-swagger-generator
