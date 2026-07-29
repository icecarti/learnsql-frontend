# LearnSQL Frontend

Новая клиентская часть образовательной платформы LearnSQL.

LearnSQL используется для практического изучения SQL. Пользователи проходят курсы, выполняют задания и получают результаты автоматической проверки запросов. Платформа применяется в учебном процессе Университета ИТМО.

## Основные возможности

- регистрация, вход и авторизация через внешних провайдеров
- защищенные маршруты и автоматическое обновление токена
- просмотр и редактирование профиля пользователя
- учебная статистика, прогресс по курсам и результаты по темам
- прохождение курсов и выполнение SQL-заданий
- SQL-редактор с подсветкой синтаксиса
- отображение схемы базы данных
- чаты через REST API и WebSocket
- светлая, темная и системная темы
- адаптация интерфейса под мобильные устройства

## Технологии

- Vue 3, TypeScript и Vite
- Vue Router и Pinia
- Axios и WebSocket
- Tailwind CSS и Sass
- Chart.js
- PrismJS
- JointJS

## Архитектура проекта

Приложение представляет собой одностраничный клиент на Vue 3.

```text
src/
├── api/          # настройка HTTP-клиента
├── assets/       # стили и статические ресурсы
├── components/   # переиспользуемые компоненты
├── composables/  # общая логика Vue
├── router/       # маршруты приложения
├── services/     # работа с API и авторизацией
├── stores/       # состояние приложения
├── types/        # TypeScript-типы
└── views/        # страницы приложения
```

Данные загружаются через REST API, а сообщения в чатах передаются через WebSocket. Состояние приложения управляется с помощью Pinia. Доступ к персональным разделам контролируется защищенными маршрутами Vue Router.

## Требования

- Node.js `20.19+` или `22.12+`

## Запуск проекта

```bash
git clone --branch new_frontend --single-branch https://github.com/icecarti/learnsql-frontend.git
cd learnsql-frontend
npm ci
```

Создайте файл `.env.local`:

```env
VITE_BACKEND_API_URL=http://localhost:8000
```

Дополнительные переменные для внешней авторизации:

```env
VITE_GOOGLE_CLIENT_ID=
VITE_YANDEX_CLIENT_ID=
VITE_YANDEX_REDIRECT_URI=http://localhost:5173/auth/callback/yandex
VITE_GITHUB_CLIENT_ID=
```

Запустите проект:

```bash
npm run dev
```

## Сборка

```bash
npm run type-check
npm run build
npm run preview
```
