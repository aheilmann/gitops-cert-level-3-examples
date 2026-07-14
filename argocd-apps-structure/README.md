# Deployment notes

This will deploy the root app. Using argocd cli assumes that you have successfully logged in to the server with `argocd login`.

```
argocd app create root-argocd-app \
    --project default \
    --repo  https://github.com/aheilmann/gitops-cert-level-3-examples.git \
    --path "argocd-apps-structure" \
    --sync-policy auto \
    --dest-namespace argocd \
    --dest-server https://kubernetes.default.svc
```