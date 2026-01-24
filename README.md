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
