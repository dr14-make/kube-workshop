```
helm repo add external-secrets https://charts.external-secrets.io

helm install external-secrets \
   external-secrets/external-secrets \
    -n external-secrets \
    --create-namespace \
   --set installCRDs=true

```


Follow this tutorial https://external-secrets.io/latest/provider/doppler/



# Core Resources
[DOCS](https://external-secrets.io/latest/api/externalsecret/)

## ExternalSecret

The ExternalSecret describes what data should be fetched, how the data should be transformed and saved as a Kind=Secret

## SecretStore

The SecretStore is namespaced and specifies how to access the external API. The SecretStore maps to exactly one instance of an external API.

By design, SecretStores are bound to a namespace and can not reference resources across namespaces.

## ClusterSecretStore

The ClusterSecretStore is a cluster scoped SecretStore that can be referenced by all ExternalSecrets from all namespaces. Use it to offer a central gateway to your secret backend.

## ClusterExternalSecret

The ClusterExternalSecret is a cluster scoped resource that can be used to manage ExternalSecret resources in specific namespaces.

With namespaceSelectors you can select namespaces in which the ExternalSecret should be created. If there is a conflict with an existing resource the controller will error out.