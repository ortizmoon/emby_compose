### Небольшой `compose` для запуска медиасервера Emby, и прокси для него, в `docker`.<br>
---
Режим сети выбран `host`, для минимизации слоев абстракции, и корректной работы `DLNA`.<br>

Тег `latest`, прописан для быстрого передеплоя, в случае выхода новой версии сервера.<br>

Предварительно требуется настроить монтирование разделов с контентом.<br>
(фильмами, сериалами и тд), после чего указать их в `compose` для мапинга.<br>

Желательно поменять в настройках папку кэша на `/cache`, из проекта.<br>
А совсем идеально, примонтировать в нее раздел от ssd, благодаря этому скорость декодинга повысится.<br>

Декодирование по-умолчанию, через CPU. Для настройки декодирования по GPU,<br>
нужно установить дрова для видеокарты, и раскомментировать `runtime` в `compose`.<br>

Порт в прокси, по-умолчанию, `80`. В зависимости от предпочтений, можно сменить на любой другой.<br>

---



#### Запуск
```bash
docker compose up -d
```

#### Обновление сервера
```bash
docker compose pull && docker compose up -d
```

#### Глянуть логи можно стандартно
```bash
docker logs embyserver
```
<br>

<div align="center">

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Nginx](https://img.shields.io/badge/nginx-009C28?style=for-the-badge&logo=nginx&logoColor=white)](http://nginx.org/)
[![Emby](https://img.shields.io/badge/Emby-FF4F00?style=for-the-badge&logoColor=white)](https://emby.media/)

</div>
