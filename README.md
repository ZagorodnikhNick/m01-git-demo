# Demo / Reference Project M01

`SOLUTION BOUNDARY: FULL GIT WORKFLOW + MINIMAL WEB CONTENT`

## Назначение

Это минимальный статический проект преподавателя для демонстрации полного рабочего процесса Git, GitHub и GitHub Pages. Он нужен для проверки команд, записи video demonstrations и подготовки реальных screenshots.

Проект не является student asset и не должен выдаваться как готовое решение практики. Содержательная часть сайта намеренно минимальна: один HTML-файл и один CSS-файл без framework, JavaScript и backend.

## Состав

- `index.html` — единственная страница;
- `styles.css` — локальное оформление без внешних ресурсов;
- `.gitignore` — нейтральные правила для временных файлов среды.

Все пути относительные. Проект совместим с GitHub Pages при публикации из ветки `main` и каталога `/(root)`.

## Локальная проверка

Открыть `index.html` напрямую или запустить локальный сервер в каталоге проекта:

```bash
python3 -m http.server 8000
```

Затем открыть `http://localhost:8000/` и проверить:

- заголовок и статус «Локальная версия»;
- три карточки Local / GitHub / Pages;
- блок ожидаемого результата;
- отсутствие внешних запросов и битых ресурсов;
- адаптацию страницы при уменьшении ширины окна.

## Подготовка рабочего репозитория

Не создавайте вложенный `.git` внутри каталога Smart Course System. Скопируйте содержимое `demo_project/` в отдельную рабочую папку, например `m01-git-demo`, и выполняйте Git workflow уже там.

```bash
git --version
git init
git branch -M main
git config user.name "Преподаватель"
git config user.email "teacher@example.com"
git status
git add index.html styles.css .gitignore README.md
git commit -m "Create minimal demo site"
```

На общем компьютере используйте repository-local `user.name` и `user.email`, как в примере без `--global`.

## Минимальное изменение для feature-ветки

Для демонстрации ветки не нужно развивать сайт. Достаточно:

1. создать `feature/published-state`;
2. в `index.html` заменить видимый статус `Локальная версия` на `Публикация готова`;
3. изменить одно предложение в lead-тексте, чтобы diff содержал осмысленное изменение;
4. проверить страницу локально;
5. выполнить `status → diff → add → diff --cached → commit → push`;
6. открыть Pull Request, проверить Files changed и выполнить merge.

Это representative change только для демонстрации Git workflow, а не решение содержательной HTML/CSS-практики.

## GitHub и Pages

Действия с GitHub выполняются только в реальном преподавательском аккаунте:

1. создать пустой repository без README, `.gitignore` и license;
2. добавить HTTPS remote и проверить `git remote -v`;
3. выполнить `git push -u origin main` через поддерживаемый browser credential flow;
4. провести feature-ветку через Pull Request и merge;
5. выбрать Pages source: `main` + `/(root)`;
6. дождаться публичного URL и проверить страницу.

Не имитировать успешный push, merge или Pages deployment. После работы на общем компьютере выйти из GitHub в браузере и удалить сохранённые Git credentials, если они были сохранены.

## Screenshot states

Точные состояния, кадрирование, имена файлов и точки вставки определены в соседнем `../visual_plan.md`.
