To provide a definition for the custom resource that that the operator is to respond to, you need to create a Custom Resource Definition (CRD). For this example, the custom resource type name we will use is `PodSet`.

Because developers of different operators may choose to use the same name for a custom resource, resource types are grouped under an API group, where different developers would use their own unique name for the group.

To support the evolution of a custom resource over time, a version name also needs to be specified. The combination of the API group name and the version name is referred to as the API version.

For this example the API version `app.example.com/v1alpha1` is used, corresponding to the API group of `app.example.com` and the version name of `v1alpha1`. See the Kubernetes documentation for more information on [API versioning](https://kubernetes.io/docs/concepts/overview/kubernetes-api/#api-versioning) and [API groups](https://kubernetes.io/docs/concepts/overview/kubernetes-api/#api-groups).

To generate the code and YAML files corresponding to the `PodSet` custom resource type, run:

```execute
operator-sdk add api --api-version=app.example.com/v1alpha1 --kind=PodSet
```

The output from the command will list the files generated.

You can inspect the generated CRD, which describes the `PodSet` custom resource, by running:

```execute
deploy/crds/app_v1alpha1_podset_crd.yaml
```