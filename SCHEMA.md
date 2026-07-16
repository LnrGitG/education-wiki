---
title: SCHEMA — Образование и направления обучений
created: 2026-07-16
updated: 2026-07-16
type: schema
---

# Education Wiki — Схема

## Структура каталогов

```
education-wiki/
├── index.md                  # Навигатор по всем страницам
├── SCHEMA.md                 # Этот файл
├── log.md                    # Журнал изменений
├── entities/                 # Сущности (вузы, организации)
├── concepts/                 # Концепции, направления, дисциплины
├── universities/             # Профили вузов
├── fields/                   # Направления подготовки (code-based)
├── raw/                      # Сырые данные (PDF, CSV, JSON)
│   └── data/                 # Таблицы, датасеты, выгрузки
└── queries/                  # Аналитические запросы/обзоры
```

## Правила именования файлов

- **entities/<slug>.md** — `mit.md`, `vsh-e.md`, `inno-university.md`
- **universities/<slug>.md** — `kazan-fu-it.md`, `msu-computer-science.md`
- **fields/<code>-<name>.md** — `09-03-01-informatika.md`, `38-03-05-ekonomika.md`
- **concepts/<slug>.md** — `kompetencionnaya-model.md`, `bolonskaya-sistema.md`
- **queries/<slug>.md** — `sravnenie-programm-ml.md`, `rynok-it-obrazovaniya.md`

## Фронтматтер (обязательные поля)

```yaml
---
title: Название направления/вуза
code: 09.03.01 # для fields (код специальности)
type: field | university | entity | concept | query
region: Поволжье | Россия | Global | Москва | etc
level: ba | ma | phd | specialist
source_url: https://...
created: 2026-07-16
updated: 2026-07-16
tags: [ml, ds, economics, finance]
---
```

## Связи

- **[[wikilinks]]** — внутренние ссылки между страницами
- `source_url` — внешние источники (сайты вузов, ФГОС, рейтинги)
- `code` — код специальности (ФГОС, ОКСО) для fields

## Таксономия тегов

| Тег | Содержание |
|-----|------------|
| `ml`, `ds`, `ai` | Машинное обучение, Data Science, ИИ |
| `econ`, `fin`, `banking` | Экономика, финансы, банки |
| `mgmt`, `startup` | Менеджмент, entrepreneuship |
| `law`, `policy` | Право, госуправление, регуляторика |
| `tech`, `eng` | Технические/инженерные специальности |
| `soft`, `design` | Софт-скиллы, дизайн, гуманитарные |
| `stats`, `math` | Статистика, математика |
| `phd`, `research` | Научные/исследовательские программы |

## Формат страницы поля/направления

```markdown
# Название направления (код)

## Описание
Краткое описание из ФГОС/сайта вуза

## Структура программы
- Core courses
- Specializations
- Electives
- Практика/project work

## Карьерные треки
- Роли/позиции после выпуска
- Отрасли

## Требования
- Вступительные экзамены
- Математическая подготовка
- Программирование

## Вузы с программой
- [[msu-computer-science]]
- [[hse-data-science]]
```

## Формат страницы вуза

```markdown
# ВУЗ — Полное название

## Профиль
Тип, уровень, аккредитация, год основания

## Направления
- [[09-03-01-informatika]]
- [[38-03-05-ekonomika]]

## Особенности
- Международные partnerships
- Research centers
- Industry connections
```

## Источники данных

- ФГОС РФ (fgos.ru)
- ОКСО (okso.obrnadzor.gov.ru)
    - Сайты вузов
- Рейтинги (QS, THE, RAEX)
    - HeadHunter/HH.ru (вакансии по направлениям)
    - Зарплатомеры (hr-аналитика)
