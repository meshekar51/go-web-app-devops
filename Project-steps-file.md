EKS with Private:

We will spin up bastian host to access api server

1. spin up the bastian host from same vpc as Worker node
2. create access keys and add it in eks access section to access eks
3. in bastian host configure aws cli and kubectl
4. setup kubeconfig file
   aws sts get-caller-identity
   
   aws eks update-kubeconfig \
  --region eu-west-1 \
  --name my-eks-cluster

5.As this is CD part lets install argocd in cluster
   kubectl apply --server-side --force-conflicts -k https://github.com/argoproj/argo-cd/manifests/crds\?ref\=stable

6. Then take access of argocd webui using bastian host
