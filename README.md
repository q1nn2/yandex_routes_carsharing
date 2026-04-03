# Яндекс Маршруты — Sprint 3 (Manual QA, каршеринг)

Ручное тестирование веб‑сервиса **Яндекс Маршруты** в части **каршеринга**: сверка вёрстки с макетом, сценарии окон «Способ оплаты» и «Добавление карты», логика кнопки «Забронировать», оформление баг‑репортов.

![Manual QA](https://img.shields.io/badge/Type-Manual%20QA-blue)
![Scope](https://img.shields.io/badge/Scope-Layout%20%2B%20Payment%20%2B%20Book-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Focus](https://img.shields.io/badge/Focus-Carsharing%20UI-purple)
![Bugs](https://img.shields.io/badge/Bugs-33_total%20%7C%201_blocker-red)

---

## Содержание

- [Описание](#описание)
- [Ссылки](#ссылки)
- [Артефакты](#артефакты)
- [Ключевые и блокирующие дефекты](#ключевые-и-блокирующие-дефекты)
- [Заблокированные проверки](#заблокированные-проверки)
- [Итоги](#итоги)
- [Окружение](#окружение)
- [Вывод](#вывод)
- [Автор](#автор)

---

## Описание

Цель работы — оценить качество реализации:

- **вёрстки** формы бронирования каршеринга, карты и окон состояния заказа (сверка с Figma);
- **окон «Способ оплаты» и «Добавление карты»** (навигация, валидация полей карты и кода);
- **логики кнопки «Забронировать»** в зависимости от заполненности прав, оплаты и адресов.

Итоги основаны на прогоне чек‑листов и тест‑кейсов, зафиксированных в Google Sheets, с дублированием артефактов в репозитории в формате Markdown.

---

## Ссылки

- **Репозиторий (GitHub):** [q1nn2/Sprint_3_yandex_routes-carsharing-](https://github.com/q1nn2/Sprint_3_yandex_routes-carsharing-)
- **Тестируемый стенд:** `https://qa-routes.praktikum-services.ru/`
- **Макеты (Figma):** [Яндекс Маршруты](https://www.figma.com/file/fPw1Xj2dYJy5mdyCg2jduh/%D0%AF%D0%BD%D0%B4%D0%B5%D0%BA%D1%81-%D0%9C%D0%B0%D1%80%D1%88%D1%80%D1%83%D1%82%D1%8B?node-id=2-18586&p=f&t=5hMAjMC5GwSXOAOg-0)
- **Требования (каршеринг):** [Требования к функциональности Каршеринг (Yonote)](https://practicum-for-students.yonote.ru/share/0ff0230f-e963-47fa-9a87-8daa1b77fac1/doc/trebovaniya-k-funkcionalnosti-karshering-fF071lXRxM)

---

## Артефакты

Общая таблица: [Google Sheets — Sprint 3](https://docs.google.com/spreadsheets/d/1RUIqS2PpyX0tpLlChrycO3SNLExo3msplwUWW8lf9Qc/edit)

| Артефакт | Формат | Google Sheets (лист) | GitHub |
|----------|--------|----------------------|--------|
| Чек‑лист вёрстки | Markdown | [gid=899462569](https://docs.google.com/spreadsheets/d/1RUIqS2PpyX0tpLlChrycO3SNLExo3msplwUWW8lf9Qc/edit?gid=899462569#gid=899462569) | [`checklists/layout.md`](checklists/layout.md) |
| Способ оплаты / Добавление карты | Markdown | [gid=1540435533](https://docs.google.com/spreadsheets/d/1RUIqS2PpyX0tpLlChrycO3SNLExo3msplwUWW8lf9Qc/edit?gid=1540435533#gid=1540435533) | [`checklists/payment-and-card.md`](checklists/payment-and-card.md) |
| Логика «Забронировать» | Markdown | [gid=1567345705](https://docs.google.com/spreadsheets/d/1RUIqS2PpyX0tpLlChrycO3SNLExo3msplwUWW8lf9Qc/edit?gid=1567345705#gid=1567345705) | [`testcases/book-button.md`](testcases/book-button.md) |
| Баг‑репорты | Markdown | [gid=977751969](https://docs.google.com/spreadsheets/d/1RUIqS2PpyX0tpLlChrycO3SNLExo3msplwUWW8lf9Qc/edit?gid=977751969#gid=977751969) | [`bugreports/`](bugreports) (`B1.md` … `B33.md`) |

---

## Ключевые и блокирующие дефекты

**Блокирующий:** [Б19](bugreports/B19.md) — окно «Машина забронирована» не закрывается по «Отменить», из‑за чего недоступна цепочка подтверждения отмены поездки.

**Критические** (по приоритету в баг‑трекере): [Б6](bugreports/B6.md), [Б11](bugreports/B11.md)–[Б17](bugreports/B17.md), [Б20](bugreports/B20.md), [Б25](bugreports/B25.md), [Б31](bugreports/B31.md)–[Б33](bugreports/B33.md) — карта и выбор авто, подтверждение прав, отображение данных после бронирования, валидация кода карты, логика бронирования и формы при пустых адресах.

**Стандартные:** [Б9](bugreports/B9.md), [Б10](bugreports/B10.md), [Б21](bugreports/B21.md)–[Б24](bugreports/B24.md), [Б26](bugreports/B26.md)–[Б29](bugreports/B29.md).

**Желательные:** [Б1](bugreports/B1.md)–[Б5](bugreports/B5.md), [Б7](bugreports/B7.md), [Б8](bugreports/B8.md), [Б18](bugreports/B18.md), [Б30](bugreports/B30.md).

---

## Заблокированные проверки

- **Т52–Т60** (окна подтверждения отмены и «Поездка отменена») — **Blocked** из‑за [Б19](bugreports/B19.md): невозможно дойти до сценария после нажатия «Отменить» в окне «Машина забронирована».
- **TC-04** — **Blocked** из‑за [Б33](bugreports/B33.md): при удалении адресов и заполненных правах/оплате форма ведёт себя не по сценарию.
- **TC-05** — **Skipped** (связь с **Б33** в таблице): проверка не выполнялась или не актуальна в текущем виде сценария.

---

## Итоги

Одна сводная таблица по прогонам. **Вёрстка:** те же цифры в **Firefox 800×600** и **Chrome 1920×1080**. **Оплата / карта:** **Chrome 1920×1080**.

| Проверка | Всего | Passed | Failed | Skipped | Blocked |
|----------|------:|-------:|-------:|--------:|--------:|
| Чек‑лист вёрстки (Т1–Т60) | 60 | 32 | 18 | 1 | 9 |
| Способ оплаты / добавление карты (Т1–Т38) | 38 | 28 | 10 | — | — |
| Тест‑кейсы кнопки «Забронировать» | 5 | 1 | 2 | 1 | 1 |

- **Skipped (вёрстка):** Т17 — нет функции.  
- **Blocked (вёрстка):** Т52–Т60 — [Б19](bugreports/B19.md).

**Баг-репорты:** **33** — блокер **1**, крит **13**, станд **10**, желат **9**.

---

## Окружение

- **ОС:** Windows 11 Pro 21H2  
- **Браузер (основной):** Google Chrome 144.0.7559.133, 1920×1080  
- **Браузер (вёрстка):** Firefox, 800×600  

---

## Вывод

> Обнаружены **блокирующий** дефект отмены поездки (**Б19**) и множество **критических** расхождений по карте, бронированию и оплате. Вёрстка и тексты формы заметно расходятся с макетом. **Релиз не рекомендуется** до устранения блокирующего и ключевых критических дефектов и повторного регрессионного прогона.

---

## Автор

**Anatoly Elnikov**  
Manual QA Engineer

