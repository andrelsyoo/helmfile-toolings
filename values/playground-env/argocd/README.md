# Just a little info context

Access your Argo CD installation:

Execute the following commands:

```
kubectl port-forward --namespace argocd svc/argocd-argo-cd-server 8080:80 &
export URL=http://127.0.0.1:8080/
echo "Argo CD URL: http://127.0.0.1:8080/"
```

Execute the following commands to obtain the Argo CD credentials:

```
echo "Username: \"admin\""
echo "Password: $(kubectl -n argocd get secret argocd-secret -o jsonpath="{.data.clearPassword}" | base64 -d)"
```