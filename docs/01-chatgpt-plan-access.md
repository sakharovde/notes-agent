# Шаг 1. Подключить модели из подписки ChatGPT

Цель первого прототипа Notes Agent на Node.js и TypeScript — подтвердить, что приложение может получить ответ от модели в рамках плана ChatGPT пользователя. Доступ для Notes Agent ещё предстоит проверить.

1. Реализовать вход в браузере через Sign in with ChatGPT. Проверить применимость программы для open-source-приложений и использовать собственную регистрацию OAuth с PKCE. Пользователь разрешает приложению использовать лимит своего плана.
2. С выданным OAuth access token запросить доступные аккаунту модели через `GET https://api.openai.com/v1/models`.
3. Выбрать модель из полученного списка и отправить тестовый запрос через `POST https://api.openai.com/v1/responses` с `stream: true` и `store: false`. Успех подтверждает событие `response.completed`.

Для первого запроса используем нейтральный текст. OAuth-токены храним вне Git. Агентский цикл, инструменты заметок и эмбеддинги добавим после проверки доступа.

[Регистрация и вход](https://developers.openai.com/siwc/token-sharing-open-source/sign-in) · [Список моделей и вызов Responses API](https://developers.openai.com/siwc/token-sharing-open-source/models-and-inference)
