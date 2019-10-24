# Lab setup - web terminal and resources

You will already need an IBM Cloud account and an IBM Kubernetes Service cluster (free or paid) in order to proceed.

## Set up the web terminal

1. Log in to the [IBM Cloud](https://cloud.ibm.com) to the dashboard

2. Click on the top left navigation menu and select **Kubernetes**

    ![Navigation Menu](../.gitbook/assets/navigation-menu.png)

3. Open the control panel for your cluster by clicking on the name

    ![Open Cluster](../.gitbook/assets/open-cluster.png)

4. Click on the **Web terminal** button

    ![Open Web Termina](../.gitbook/assets/open-web-terminal.png)

5. Click on the **Install** button if prompted (this won't be shown if the terminal is already installed). Getting the terminal ready will take a couple of minutes. If you click on the **Web terminal** button before it's ready you will see

    ![Kubernetes terminal unavailable](../.gitbook/assets/terminal-unavailable.png)

6. Open the web terminal - it will initially display at the bottom of the browser panel. Click on the expand button to open the terminal in a full browser tab:

    ![Expand the web terminal](../.gitbook/assets/expand-terminal.png)

7. Run the `ibmcloud ks clusters` command to verify the terminal and setup for access to the cluster:

    ![Confirm clustert access](../.gitbook/assets/terminal-ready.png)

8. Configure the `kubectl` cli available within the terminal for access to your cluster and verify access to the Kubernetes API

    ```bash
    $ eval $(ibmcloud ks cluster-config --cluster mycluster --export)
    $ kubectl get namespace
    NAME              STATUS   AGE
    default           Active   125m
    ibm-cert-store    Active   121m
    ibm-system        Active   124m
    kube-node-lease   Active   125m
    kube-public       Active   125m
    kube-system       Active   125m
    ```

    If your output looks like that - you're good to go with the rest of the lab exercises.

## Clone the lab repository

1. In some of the labs, you will be creating Kubernetes resources by applyig `.yaml` files representing the desired state for the resource. To save typing in all of that, clone the lab repository into your web terminal:

    ```text
    $ git clone https://github.com/timroster/digidevcon-iks
    Cloning into 'digidevcon-iks'...
    remote: Enumerating objects: 61, done.
    remote: Counting objects: 100% (61/61), done.
    remote: Compressing objects: 100% (44/44), done.
    remote: Total 61 (delta 13), reused 61 (delta 13), pack-reused 0
    Unpacking objects: 100% (61/61), done.
    ```

Continue on to the [next exercise](../exercise-1/README.md).