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

Задание 5.1. Отмена незакоммиченных изменений и правка коммита
PS C:\Users\Admin\infra-project> git restore docker/Dockerfile
git log --oneline -1
e347cda (HEAD -> main) docs: update readme

Задание 5.2. Отмена опубликованного коммита
Коммит уже отправлен на сервер, и его могли забрать другие участники (git pull). Если переписать историю (например, git reset + push --force), это создаст расхождение между локальными копиями разных людей и может привести к потере чужих изменений. git revert безопасен: он не удаляет коммит из истории, а добавляет новый коммит с противоположными изменениями — история остаётся правдивой и линейной, видно, что было сделано и что потом отменено.


1. Что такое коммит и зачем нужна область индекса (staging area)?
коммит это снимок который хранит в себе дату, автора и сообщение
2. Что такое ветка в Git?
это как цепочка которая позволяет работать над изменениями отдлельно от main
3. Что такое HEAD?
показывает последний коммит
4. Чем git fetch отличается от git pull?
git fetch скачивает изменения а git pull сразу сливает
5. Почему файл .env нельзя добавлять в репозиторий?
пароли и токены могут остаться в открытом доступе
