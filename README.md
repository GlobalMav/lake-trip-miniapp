# Закупки на озеро — Firebase mini app

Статическое приложение для общей таблицы закупок: редактирование строк, добавление строк и итог по цене.

## 1. Вставить Firebase config

Откройте `index.html` и замените пустой объект `firebaseConfig` на конфиг из Firebase Console:

Firebase Console → Project settings → General → Your apps → Web app → SDK setup and configuration → Config.

Важно: `databaseURL` для текущей базы:

```js
"https://poezdkatatavuty228-default-rtdb.firebaseio.com"
```

## 2. Правила Realtime Database

Firebase Console → Realtime Database → Rules:

```json
{
  "rules": {
    "lakeTrip": {
      ".read": true,
      ".write": true
    }
  }
}
```

Такой режим удобен для поездки без логина, но любой человек со ссылкой сможет менять данные.

## 3. Деплой через Firebase Hosting

Установите Firebase CLI, если он еще не установлен:

```bash
npm install -g firebase-tools
```

Войдите в аккаунт:

```bash
firebase login
```

Из папки проекта выполните:

```bash
firebase deploy --only hosting
```

После деплоя Firebase покажет Hosting URL.

## Если запускаете `firebase init hosting`

- Use an existing project: `poezdkatatavuty228`
- Public directory: `.`
- Configure as a single-page app: `Yes`
- Overwrite `index.html`: `No`
- Set up automatic builds and deploys with GitHub: по желанию
