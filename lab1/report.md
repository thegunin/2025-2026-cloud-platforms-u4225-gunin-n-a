# Отчет по лабораторной №1

University: [ITMO University](https://itmo.ru/ru/)  
Faculty: FTMI  
Course: [introduction-in-web-tech](https://itmo-ict-faculty.github.io/introduction-in-web-tech)  
Year: 2025/2026  
Group: U4225  
Author: Gunin Nikita Alekseevich  
Lab: Lab1  
Date of create: 01.12.2025  
Date of finished: 01.12.2025

---

## Ход работы

### Шаг 1. Открытие IAM и проверка доступа
Сначала был получен доступ к Google Cloud и открыт раздел IAM.

![lab1_step1_iam_dashboard.png](screenshots/lab1_step1_iam_dashboard.png)

---

### Шаг 2. Создание Service Account с ролью Storage Admin
Был создан сервисный аккаунт `ngunin-sa-lab1` и присвоена роль **Storage Admin**.

![lab1_step2_service_account.png](screenshots/lab1_step2_service_account.png)

---

### Шаг 3. Переход на страницу VM Instances
Открыта панель Compute Engine → VM Instances.

![lab1_step3_vm_page.png](screenshots/lab1_step3_vm_page.png)

---

### Шаг 4. Создание виртуальной машины (VM)
Создана минимальная VM типа **e2-micro** в режиме **Spot**.

![lab1_step4_vm_created.png](screenshots/lab1_step4_vm_created.png)

---

### Шаг 5. Подключение к VM по SSH
Подключение выполнено через SSH-in-browser.

![lab1_step5_vm_ssh_connected.png](screenshots/lab1_step5_vm_ssh_connected.png)

---

### Шаг 6. Копирование файлов из Google Cloud Storage
Проверена версия gsutil, найден бакет `lab1-bucket-itmo`, создан каталог `~/lab1`, файлы успешно скопированы на VM, проверено их наличие.

![lab1_step5_gsutil_copy.png](screenshots/lab1_step5_gsutil_copy.png)

---

### Шаг 7. Изменение роли сервисного аккаунта и повторная проверка
Роль сервисного аккаунта изменена со **Storage Admin** на **Compute Viewer**, что привело к ожидаемой ошибке доступа при повторной попытке копирования.

![lab1_step7_change_role_compute_viewer.png](screenshots/lab1_step7_change_role_compute_viewer.png)

---

## Результаты лабораторной работы

В ходе выполнения лабораторной работы были выполнены следующие действия:

1. Получен доступ к Google Cloud и открыт IAM.  
2. Создан сервисный аккаунт с корректным неймингом.  
3. Создана минимальная виртуальная машина e2-micro в Spot-режиме.  
4. Выполнено SSH-подключение к VM.  
5. С помощью gsutil скопированы файлы из бакета на виртуальную машину.  
6. После изменения роли на Compute Viewer доступ к объектам был корректно закрыт, что подтверждается ошибкой 403.  
7. Все созданные ресурсы были удалены.  

Все пункты работы выполнены, скриншоты приложены.