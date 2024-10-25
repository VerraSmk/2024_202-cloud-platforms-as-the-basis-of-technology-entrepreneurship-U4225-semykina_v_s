University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Cloud platforms as the basis of technology entrepreneurship](https://) ADD link
Year: 2024/2025
Group: U4225
Author: Semykina Vera Stanislavovna
Lab: Lab1
Date of create: 25.10.2024
Date of finished: 25.10.2024

# Лабораторная работа 1 - Обзор Google Cloud и исследование ключевых сервисов
## Цель
Познакомиться с основными возможностями и преимуществами платформы Google Cloud.
## Отчет по ходу работы
1. **Создание служебной учетной записи**
    * Перейдем на вкладку IAM и создайте служебную учетную запись с ролью `Storage Admin`;
    * Имя: `vsemykina-sa-lab1`.
      ![image](https://github.com/user-attachments/assets/2b9cdb3a-52fc-4e36-a366-30a667db5dc0)
2. **Создание виртуальной Машины**
    * Создадим минимальную вычислительную машину (VM) с типом машины e2-micro в режиме спот;
    * Имя: `vsemykina-vm-lab1`.
    * Конфигурация машины: 
           * `"Series": "E2"`,
            * `"Machine type": "e2-micro"`,
            *  `"Availability policies": "Spot"`.
      ![image](https://github.com/user-attachments/assets/921aef77-453a-404b-8566-55fc13a5a7c9)
3. **Копирование файлов из бакета**
    * Используем инструмент `gsutil`, чтобы найти бакет `lab1-bucket-itmo` и скопировать 3 файла в локальную папку на VM. Используйте `ls` `-lah`, чтобы отобразить скопированные файлы.
   ![image](https://github.com/user-attachments/assets/4d349772-0126-406a-8815-5c9b5bbacc47)

4. **Изменение прав доступа**
    * Изменим роль служебной учетной записи с `Storage Admin` на `Compute Viewer` и попробуем повторить шаг с копированием данных. Делаем выводы из результатов.
      Изменила роль служебной учетной записи на Compute Viewer и попыталась снова скопировать файлы
      Попробовала выполнить ту же команду, но получил ошибку AccessDeniedException (403).
         ![image](https://github.com/user-attachments/assets/f2872d10-c9b3-4715-8c9d-2355d12f0038)
# **Выводы** 
Изменение роли на Compute Viewer лишило доступа к бакету, что подтвердило важность разрешений IAM. Тем не менее, я все еще мог управлять VM, что подчеркивает гранулярность ролей IAM.

5. **Очистка**
    * Удаляем все созданные сервисы и пишем отчет со скриншотами.
