# useful aliases
```
alias k="kubectl"
alias kgp="kubectl get pods --all-namespaces -o wide"
alias ks="kubectl --namespace=kube-system"
alias wk="watch 'kubectl get pods -o wide'"
```

# important kubernetes commands
Show all pods in all namespaces at once
```
kubectl get pods -o wide --all-namespaces
```

Show all services in all namespaces
```
kubectl get svc --all-namespaces
```

Show connected endpoints (aka routing)
```
kubectl get endpoints
```

# How to create a ingress controller in AKS
https://docs.microsoft.com/bs-cyrl-ba/azure/aks/ingress-basic

