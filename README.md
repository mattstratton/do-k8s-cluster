# do-k8s-cluster
Quick and dirty pulumi program to spin up a k8s cluster on Digital Ocean.

1. [Install Pulumi](https://www.pulumi.com/docs/get-started/install/)
1. [Configure Pulumi for Digital Ocean](https://www.pulumi.com/docs/intro/cloud-providers/digitalocean/setup/)
1. [Configure Pulumi for Python](https://www.pulumi.com/docs/intro/languages/python/)

## Instructions
Clone this repo.

1. Create a new stack:

    ```bash
    $ pulumi stack init
    ```

2. Set your configuration values for the cluster you want to create (replace names as appropriate)

```bash
$ pulumi config set cluster-name my-cluster

$ pulumi config set node-count 4

$ pulumi config set node-pool-name my-cluster-pool

$ pulumi config set node-size s-1vcpu-2gb

$ pulumi config set region nyc3

$ pulumi config set tag my-cluster
```

3. Run `pulumi up` to preview and deploy changes:

4. You can get the `kubeconfig` by running:

```bash
$ pulumi stack output kubeconfig --show-secrets > kubeconfig
```

## Clean up

To clean up/delete the cluster, run `pulumi destroy`
