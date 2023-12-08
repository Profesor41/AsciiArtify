# <center>Підготовка POC для ArgoCD на minikube</center>  
 ## <center>Крок 1: Розгортання Kubernetes кластера </center>

 - Встановіть та налаштуйте minikube, використовуючи інструкції з офіційного сайту. (https://minikube.sigs.k8s.io/docs/start/)
- Запустіть minikube і переконайтеся, що кластер працює:
    - minikube start  
## <center>Крок 2: Встановлення ArgoCD </center>  

- Встановіть ArgoCD, використовуючи Helm:  
    - helm repo add argo https://argoproj.github.io/argo-helm  
    - helm install argocd argo/argo-cd  
- Зачекайте, доки всі ресурси ArgoCD будуть розгорнуті:  
    - kubectl get pods -n argocd  
- Отримайте пароль для входу в ArgoCD:  
    -kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d  
## <center>Крок 3: Доступ до графічного інтерфейсу ArgoCD </center>  

- Запустіть проксі для доступу до графічного інтерфейсу:  
    - kubectl port-forward svc/argocd-server -n argocd 8080:443
    - У браузері відкрийте http://localhost:8080 і використовуйте раніше отриманий пароль для входу.

