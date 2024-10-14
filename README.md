# Домашнее задание к занятию 11 «Teamcity» Шарапат Виктор

## Подготовка к выполнению

1. В Yandex Cloud создайте новый инстанс (4CPU4RAM) на основе образа `jetbrains/teamcity-server`.
2. Дождитесь запуска teamcity, выполните первоначальную настройку.
3. Создайте ещё один инстанс (2CPU4RAM) на основе образа `jetbrains/teamcity-agent`. Пропишите к нему переменную окружения `SERVER_URL: "http://<teamcity_url>:8111"`.
4. Авторизуйте агент.
5. Сделайте fork [репозитория](https://github.com/aragastmatb/example-teamcity).
6. Создайте VM (2CPU4RAM) и запустите [playbook](./infrastructure).

## Основная часть

1. Создайте новый проект в teamcity на основе fork.
2. Сделайте autodetect конфигурации.
3. Сохраните необходимые шаги, запустите первую сборку master.
4. Поменяйте условия сборки: если сборка по ветке `master`, то должен происходит `mvn clean deploy`, иначе `mvn clean test`.
5. Для deploy будет необходимо загрузить [settings.xml](./teamcity/settings.xml) в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
6. В pom.xml необходимо поменять ссылки на репозиторий и nexus.
7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.
8. Мигрируйте `build configuration` в репозиторий.
9. Создайте отдельную ветку `feature/add_reply` в репозитории.
10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово `hunter`.
11. Дополните тест для нового метода на поиск слова `hunter` в новой реплике.
12. Сделайте push всех изменений в новую ветку репозитория.
13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.
14. Внесите изменения из произвольной ветки `feature/add_reply` в `master` через `Merge`.
15. Убедитесь, что нет собранного артефакта в сборке по ветке `master`.
16. Настройте конфигурацию так, чтобы она собирала `.jar` в артефакты сборки.
17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.
18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.
19. В ответе пришлите ссылку на репозиторий.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---

### Решение

## Подготовка к выполнению

В Yandex Cloud создал три ВМ:

* teamcity-server
* teamcity-agent
* nexus (развернул через playbook, исправил ошибку в нем).

![Screenshot_1](https://github.com/user-attachments/assets/a9a2cb1f-9a25-4ca3-add4-b3938037611d)

![Screenshot_3](https://github.com/user-attachments/assets/39306b9f-523c-4335-9ace-6405e24a4238)


![Screenshot_4](https://github.com/user-attachments/assets/c93d9569-84ac-4643-9462-42bc4dde7d02)

![Screenshot_5](https://github.com/user-attachments/assets/d5c1ed11-b337-4c3c-9447-1efd9f5789ae)

![Screenshot_10](https://github.com/user-attachments/assets/a79b6497-c1b0-49b6-944a-8224e166bd62)

Сделайте fork 

![image](https://github.com/user-attachments/assets/e87ac7b2-419e-480f-bf27-2cc1adb0bd02)


Авторизовал агента

![image](https://github.com/user-attachments/assets/db9b3749-86bf-4ace-a6a5-a4f0ef29c23e)


## Основная часть

Создайте новый проект на основе fork, сделал autodetect, загрузить конфиг, внес изменения для подключения к nexus.
В pom.xml поменял ссылки на репозиторий и nexus.

![image](https://github.com/user-attachments/assets/e0c67439-fc08-4b5d-9842-84867e3b1187)

![image](https://github.com/user-attachments/assets/d62afc5e-4fc7-4f8f-b74f-389dcd39cf37)

![image](https://github.com/user-attachments/assets/633ec1ab-fb6e-4818-9b45-f7cba9008587)

![image](https://github.com/user-attachments/assets/c8180673-ffab-4bce-8157-e26e4b6a8ecc)

![image](https://github.com/user-attachments/assets/798c74a6-d2fd-4a3c-9d07-3bba8c635cbf)

![image](https://github.com/user-attachments/assets/4230d321-e3d0-4750-8d5f-6da7219891aa)

![image](https://github.com/user-attachments/assets/626ba95d-315a-4a9a-a86d-cf9e710d4bef)

![image](https://github.com/user-attachments/assets/b2474bd5-472a-4647-934c-835ca2e3214f)

![image](https://github.com/user-attachments/assets/ac33ea98-6f6f-4265-9e04-5f716e0b829a)

![image](https://github.com/user-attachments/assets/c7ca9950-3e12-4653-a113-a19c63b085f9)

Создал отдельную ветку `feature/add_reply` в репозитории. Внес новый метод для класса Welcomer, дополните тест для нового метода на поиск слова `hunter` в новой реплике.
Внес изменения из произвольной ветки `feature/add_reply` в `master` через `Merge`. Настроил конфигурацию так, чтобы она собирала `.jar` в артефакты сборки.

![image](https://github.com/user-attachments/assets/b4723aa4-b5eb-454d-9e05-31b9fdf08f87)

![image](https://github.com/user-attachments/assets/7bc94548-6098-4196-8b45-68bffdfc493c)

![image](https://github.com/user-attachments/assets/e3506950-449a-4d22-a462-a7e8710d2a39)

![image](https://github.com/user-attachments/assets/30d8cf86-c93c-4689-8511-edcfed78f5f9)

![image](https://github.com/user-attachments/assets/2ccb0b8f-4f87-4378-9314-098f91642642)

![image](https://github.com/user-attachments/assets/06114998-b56c-4b94-9cb7-531b9b46ceb2)

![image](https://github.com/user-attachments/assets/3d3abbc8-288e-445d-8360-b01ebb58bea8)

![image](https://github.com/user-attachments/assets/4481414c-9394-4ac7-8a38-070b0b52cfd9)

![image](https://github.com/user-attachments/assets/c6a7319f-158f-46ed-81d9-d202dc5d9d2d)

