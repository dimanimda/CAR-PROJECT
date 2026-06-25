# CAR-PROJECT — полигон сравнения пайплайнов

Один **замороженный** эталон = неподвижная мишень. Вокруг неё крутим три независимые оси и складываем иммутабельные прогоны, которые честно сравниваются во времени.

## Что заморожено
- **`PROMPT.md`** — эталонный промпт (базовая постановка). Не меняется.
- **`RUBRIC.md`** — критерии оценки. Меняются только переходом на новую версию.

Меняем оси, не мишень.

## Три оси эксперимента

1. **Обвязка (harness)** — чем исполняем: `hermes` (голый), `hermes-pi`, `hermes-claudecode`, `hermes-codex`, `hermes-opencode`, `hermes-multi` (pipeline-coding).
2. **Модель** — какой мозг под обвязкой: `deepseek-v4-pro`, `claude-sonnet-4`, … (где обвязка даёт выбор). `mixed` для мульти-провайдерных пайплайнов.
3. **Подход к постановке** — `baseline` · `criteria` · `constraints` · `spiral` (см. `prompts/`). Можно добавлять новые.

## Структура

```
CAR-PROJECT/
├── PROMPT.md          эталон                              [ЗАМОРОЖЕН]
├── RUBRIC.md          критерии оценки (v1)                 [ЗАМОРОЖЕН до v2]
├── README.md          этот файл
├── RESULTS.md         append-only журнал всех прогонов
├── prompts/           ось 3 — постановки задачи
│   ├── 00-baseline.md
│   ├── 01-criteria.md
│   ├── 02-constraints.md
│   └── 03-spiral.md
└── runs/              все прогоны
    └── <harness>__<model>__<approach>/
        ├── index.html
        ├── used-prompt.md     точная постановка, что ушла модели
        ├── meta.json          harness, model, approach, дата, время ген., #итераций/токены
        └── screenshot.png
```

## Схема именования прогона
`<harness>__<model>__<approach>` — три оси, разделитель `__` (двойное подчёркивание), дефисы остаются внутри сегментов.

Примеры:
- `runs/hermes__deepseek-v4-pro__baseline/`
- `runs/hermes-pi__deepseek-v4-pro__spiral/`
- `runs/hermes-multi__mixed__criteria/`

Плоско → grep по любой оси (`ls runs/ | grep spiral`), 1 папка = 1 строка в `RESULTS.md`.

## Протокол одного прогона
1. Выбрать ячейку матрицы (harness × model × approach).
2. Создать `runs/<harness>__<model>__<approach>/`.
3. Положить `used-prompt.md` — точную постановку (из `prompts/`).
4. Сгенерировать `index.html` выбранной обвязкой.
5. Записать `meta.json` (harness, model, approach, дата, время генерации, #итераций/токены).
6. Открыть в браузере → `screenshot.png` + прочитать console.
7. Оценить по `RUBRIC.md` → добавить строку в `RESULTS.md`.

## Ритуал возвращения
- Старые прогоны **иммутабельны** — новый визит добавляет ячейки, не переписывает старые.
- `RESULTS.md` — **append-only**.
- Меняем критерии → `RUBRIC v2`, помечаем версию у каждого прогона.
- Эталон (`PROMPT.md`) и текст постановок (`prompts/`) фиксируем; новые подходы добавляем новыми файлами `prompts/NN-*.md`, не правим старые.
