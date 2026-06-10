# Поездка на озеро — mini app

Статическое приложение для GitHub Pages: редактируемая таблица закупок, мобильный карточный интерфейс, итог по цене и синхронизация через Firebase Realtime Database.

## Как включить общий режим

В `index.html` найди блок `firebaseConfig` и вставь полный конфиг из Firebase:

Firebase → Project settings → General → Your apps → Web app → SDK setup and configuration → Config.

Минимально важны поля:

- `apiKey`
- `databaseURL`
- `projectId`

В проекте уже подставлен `databaseURL` для `poezdkatatavuty228`, но `apiKey` нужно взять из Firebase Web App config.

## Правила Realtime Database для общего редактирования

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

Такой режим открыт для всех, у кого есть ссылка. Для поездки это удобно, но для публичного долгого проекта правила лучше закрыть.

## Деплой на GitHub Pages

Загрузи в корень репозитория:

- `index.html`
- `README.md`
- `.nojekyll`

Затем: Settings → Pages → Deploy from a branch → main → /root.
