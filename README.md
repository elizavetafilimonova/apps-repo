# apps-repo
манифесты приложений (в рамках ТЗ — podinfo)  
1. **Скопированы файлы из публичного репозитория.**
2. **Создан патч affinity.yaml.**
3. **Изменен файл kustomization.yaml (включен патч).**
> patches:  
>  - path: affinity.yaml  
>    target:  
>      kind: Deployment  
5. **Проверена правильность объединения всех манифестов:**
>  kubectl kustomize .    
6. **Пушим.**  
7. **Проверка запуска на разных нодах:**  
> kubectl get pods -o wide
<img width="946" height="180" alt="image" src="https://github.com/user-attachments/assets/87856495-2378-427d-bc28-fd16045db39d" />
