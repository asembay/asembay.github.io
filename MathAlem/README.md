# Сайт MathAlem For Kids для App Store Connect

Готовый статический сайт в стиле игры: фон из приложения, персонаж, кремовые карточки, зелёные кнопки и фиолетовые акценты. Страницы адаптируются к телефону, планшету и компьютеру. Использованы только существующие изображения проекта.

## Названия для публикации

- Name в App Store Connect для RU/EN/KK: **MathAlem For Kids** (17 символов).
- Подпись под иконкой и бренд внутри приложения: **MathAlem**.
- Проект Xcode: `MathAlem.xcodeproj`, схема и target: `MathAlem`.
- Bundle ID для регистрации App ID и создания карточки: **`com.asembay.mathalem`**. После загрузки первой сборки Bundle ID карточки менять нельзя. Смена идентификатора до публикации создаёт отдельную установку на устройстве; тестовые данные и PIN прежнего Bundle ID автоматически не переносятся.
- Карточка App Store Connect пока не создана: эти названия подготовлены в проекте и на сайте, но не зарезервированы в магазине.
- Для слов **For Kids** необходима категория Kids / настройка Made for Kids и соблюдение её требований, включая родительский контроль внешних ссылок и покупок. После одобрения Made for Kids эту настройку нельзя убрать. Источники: [App Review Guidelines 1.3 и 2.3.8](https://developer.apple.com/app-store/review/guidelines/), [App Information](https://developer.apple.com/help/app-store-connect/reference/app-information/app-information/).

## Страницы

| Назначение | Русский | English | Қазақша |
| --- | --- | --- | --- |
| Главная / Marketing URL | `index.html` | `en/index.html` | `kk/index.html` |
| Поддержка / Support URL | `support.html` | `en/support.html` | `kk/support.html` |
| Политика / Privacy Policy URL | `privacy-policy.html` | `en/privacy-policy.html` | `kk/privacy-policy.html` |
| Условия использования | `terms.html` | `en/terms.html` | `kk/terms.html` |

Контакт поддержки, подтверждённый владельцем: **yekaterina.kim90@gmail.com**. Кнопка открывает почтовое приложение; сайт сам не отправляет письма.

## Публикация через GitHub Pages

Сайт размещается в репозитории `asembay/asembay.github.io`, ветка `main`, папка `MathAlem/`. В App Store Connect вставляются HTTPS-ссылки, а не HTML-файлы.

| Поле App Store Connect | Русский URL |
| --- | --- |
| Marketing URL | https://asembay.github.io/MathAlem/ |
| Support URL | https://asembay.github.io/MathAlem/support.html |
| Privacy Policy URL | https://asembay.github.io/MathAlem/privacy-policy.html |

Для английской локализации добавьте `en/` перед именем файла, для казахской — `kk/`. Например: https://asembay.github.io/MathAlem/en/support.html.

Условия использования: https://asembay.github.io/MathAlem/terms.html. Эта страница не является настроенной Custom EULA в App Store Connect.

Политика должна быть доступна также внутри приложения. После публикации добавьте её окончательный URL в «О программе»; размещение сайта само по себе код приложения не меняет.

## Изменения и локальная проверка

Название магазина, подпись приложения, контакт и дата политики находятся в `docs/site-config.json`. Тексты всех трёх языков — в `Scripts/build-store-site.py`, оформление — в `docs/assets/site.css`. После редактирования текстов или настроек выполнить из корня проекта:

```sh
python3 Scripts/build-store-site.py
python3 -m http.server 8765 --bind 127.0.0.1 --directory docs
```

Затем открыть `http://127.0.0.1:8765/`. Первая команда создаёт 12 HTML-страниц; JavaScript, сборщик и установка библиотек не нужны. При публикации сохранять всю структуру `docs/`, включая `assets/`, `en/`, `kk/` и `.nojekyll`.

Политика описывает текущие функции, проверенные в коде: локальный прогресс, Keychain для PIN, выбранные изображения наград, CSV-экспорт по действию родителя, возможные системные резервные копии Apple, обращения по email и техническую обработку запросов хостингом GitHub Pages. В игре сейчас нет рекламы, обязательного аккаунта, сторонней аналитики и реализованной платной подписки. При добавлении подписки, сервера или SDK обновить документы до публикации новой версии.

Этот комплект подготовлен локально; он не опубликован на GitHub Pages и не отправлен в App Store Connect.
