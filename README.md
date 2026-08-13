# Автозонд — юридические страницы

Публичный хостинг документов приложения «Автозонд» (Android, диагностика авто по OBD-II):
политика конфиденциальности (RU/EN) и страница удаления аккаунта и данных. Раздаётся GitHub Pages —
эти URL указаны в Google Play Console и зашиты в приложение.

| Страница | URL |
|---|---|
| Политика конфиденциальности (RU) | https://romanchetverikov.github.io/autozond-legal/privacy-ru.html |
| Privacy policy (EN) | https://romanchetverikov.github.io/autozond-legal/privacy-en.html |
| Удаление аккаунта и данных | https://romanchetverikov.github.io/autozond-legal/data-deletion.html |

## Как обновлять

Источник правды — приватный репозиторий приложения, каталог `store/`. Правится там, затем файлы
копируются сюда и пушатся:

```bash
cp ../Obd2Codes/store/{privacy-ru,privacy-en,data-deletion}.html .
git commit -am "обновить политику" && git push
```

Публикация — минута после пуша. Даты вступления в силу указаны внутри страниц; при смысловых
правках дату надо поднимать.

## Почему отдельный репозиторий

Репозиторий приложения приватный, а GitHub Pages из приватного репозитория требует платного плана.
Хостинг на Supabase, который был в первоначальном плане, не подходит: платформа принудительно
отдаёт любой HTML как `text/plain` с `nosniff` — и из Storage, и из Edge Function — так что в
браузере страница выглядела бы исходным кодом.
