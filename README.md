# promstack-argocd
Deploying the Kube-Prometheus-Stack along with dashboards and alerting rules using Kubernetes resources and ArgoCD
-------------------------------------------------------------------
Firstly, we need to create secrets for admin Credentials. Then we need to create some custom Dashboards and Alerting Rule and then we need to create some ConfigMap for Alerting Rules,
Later have to configure the Helm Values file and then we can Create an ArgoCD Application Manifest. Then the last we can Deploy with ArgoCD.
1. apply the secrets, config maps, and Helm values -:

For the Secrets we need to install Sealed Secrets in your cluster.
Then we can use kubeseal command-line tool to create a Sealed Secret from your regular Secret. The Sealed Secret can be safely stored in your Git repository.

**kubeseal <secret.yaml > sealed-secret.yaml**
Then we can store the sealed-secret.yaml in your Git repository. Since it's encrypted, it's safe to be versioned alongside your other configuration files.

Then at the last we can create the argocd application
**kubectl apply -f argocd-application.yaml**


**ArgoCD will now deploy the Kube-Prometheus-Stack Helm chart with custom dashboards and alerting rules in the Kubernetes cluster. Sensitive information such as admin passwords and SMTP credentials is securely managed by using Kubernetes secrets**
**We can adjust the Helm values file and ArgoCD application manifest according to our specific requirements and configurations.**
