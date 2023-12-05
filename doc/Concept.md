Давайте порівняємо кілька інструментів розгортання Kubernetes кластерів в локальному середовищі. Minikube, Kind та K3d.
Minikube

- Minikube - це локальна система Kubernetes, яка дозволяє розгортати кластер Kubernetes на одному комп'ютері. Вона призначена для локальної розробки та тестування.

- Kind - інструмент для створення локальних Kubernetes кластерів в Docker контейнерах. Дозволяє тестувати Kubernetes локально.

- K3d - інструмент для створення локальних Kubernetes кластерів в Docker контейнерах, використовуючи Rancher Kubernetes Engine (RKE). Швидко створює та тестує кластери Kubernetes у Docker-контейнерах.

# <center>Характеристики</center>

| Характеристика               | Minikube                                                | Kind (Kubernetes IN Docker)                             | K3d                                                     |
|------------------------------|---------------------------------------------------------|--------------------------------------------------------|---------------------------------------------------------|
| **Підтримувані ОС та архітектури** | Різні ОС, включаючи Windows, macOS та Linux             | Зручний для використання на різних платформах           | Різні ОС, включаючи Windows, macOS та Linux               |
| **Можливість автоматизації**    | Має CLI для автоматизації                                | Простий CLI для автоматизації                           | CLI для автоматизації                                      |
| **Додаткові функції**           | Має вбудовані додаткові функції для легкої роботи з Kubernetes | Дозволяє легко тестувати Kubernetes у Docker           | Використовує RKE для створення кластеру в Docker, швидке розгортання |
| **Переваги** | Легкий у використанні, швидке розгортання, активна спільнота | Швидке створення та використання у Docker, простий у використанні | Швидке розгортання, легко інтегрується з Docker |
| **Недоліки** | Може бути обмежений в масштабуванні для великих проектів | Може вимагати додаткової конфігурації для складних сценаріїв | Може бути менш стабільним порівняно з іншими інструментами |

# <center>Демонстрація:</center>

### <center>Minikube:</center>
- Розгортання кластеру  
minikube start

- Демонстрація застосунку "Hello World"

kubectl create deployment hello-world --image=gcr.io/google-samples/hello-app:1.0  
kubectl expose deployment hello-world --type=NodePort --port=8080  
minikube service hello-world  
### <center>Kind (Kubernetes IN Docker):</center>  
- Розгортання кластеру  
kind create cluster

- Демонстрація застосунку "Hello World"  
kubectl create deployment hello-world --image=gcr.io/google-samples/hello-app:1.0  
kubectl expose deployment hello-world --type=NodePort --port=8080  
kubectl port-forward service/hello-world 8080:8080  
### <center>K3d</center>   
- Розгортання кластеру  
k3d create cluster

- Демонстрація застосунку "Hello World"  
kubectl create deployment hello-world --image=gcr.io/google-samples/hello-app:1.0  
kubectl expose deployment hello-world --type=NodePort --port=8080  
kubectl port-forward service/hello-world 8080:8080  
# <center>Висновки:</center>  
Після оцінки характеристик та демонстрації, для стартапу "AsciiArtify" може бути вигідніше використовувати Minikube, оскільки він легкий у використанні, має швидке розгортання та активну спільноту. Це особливо важливо для команди без досвіду у DevOps, оскільки Minikube дозволяє швидко отримати локальний Kubernetes класт


