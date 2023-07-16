В этом репозитории находится пример приложения с тестами:

- [e2e тесты](e2e/example.spec.ts)
- [unit тесты](src/example.test.tsx)

Для запуска примеров необходимо установить [NodeJS](https://nodejs.org/en/download/) 16 или выше.

Как запустить:

```sh
# установить зависимости
npm ci

# запустить приложение
npm start
```

Как запустить e2e тесты:

```sh
# скачать браузеры
npx playwright install

# запустить тесты
npm run e2e
```

Как запустить модульные тесты:

```sh
npm test
```

ВЫПОЛНЕНИЕ ДЗ:
1. Настройка линтера для соответствия сообщений о коммитах формату conventional commits

   (cделана при помощи commitlint и husky)


    feat: wip - верно
    
    аsdasd - неверно
    
Попробуйте закомитить двумя разными способами для проверки работы. 

2. Автоматический запуск проверок в CI для пулл реквестов
 Запускаются e2e тесты + модульные тесты + линтер - [quality.yml](/.github/workflows/quality.yml)

    [Pr со сломанными тестами (ограничен для мержа)](https://github.com/illicit-oblivion/unit-demo-cra/pull/63)

    [Pr, где все проверки пройдены](https://github.com/illicit-oblivion/unit-demo-cra/pull/65)

3. Релизный процесс
   [release.yml](/.github/workflows/release.yml)

- Создается запись в реестре релиза - issue
- Запускается [quality.yml](/.github/workflows/quality.yml)
- Если шаг 1 и 2 успешны -происходит deploy на gh pages
- Если шаг deploy успешен - происходит обновление записи в реестре релизов
- Закрытие issue

Создать пару тестовых комитов
```sh
 # создать тег и запушить
 git tag v107 && git push origin --tags
```
[пример записи в реестре](https://github.com/illicit-oblivion/unit-demo-cra/issues/66)
