# promstack-argocd
Deploying the Kube-Prometheus-Stack along with dashboards and alerting rules using Kubernetes resources and ArgoCD
-------------------------------------------------------------------
First, we need to create secrets for admin Credentials.
Then we need to create some custom Dashboards and Alerting Rules
Then we need to create some ConfigMap for Alerting Rules
Later have to configure the Helm Values file
Later have to Create an ArgoCD Application Manifest
Then the last we can Deploy with ArgoCD 
1. apply the secrets, config maps, and Helm values -:
**kubectl apply -f secrets.yaml
kubectl apply -f custom-dashboards-configmap.yaml
kubectl apply -f custom-alert-rules-configmap.yaml**
Then at the last we can create the argocd application
**kubectl apply -f argocd-application.yaml**


**ArgoCD will now deploy the Kube-Prometheus-Stack Helm chart with custom dashboards and alerting rules in the Kubernetes cluster. Sensitive information such as admin passwords and SMTP credentials is securely managed by using Kubernetes secrets**
**We can adjust the Helm values file and ArgoCD application manifest according to our specific requirements and configurations.**
