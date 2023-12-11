# <center>Minimum Viable Product (MVP) за допомогою ArgoCD</center>  

1. В AgroCD додаємо додаток (+ NEW APP)  
 ## <center>В новому вікні заповнюємо поля General</center>  
    - Application Name (Потрібне ім`я додатку)  
    - Project Name (default)  
    - Активуємо AUTO-CREATE NAMESPACE  
    
## <center>В блоці SOURCE</center>  
    - Repository URL (посилання на репозиторій)  
    - Revision (HEAD)  
    - Path (helm)  

## <center>В блоці  DESTINATION</center> 
    - Cluster URL (https://kubernetes.default.svc/)  
    - Namespace (Потрібне ім`я)  

2. Та натискаємо "Create"

![Відео](images/4.6.gif)


