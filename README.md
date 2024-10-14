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


Авторизуйте агент
![image](https://github.com/user-attachments/assets/db9b3749-86bf-4ace-a6a5-a4f0ef29c23e)


## Основная часть


![image](https://github.com/user-attachments/assets/e0c67439-fc08-4b5d-9842-84867e3b1187)








