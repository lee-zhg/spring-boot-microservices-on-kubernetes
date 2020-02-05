# Lab 0c. Connect to your kubernetes environment

Complete steps in this section to connect to your Kubernetes cluster.

1. Open a terminal window or command window.

    > **Note: use a web terminal if you attend a workshop**

2. Set an environment variable

    ```
    export USERNAME=user###
    ```

    > **Note: replace ### with your assigned ID**

3. Install the kubernetes and container registry plugins:
    ```
    ibmcloud plugin install kubernetes-service -r Bluemix    
    
    ibmcloud plugin install container-registry -r Bluemix
    ```

4. Login to [Kubernetes service in IBM Cloud](https://cloud.ibm.com/kubernetes/clusters).

5. Select your Kubernetes cluster.

6. Navigate to `Access` tab.

![access-cluster](../images/access-cluster.png)

7. In the above terminal window, complete all steps in the section `After your cluster provisions, gain access`.



