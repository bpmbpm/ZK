# ZK — Zettelkasten: User Manual / Руководство пользователя

---

## 🇬🇧 English Manual

### Table of Contents
1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Creating Notes](#creating-notes)
4. [Linking Notes](#linking-notes)
5. [Tags](#tags)
6. [Graph View](#graph-view)
7. [Search](#search)
8. [Backlinks](#backlinks)
9. [Outline View](#outline-view)
10. [Editor Modes](#editor-modes)
11. [Markdown Reference](#markdown-reference)
12. [GitHub Sync](#github-sync)
13. [Clear All Data](#clear-all-data)
14. [Keyboard Shortcuts](#keyboard-shortcuts)
15. [Deployment on GitHub Pages](#deployment-on-github-pages)

---

### Introduction

**ZK** is a full-featured, browser-based Zettelkasten note-taking application inspired by [Obsidian](https://obsidian.md/). It runs entirely in the browser with no backend required. Your notes are stored in `localStorage` by default and can be synced to a GitHub repository.

Key features:
- 📝 Markdown note editing with live preview
- 🔗 Wiki-style `[[wikilinks]]` between notes
- ⬡ Interactive force-directed graph view
- 🏷 Tag system with filtering
- ↩ Automatic backlinks panel
- 🔍 Full-text search
- 📋 Outline (table of contents) panel
- 🌐 English/Russian language support
- ☁ GitHub sync (for GitHub Pages owners)
- 🗑 One-click clear all data

---

### Getting Started

Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari). No installation, no server required.

**First launch:** Three sample notes are created automatically:
- **Welcome to ZK** — overview and feature list
- **ZK Guide** — keyboard shortcuts and tips
- **Markdown Reference** — markdown syntax cheat sheet

---

### Creating Notes

#### Method 1: Button
Click the **+ New Note** button in the top-left header.

#### Method 2: Keyboard Shortcut
Press **Ctrl+N** (or **⌘+N** on Mac).

#### Method 3: File Explorer
Click the **+** button next to "VAULT" in the left sidebar.

#### New Note Dialog
When creating a note, you can choose a **template**:
- **Blank** — empty note
- **Daily Note** — pre-formatted with date, tasks, journal sections
- **Meeting Note** — attendees, agenda, action items
- **Project Note** — overview, tasks, linked notes

**Example:**
1. Press `Ctrl+N`
2. Type "My First Note"
3. Select "Daily Note" template
4. Click **Create** or press `Enter`

---

### Linking Notes

ZK uses **wikilinks** — the standard Zettelkasten linking format.

#### Creating a link
Type `[[` followed by a note name, then `]]`:
```
See also [[Welcome to ZK]] for more details.
```

#### Autocomplete
While typing inside `[[...]]`, an autocomplete dropdown appears with matching note titles. Use **↑/↓** to navigate and **Enter** to select.

#### Creating a new note from a link
In preview mode, clicking a **broken link** (shown in grey) automatically creates a new note with that title.

#### Custom display text
```
[[Note Title|Custom display text]]
```

**Example note content:**
```markdown
# Project Alpha

This project relates to [[Research Notes]] and [[Meeting 2024-01-15]].

See the [[ZK Guide|full guide]] for tips.
```

---

### Tags

Add tags anywhere in a note using the `#` prefix:

```markdown
This note is about #productivity and #zettelkasten methodology.
```

#### Tag Rules
- Start with `#` followed by a letter (no spaces)
- Can contain letters, numbers, `/`, `-`, `_`
- Hierarchical tags: `#project/alpha`, `#area/work`
- Cyrillic supported: `#заметки`, `#проект`

#### Tags Panel
Click the **Tags** tab in the left sidebar to see all tags with note counts. Click a tag to filter the file explorer.

**Example:**
1. Add `#idea` to several notes
2. Click **Tags** tab in sidebar
3. Click `#idea` — the file explorer shows only those notes

---

### Graph View

The graph view visualizes connections between all your notes.

#### Opening the Graph
- Click **⬡ Graph** button in header, or
- Press **Ctrl+G**

#### Graph Elements
- 🔵 **Blue nodes** — notes
- 🟢 **Teal nodes** — tags
- 🟠 **Orange node** — currently active note
- **Lines** — connections (wikilinks or shared tags)
- **Node size** — larger = more connections

#### Interactions
| Action | Effect |
|--------|--------|
| **Click** node | Open that note |
| **Drag** node | Reposition it |
| **Drag** background | Pan the view |
| **Scroll wheel** | Zoom in/out |
| **Hover** node | Show tooltip with name and link count |
| **+/− buttons** | Zoom in/out |
| **⊡ button** | Reset zoom and position |
| **✕ Close** | Return to note editor |

**Tip:** Create several linked notes and then open the graph to see how your knowledge network looks!

---

### Search

#### Quick Search (header)
Type in the search bar at the top of the page. The left sidebar switches to the search panel showing results.

#### Full-text Search
1. Click the **Search** tab in the left sidebar
2. Type your query
3. Results show note titles and highlighted matching text

#### Quick Switcher
Press **Ctrl+P** to open the Quick Switcher. Type to filter notes by title, use **↑/↓** to navigate, **Enter** to open.

**Example searches:**
- `project alpha` — finds notes containing these words
- `#idea` — finds notes with the tag (via tag filter in sidebar)
- `meeting` — finds all meeting notes

---

### Backlinks

The **Backlinks** panel (right sidebar) shows all notes that link TO the current note.

Each backlink shows:
- The title of the linking note
- A snippet of context around the link

Click any backlink to navigate to that note.

**Example:**
- Note "Project Alpha" contains `[[Research Notes]]`
- Open "Research Notes" → the Backlinks panel shows "Project Alpha" as a backlink

---

### Outline View

Click the **Outline** tab in the right panel to see a table of contents based on the headings in the current note.

- Click any heading to scroll/jump to it
- Works in both Edit and Preview modes
- Supports H1–H4 headings

---

### Editor Modes

Three modes are available (toggle via buttons in the editor toolbar):

| Mode | Description |
|------|-------------|
| **Edit** | Raw markdown text editor |
| **Preview** | Rendered markdown output |
| **Split** | Editor and preview side by side |

**Tip:** Use **Split** mode to see changes in real time as you type.

---

### Markdown Reference

#### Text Formatting
```markdown
**Bold text**
*Italic text*
~~Strikethrough~~
`Inline code`
***Bold and italic***
```

#### Headings
```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```

#### Lists
```markdown
- Unordered item
- Another item

1. First item
2. Second item

- [ ] Unchecked task
- [x] Completed task
```

#### Links
```markdown
[[Internal Note]]
[[Note Title|Custom Text]]
[External Link](https://example.com)
```

#### Blockquote
```markdown
> This is a blockquote
```

#### Code Block
````markdown
```javascript
const x = 42;
console.log(x);
```
````

#### Table
```markdown
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |
```

#### Images
```markdown
![Alt text](https://example.com/image.png)
```

---

### GitHub Sync

ZK can save and load notes from a GitHub repository, enabling persistent storage for GitHub Pages deployments.

#### Setup
1. Create a **Personal Access Token** in GitHub:
   - Go to GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens
   - Grant **Contents: Read and Write** permission for your repository
2. Click **⬡ GitHub** button in the header, or expand the right panel and click **GitHub** tab
3. Fill in:
   - **Token**: your `ghp_...` token
   - **Owner**: your GitHub username
   - **Repository**: repository name
   - **Branch**: target branch (default: `main`)
4. Click **Connect**

#### Push Notes to GitHub
Click **Push to GitHub** — saves all notes as `zk-notes.json` in your repository.

#### Pull Notes from GitHub
Click **Pull from GitHub** — loads notes from `zk-notes.json` in your repository (overwrites local notes).

**⚠ Important:** Your token is stored in `localStorage`. Do not use ZK on shared/public computers with your token configured.

---

### Clear All Data

Click the **🗑 Clear All** button in the header to delete all notes.

A confirmation dialog appears. This action is **irreversible** — all notes will be permanently deleted from localStorage.

**Tip:** Before clearing, use **Push to GitHub** to create a backup.

---

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+N` | New Note |
| `Ctrl+P` | Quick Open (switcher) |
| `Ctrl+G` | Toggle Graph View |
| `Ctrl+F` | Focus Search |
| `Ctrl+S` | Save (notes auto-save) |
| `Ctrl+B` | Bold |
| `Ctrl+I` | Italic |
| `Ctrl+Tab` | Next Tab |
| `Escape` | Close modal / hide autocomplete |
| `↑/↓` in autocomplete | Navigate suggestions |
| `Enter` in autocomplete | Insert selected link |

---

### Deployment on GitHub Pages

1. Fork or create a repository with `ver1/index.html`
2. Go to repository **Settings** → **Pages**
3. Set **Source** to `Deploy from a branch`
4. Select branch `main` and folder `/ver1` (or root if you moved it)
5. Click **Save**
6. Your ZK will be available at `https://USERNAME.github.io/REPO/ver1/`

**For persistent storage:** Configure GitHub Sync (see above) using a token with write access to the same repository.

---

---

## 🇷🇺 Руководство на русском языке

### Содержание
1. [Введение](#введение)
2. [Начало работы](#начало-работы)
3. [Создание заметок](#создание-заметок)
4. [Связывание заметок](#связывание-заметок)
5. [Теги](#теги)
6. [Граф связей](#граф-связей)
7. [Поиск](#поиск)
8. [Обратные ссылки](#обратные-ссылки)
9. [Структура заметки](#структура-заметки)
10. [Режимы редактора](#режимы-редактора)
11. [Справка по Markdown](#справка-по-markdown)
12. [Синхронизация с GitHub](#синхронизация-с-github)
13. [Очистка данных](#очистка-данных)
14. [Горячие клавиши](#горячие-клавиши)
15. [Развёртывание на GitHub Pages](#развёртывание-на-github-pages)

---

### Введение

**ZK** — полнофункциональное браузерное приложение для ведения заметок в стиле Zettelkasten, вдохновлённое [Obsidian](https://obsidian.md/). Работает полностью в браузере без сервера. Заметки хранятся в `localStorage` и могут синхронизироваться с GitHub-репозиторием.

Основные возможности:
- 📝 Редактирование заметок в формате Markdown с предпросмотром
- 🔗 Вики-ссылки `[[название заметки]]` между заметками
- ⬡ Интерактивный граф связей
- 🏷 Система тегов с фильтрацией
- ↩ Автоматические обратные ссылки
- 🔍 Полнотекстовый поиск
- 📋 Панель структуры (оглавление)
- 🌐 Поддержка русского и английского языков
- ☁ Синхронизация с GitHub
- 🗑 Кнопка очистки всех данных

---

### Начало работы

Откройте `index.html` в любом современном браузере (Chrome, Firefox, Edge, Safari). Установка и сервер не нужны.

**При первом запуске** автоматически создаются три учебные заметки:
- **Welcome to ZK** — обзор возможностей
- **ZK Guide** — горячие клавиши и советы
- **Markdown Reference** — шпаргалка по синтаксису Markdown

---

### Создание заметок

#### Способ 1: Кнопка
Нажмите кнопку **+ New Note** / **+ Новая заметка** в заголовке.

#### Способ 2: Горячая клавиша
Нажмите **Ctrl+N**.

#### Способ 3: Боковая панель
Нажмите **+** рядом с надписью «ХРАНИЛИЩЕ» в левой панели.

#### Диалог создания заметки
Доступны **шаблоны**:
- **Пустой** — чистая заметка
- **Daily Note** — ежедневная заметка с датой, задачами, дневником
- **Meeting Note** — заметка о встрече: участники, повестка, задачи
- **Project Note** — проект: обзор, задачи, ссылки

**Пример:**
1. Нажмите `Ctrl+N`
2. Введите "Моя первая заметка"
3. Выберите шаблон "Daily Note"
4. Нажмите **Создать** или `Enter`

---

### Связывание заметок

ZK использует **вики-ссылки** — стандартный формат Zettelkasten.

#### Создание ссылки
Введите `[[` и название заметки, затем `]]`:
```
Смотрите также [[Welcome to ZK]] для деталей.
```

#### Автодополнение
При вводе внутри `[[...]]` появляется выпадающий список с подходящими заметками. Используйте **↑/↓** для навигации и **Enter** для выбора.

#### Создание новой заметки по ссылке
В режиме предпросмотра клик по **сломанной ссылке** (серой) автоматически создаёт новую заметку.

#### Альтернативный текст ссылки
```
[[Название заметки|Отображаемый текст]]
```

**Пример содержимого заметки:**
```markdown
# Проект Альфа

Связан с [[Исследования]] и [[Встреча 2024-01-15]].

Подробности в [[ZK Guide|полном руководстве]].

#проект #идея
```

---

### Теги

Добавляйте теги в любом месте заметки с префиксом `#`:

```markdown
Эта заметка о #продуктивности и методологии #zettelkasten.
```

#### Правила тегов
- Начинаются с `#`, за которым следует буква (без пробелов)
- Могут содержать буквы, цифры, `/`, `-`, `_`
- Иерархические теги: `#проект/альфа`, `#область/работа`
- Поддерживается кириллица: `#заметки`, `#идея`

#### Панель тегов
Нажмите вкладку **Теги** в левой панели, чтобы увидеть все теги с количеством заметок. Нажмите на тег, чтобы отфильтровать список заметок.

**Пример:**
1. Добавьте `#идея` в несколько заметок
2. Откройте вкладку **Теги**
3. Нажмите `#идея` — в обозревателе файлов отобразятся только эти заметки

---

### Граф связей

Граф отображает связи между всеми вашими заметками.

#### Открытие графа
- Нажмите кнопку **⬡ Граф** в заголовке, или
- Нажмите **Ctrl+G**

#### Элементы графа
- 🔵 **Синие узлы** — заметки
- 🟢 **Бирюзовые узлы** — теги
- 🟠 **Оранжевый узел** — текущая открытая заметка
- **Линии** — связи (вики-ссылки или общие теги)
- **Размер узла** — больше = больше связей

#### Управление
| Действие | Результат |
|----------|-----------|
| **Клик** по узлу | Открыть заметку |
| **Перетащить** узел | Переместить |
| **Перетащить** фон | Перемещение вида |
| **Колесо мыши** | Масштаб |
| **Навести** на узел | Подсказка с именем |
| **Кнопки +/−** | Масштаб |
| **Кнопка ⊡** | Сбросить вид |
| **✕ Закрыть** | Вернуться к редактору |

**Совет:** Создайте несколько связанных заметок и откройте граф, чтобы увидеть вашу сеть знаний!

---

### Поиск

#### Быстрый поиск (заголовок)
Введите запрос в поле поиска вверху страницы. Левая панель переключится на вкладку поиска.

#### Полнотекстовый поиск
1. Нажмите вкладку **Поиск** в левой панели
2. Введите запрос
3. Результаты показывают заголовки заметок и выделенный текст совпадения

#### Быстрое переключение
Нажмите **Ctrl+P** — откроется переключатель заметок. Вводите для фильтрации, используйте **↑/↓**, затем **Enter**.

---

### Обратные ссылки

Панель **Обратные ссылки** (правая боковая панель) показывает все заметки, которые ссылаются на текущую заметку.

Каждая обратная ссылка показывает:
- Заголовок ссылающейся заметки
- Фрагмент контекста вокруг ссылки

Нажмите на обратную ссылку, чтобы перейти к той заметке.

**Пример:**
- Заметка "Проект Альфа" содержит `[[Исследования]]`
- Открыв "Исследования", в панели обратных ссылок увидите "Проект Альфа"

---

### Структура заметки

Откройте вкладку **Структура** в правой панели — увидите оглавление на основе заголовков текущей заметки.

- Нажмите на заголовок, чтобы перейти к нему
- Работает в режимах редактора и предпросмотра
- Поддерживает заголовки H1–H4

---

### Режимы редактора

Три режима (переключаются кнопками в панели инструментов редактора):

| Режим | Описание |
|-------|----------|
| **Редактор** | Редактирование сырого текста Markdown |
| **Просмотр** | Отрендеренный Markdown |
| **Разделить** | Редактор и предпросмотр рядом |

**Совет:** Используйте режим **Разделить** для отображения изменений в реальном времени.

---

### Справка по Markdown

#### Форматирование текста
```markdown
**Жирный текст**
*Курсив*
~~Зачёркнутый~~
`Встроенный код`
```

#### Заголовки
```markdown
# Заголовок 1
## Заголовок 2
### Заголовок 3
```

#### Списки
```markdown
- Маркированный элемент
- Другой элемент

1. Первый элемент
2. Второй элемент

- [ ] Невыполненная задача
- [x] Выполненная задача
```

#### Ссылки
```markdown
[[Внутренняя заметка]]
[[Заметка|Отображаемый текст]]
[Внешняя ссылка](https://example.com)
```

#### Цитата
```markdown
> Это цитата
```

#### Блок кода
````markdown
```python
x = 42
print(x)
```
````

#### Таблица
```markdown
| Столбец 1 | Столбец 2 |
|-----------|-----------|
| Ячейка 1  | Ячейка 2  |
```

---

### Синхронизация с GitHub

ZK может сохранять и загружать заметки из GitHub-репозитория, обеспечивая постоянное хранение для GitHub Pages.

#### Настройка
1. Создайте **Personal Access Token** на GitHub:
   - GitHub → Settings → Developer settings → Personal access tokens
   - Выдайте разрешение **Contents: Read and Write** для вашего репозитория
2. Нажмите кнопку **⬡ GitHub** в заголовке
3. Заполните поля:
   - **Token**: ваш токен `ghp_...`
   - **Owner**: ваш логин GitHub
   - **Repository**: имя репозитория
   - **Branch**: ветка (по умолчанию: `main`)
4. Нажмите **Подключить**

#### Сохранение заметок в GitHub
Нажмите **Сохранить в GitHub** — все заметки сохраняются как `zk-notes.json` в репозитории.

#### Загрузка заметок из GitHub
Нажмите **Загрузить из GitHub** — заметки загружаются из `zk-notes.json` (перезаписывает локальные заметки).

**⚠ Важно:** Токен хранится в `localStorage`. Не используйте ZK на общедоступных компьютерах с настроенным токеном.

---

### Очистка данных

Нажмите кнопку **🗑 Очистить всё** в заголовке для удаления всех заметок.

Появится диалог подтверждения. Действие **необратимо** — все заметки будут безвозвратно удалены из localStorage.

**Совет:** Перед очисткой используйте **Сохранить в GitHub** для создания резервной копии.

---

### Горячие клавиши

| Клавиши | Действие |
|---------|----------|
| `Ctrl+N` | Новая заметка |
| `Ctrl+P` | Быстрое переключение |
| `Ctrl+G` | Открыть/закрыть граф |
| `Ctrl+F` | Фокус на поиск |
| `Ctrl+S` | Сохранить (заметки сохраняются автоматически) |
| `Ctrl+B` | Жирный текст |
| `Ctrl+I` | Курсив |
| `Ctrl+Tab` | Следующая вкладка |
| `Escape` | Закрыть диалог / скрыть подсказки |
| `↑/↓` в автодополнении | Навигация по подсказкам |
| `Enter` в автодополнении | Вставить выбранную ссылку |

---

### Развёртывание на GitHub Pages

1. Создайте или форкните репозиторий с файлом `ver1/index.html`
2. Перейдите в **Settings** → **Pages** репозитория
3. Установите **Source**: `Deploy from a branch`
4. Выберите ветку `main` и папку `/ver1`
5. Нажмите **Save**
6. ZK будет доступен по адресу `https://USERNAME.github.io/REPO/ver1/`

**Для постоянного хранения:** Настройте синхронизацию с GitHub (см. выше), используя токен с правами на запись в тот же репозиторий.

---

*ZK — Zettelkasten | Browser-based | No server required | Open source*
