# Chat Assistant AI

Корпоративный AI-ассистент на Spring Boot с RAG.

## Технологии
- Spring Boot 3.4.3
- Spring AI
- PostgreSQL + pgvector
- Ollama (qwen2.5:3b, nomic-embed-text)

## Запуск
```bash
# Запустить контейнеры
docker-compose up -d

# Скачать модели
docker exec -it ai_ollama ollama pull qwen2.5:3b
docker exec -it ai_ollama ollama pull nomic-embed-text

# Запустить приложение
mvn spring-boot:run
