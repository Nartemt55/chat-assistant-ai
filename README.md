# Chat Assistant AI

Корпоративный AI-ассистент на Spring Boot

## Технологии

- Spring Boot 3.4.3
- Spring AI
- PostgreSQL + pgvector
- Ollama (qwen2.5:3b, nomic-embed-text)
- Docker Compose

## Требования

- Docker Desktop
- Java 21
- Maven

## Старт

### 1. Клонируйте репозиторий

```bash
git clone https://github.com/Nartemt55/chat-assistant-ai.git
cd chat-assistant-ai
```

### 2. Настройка конфигурации

Скопируйте файл-шаблон:

```bash
cp src/main/resources/application-template.yml src/main/resources/application.yml
```

Отредактируйте `application.yml`, заменив `YOUR_PASSWORD_HERE` на пароль из `docker-compose.yml`:

```yaml
spring:
  datasource:
    password: tank
```

### 3. Запустите контейнеры

```bash
docker-compose up -d
```

### 4. Скачайте модели

```bash
docker exec -it ai_ollama ollama pull qwen2.5:3b
docker exec -it ai_ollama ollama pull nomic-embed-text
```

## Проверка работы

```bash
# Проверить контейнеры
docker ps

# Проверить PostgreSQL
docker exec -it ai_postgres psql -U admin -d ragdb -c "SELECT 1"

# Проверить модели Ollama
docker exec -it ai_ollama ollama list
```


