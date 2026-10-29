Отчет по выполнению midterm’а
Задание 1.3. Просмотр изменений
Выполнено:
git diff
Вывод:
-<!-- Допишите сюда -->
+Задача для выпонения и практики Git, docker, ansible
После git add второй git diff пустой, потому что изминения из рабочей папки переносятся в индекс и рабочая папка и индекс становятся идентичны, разницы между ними нет  

Задание 2.1. История коммитов
 1- команда: git log --oneline
077f64d (HEAD -> main, origin/main) update README description / git diff
767650d ansible/
bce3cad add docker/
3dccb49 add README.md and .env.example
416e544 add gitignore
 2 - команда: git log --oneline --graph --all
* 077f64d (HEAD -> main, origin/main) update README description / git diff
* 767650d ansible/
* bce3cad add docker/
* 3dccb49 add README.md and .env.example
* 416e544 add gitignore
3 - команда: git show HEAD~1
commit 767650d1f77bb95d6ced9014331e463b0c18ea69
Author: Айша Табалдиева <tbldva05@gmail.com>
Date:   Thu Oct 29 13:31:07 2026 +0600

    ansible/

diff --git a/ansible/ansible.cfg b/ansible/ansible.cfg
new file mode 100644
index 0000000..4dd424d
--- /dev/null
+++ b/ansible/ansible.cfg
@@ -0,0 +1,3 @@
+[defaults]
:

Задание 2.2. Ветка и слияние
git merge feature/healthcheck
Updating 077f64d..156c765
Fast-forward
 docker/Dockerfile | 1 +
 1 file changed, 1 insertion(+)
 Создана ветка feature/healthcheck, добавлена строка HEALTHCHECK в Dockerfile, слияние выполнено fast-forward, ветка удалена
 
 Задание 2.3. Конфликт слияния
 <<<<<<< HEAD
app_port: 8000
=======
app_port: 9090
>>>>>>> fix/app-port

Задание 3.1. Получение изменений с сервера
 git log --oneline
d2ff905 (HEAD -> main, origin/main, origin/HEAD) Merge branch 'main' of github.com:aishaaa74/infra-project
a1f9762 update README

Задание 3.2. Merge Request
https://github.com/aishaaa74/infra-project/pull/1

PS C:\Users\Admin\infra-project> git pull
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (1/1), 903 bytes | 225.00 KiB/s, done.
From github.com:aishaaa74/infra-project
   d2ff905..72299b4  main       -> origin/main
Updating d2ff905..72299b4
Fast-forward
 ansible/playbook.yml | 5 +++++
 1 file changed, 5 insertions(+)

 
