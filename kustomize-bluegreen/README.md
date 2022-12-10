# ArgoCD Kustomize Blue/Green Example

This repository contains example applications for demoing ArgoCD functionality. Feel free
to register this repository to your ArgoCD instance, or fork this repo and push your own commits
to explore ArgoCD and GitOps!

| Application | Description |
|-------------|-------------|
| [helm-guestbook](helm-guestbook/) | The guestbook app as a Helm chart |
| [kustomize-bluegreen](kustomize-bluegreen/) | The guestbook app as a Kustomize 2 app |




$ kubectl argo rollouts -n argo-test set image guestbook-ui guestbook-ui=heptio-images/ks-guestbook-demo:0.2

$ kubectl argo rollouts list rollouts -n argo-test


argocd app create --name kustomize-bluegreen --repo https://github.com/pdebuitlear/argocd-example-apps --dest-server https://kubernetes.default.svc --dest-namespace argo-test --path kustomize-bluegreen && argocd app sync 
kustomize-bluegreen