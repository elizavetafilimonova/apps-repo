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
8. **Открываем приложение через kubectl port-forward:**  
<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/dbb3b6a2-98ed-472c-9a29-a214389bb152" />
9. **Логи и диагностика:**
<img width="1722" height="218" alt="image" src="https://github.com/user-attachments/assets/858df97d-726b-48c6-93a3-fd6cb63bbb9d" />
<img width="847" height="192" alt="image" src="https://github.com/user-attachments/assets/4dec86e7-7161-431b-b842-ee0e474fb43b" />



