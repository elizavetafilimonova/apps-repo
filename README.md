# apps-repo
манифесты приложений (в рамках ТЗ — podinfo) 

Структура:  
podinfo - манифесты podinfo  
kustomization.yaml - откуда брать ресурсы  
  
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

10. **Поломка:**
Я создала новый патч, куда вписала неверный образ. Запушила. Flux начал создавать новую реплику, удалив старую и не смог этого сделать.
<img width="823" height="151" alt="image" src="https://github.com/user-attachments/assets/65aba37d-e98c-4e66-a5a0-7fddb7569d0d" />  
<img width="662" height="135" alt="image" src="https://github.com/user-attachments/assets/cfcf2110-befb-435d-ac64-7660a07113a3" />

В events нашли причину.  
<img width="1905" height="594" alt="image" src="https://github.com/user-attachments/assets/ffc54282-e1cf-44ed-b694-f2a221567c14" />  
Удалила патч. Проверила работоспособность.  
<img width="870" height="204" alt="image" src="https://github.com/user-attachments/assets/f222233b-38b3-4733-b78a-2758a493288f" />

