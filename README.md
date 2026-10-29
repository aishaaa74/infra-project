# Infra project

Учебный инфраструктурный репозиторий курса 

Задачи для выпонения и практики Git, docker, ansible

## Запуск в Docker

Сборка образа:
\`\`\`bash
docker build -t infra-web:1.0 docker/
\`\`\`

Запуск контейнера:
\`\`\`bash
docker run -d --name infra-web -p 8080:80 infra-web:1.0
\`\`\`

Проверка:
\`\`\`bash
curl http://localhost:8080
\`\`\`