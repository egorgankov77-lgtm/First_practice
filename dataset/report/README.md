# Security Scan Dataset — basic-flask-template

## Назначение

Датасет содержит результаты анализа учебного Flask-проекта `basic-flask-template-master`.

## Объекты анализа

- Исходный Python-код проекта — анализирован Bandit.
- Локально запущенное Flask-приложение — `http://127.0.0.1:5000`, анализировано Nikto 2.1.5.

Сканирование выполнялось только против локального тестового сервера.

## Результаты

### Bandit

Bandit завершил анализ без обнаруженных проблем:

- Total lines of code: 30
- High: 0
- Medium: 0
- Low: 0
- Files skipped: 0

Сырые результаты:

- `raw/bandit_result.json`
- `raw/bandit_result.txt`

### Nikto

Nikto 2.1.5 проверил локальный сервер:

- Target: `127.0.0.1`
- Port: `5000`
- Server: `Werkzeug/3.1.9 Python/3.14.4`
- 6544 items checked
- 0 errors
- 3 reported items

Сырой HTML-отчёт:

- `raw/nikto_report.html`

## Структура

```text
dataset/
├── data/
│   └── scan_findings.csv
├── meta/
│   └── scan_findings.meta
├── raw/
│   ├── bandit_result.json
│   ├── bandit_result.txt
│   └── nikto_report.html
└── report/
    ├── README.md
    ├── expert_assessment.md
    └── sources.md
```

## Важно

Файлы `raw/` являются исходными результатами, полученными в VM. Если этот архив собирается вне VM, скопируйте в него именно те файлы, которые были созданы командами Bandit и Nikto.

`scan_findings.csv` содержит только фактически зафиксированные результаты; отсутствие находок Bandit не превращается в искусственную уязвимость.
