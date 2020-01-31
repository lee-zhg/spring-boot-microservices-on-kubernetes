# Develop a Java Microservice with Spring Boot

IBM Cloud provides `Starter Kits` as the starting point of quick cloud native development and deployment. For example
   * Java Microservice with Spring
   * Java Microservice with Eclipse MicroProfile and Java EE
   * Node.js Microservice with Express.js
   * Python Microservice with Flask

In this session, you develop a Java Microservice using the `Java Microservice with Spring` starter kit. With this kit, you can have a basic Java microservice developed and deployed in a few minutes. You create a CI/CD pipeline in IBM Cloud which automates your service's deployment to Kubernetes cluster.

The Java source code is available in the Git repo that is created as part of the CI/CD pipeline. It can serve as a starting point of your development project. You can download the repo to your local machine, develop and test your service locally, then check in the complete version of your project back to your Git repo. This will trigger a re-build and re-deployment process. The latest version of your microservice is deployed and running in Kubernetes cluster.

`Java Microservice with Spring Boot` starter kit is used as an example to jump start a development project of `Java Microservice`. Other starter kits in the IBM Cloud work similarly. If you prefer other language or framework in your project, the steps in this session can still be applied.

The instructions were adapted from the more comprehensive tutorial found here - https://cloud.ibm.com/docs/apps/tutorials?topic=creating-apps-tutorial-scratch#prereqs-scratch.


## Create a Java Microservice with Spring Boot

To createa a Java Microservice with Spring Boot using the starter kit,

1. Login to IBM Cloud.

1. Select `Catalog` in your account dashboard.

1. Go to `Software` tab.

1. Search and select the `Java Spring App`.

   ![catalog-spring-boot-microservice](images/catalog-software01.png)

1. Click `Create app`.

1. Accept the default settings and click `Create`.

   ![spring-boot-microservice](images/javaservice.png)


## Create a Continuous Delivery pipeline

`Continuous Delivery` automates builds, tests, and deployments of your service through Delivery Pipeline, GitLab, and more. By default, it is not enabled.

To enable the continous delivery for your service,

1. On the `App details` page, click the `Deploy your app` button in the `Configure continuous delivery` section.

   ![microservice-cd](images/configure_cd.png)

1. Select the `IBM Cloud Kubernetes Service` option.

   ![microservice-cd-k8s](images/configure_cd_k8s.png)

1. Click `New` to generate a new `IBM Cloud API key`.

1. Click `OK` when prompted.

1. Select the desired `Region` and `Cluster`.

1. Select the `Region` to create your toolchain in, and then select the `Resource group` that provides access to your new toolchain.

   ![microservice-cd-k8s](images/configure_cd_k8s02.png)

1. Accept the defaults for the rest of settings and `Create`.

1. It may take a few minutes to complete the `Continuous Delivery` configuration. You can continue to the next step.

   ![cd-k8s-configured](images/cd_k8s_configured.png)

1. The toolchain offers two main components.

   A `Git repo` is created for storing the source code of your service development project. It also provides version control service.

   A `Deliver Pipeline` is also created. It automates builds, tests, and deployments of your service.

1. Click on the name of your toolchain. For example, `JavaSpringAppXXXXXX` to open the `Delivery Pipeline` window.

1. The `Delivery Pipeline` should run through its stages. This may take a few minutes. After it completes, you should see **Stage Passed** messages for each stage.

   ![cd-k8s-pipeline](images/cd_pipeline_suc.png)


## Verify your service

Now, your microservice is running in your Kubernetes cluster on IBM Cloud.

1. To find out how your servoice can be accessed, execute commands below

   ```
   $ ibmcloud ks workers <your cluster>

   $ kubectl get svc
   ```

   Locate the `Public IP` and `Port(s)`.

1. To verify your microservice, enter http:<Public IP>:<Port> in a browser.

   ![k8s-microservice](images/k8s-microservice.png)


