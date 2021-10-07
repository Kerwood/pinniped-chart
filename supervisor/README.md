To download a new version of Pinniped Supervisor replace the version tag and downloaded the `install-pinniped-supervisor.yaml` file.

```
http -d https://get.pinniped.dev/v0.8.0/install-pinniped-supervisor.yaml -o templates/install-pinniped-supervisor.yaml
```

Create secret with the Azure App Registration creds for the supervisor.
```sh
kubectl create secret generic azure-oidc-client \
  --namespace pinniped-supervisor \
  --type secrets.pinniped.dev/oidc-client \
  --from-literal=clientID="<client-id-goes-here>" \
  --from-literal=clientSecret="<secret-goes-here>"
```