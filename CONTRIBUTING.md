## Коммиты

> [Conventional commits](https://www.conventionalcommits.org/en)

#### Конвенция
```clj
тип(скоуп): описание
```
```clj
тип: описание
```

Тип коммита классифицирует характер внесённых изменений. Ограничивает поведение разработчика в рамках одного коммита: например, нельзя одновременно пофиксить баг `fix` и добавить новую фичу `feat`.

Скоуп описывает область проекта, затронутую коммитом. При наличии ограничивает поведение разработчика в рамках одного коммита: например, нельзя одновременно добавить код в несвязанные (не поддающиеся обобщению) скоупы `persistence` (DAL) и `api` (HTTP контроллеры). Где это возможно, предпочтение отдаётся абстрактной продуктовой терминологии, а не конкретной технической: `users` вместо `UserUpdateCommand`, `configuration` вместо `app settings`. Сокращения не приветствуются: `localization` вместо `local`, `configuration` вместо `config`. Допускается отсутствие скоупа. Соблюдение единого нейминга в рамках одного репозитория необходимо.

Описание — короткое и ёмкое, в настоящем времени. Допускаются перечисления: `add ru-RU and en-US locales`, `fix memory leak by migrating to NewtonsoftJSON`, `describe services and DTOs`. Английский язык — везде, где возможно.

#### Типы коммитов
- `feat` — добавление новой функциональности, влияющее на взаимодействие клиента с сервисом (триггерит minor релиз)
- `fix` — изменение логики работы кода для устранения бага/ошибки, влияющее на взаимодействие клиента с сервисом (триггерит patch релиз)
- `perf` — оптимизация потребления ресурсов (триггерит patch релиз)
- `refactor` — рефакторинг, изменения формы кода, не влияющие на логику его работы
- `chore` — регулярная поддержка кодовой базы с точки зрения окружения и инфраструктуры (например, обновление библиотек, изменение процесса сборки), не затрагивающая кодовую базу самого сервиса и тестов
- `test` — покрытие тестами или их исправление без внесения изменений в кодовую базу самого сервиса
- `ci` — изменение конфигураций CI/CD
- `revert` — откат коммита (см. [git revert](https://git-scm.com/docs/git-revert))

Использование других типов не допускается.

#### Примеры
```clj
feat(users): add registration use-case
```
```clj
fix(configuration): replace KAFKA_BOOTSTRAP_HOST with KAFKA_BOOTSTRAP_SERVER
```
```clj
fix(parsing): eliminate JSON parser memory leak
```
```clj
refactor(persistence): replace data annotations with separate entity configuration classes
```
```clj
refactor(api): decorate controllers with OpenAPI documentation
```
```clj
refactor: apply Microsoft code style guidelines
```
```clj
chore(dependencies): update NuGet packages to the latest versions
```
```clj
revert: replace data annotations with separate entity configuration classes
```
