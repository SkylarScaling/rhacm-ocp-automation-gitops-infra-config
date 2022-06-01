# imageregistry

imageregistry contains configurations to support managing the [default Image Registry](https://docs.openshift.com/container-platform/4.5/registry/configuring-registry-operator.html)

## Exposing OpenShift registry

By default, access to the default image registry is not exposed outside the cluster. Access to the registry can be exposed by setting `defaultRoute: true` on the `configs.imageregistry.operator.openshift.io/cluster` resource. 

The created route will take the form `default-route-openshift-image-registry.apps.<subudomain>`

Additional information can be found in [this](https://docs.openshift.com/container-platform/4.5/registry/securing-exposing-registry.html) document.
