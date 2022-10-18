# Action-c

* [action-c](.github/workflows/action-c.yml) workflow for create and destroy Azure Kubernetes Service (AKS).

* [Configure Azure credentials](https://github.com/Azure/actions-workflow-samples/tree/master/Kubernetes) before applies labels.
* Applies a "spin up environment" label to a [pull request](../../pull/3), for set up our resources on an Azure environment.
* Applies a "destroy environment" label to a [pull request](../../pull/3), for tear down any resources that are running on our Azure environment.
