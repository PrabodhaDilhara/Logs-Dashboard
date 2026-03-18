# Logs Dashboard

Real-time Logs Dashboard for monitoring live table status, logs, alerts, error analysis, layout changes, camera health, and TDI visualization using FastAPI, WebSocket, and a separate frontend UI.

---

## Project Structure

```text
logs-dashboard/
│
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   │
│   └── app/
│       ├── api/
│       │   └── routes/
│       │       ├── logs.py
│       │       ├── tables.py
│       │       ├── alerts.py
│       │       └── layout.py
│       │
│       ├── core/
│       │   ├── config.py
│       │   └── database.py
│       │
│       ├── models/
│       │   ├── log.py
│       │   ├── alert.py
│       │   ├── table_status.py
│       │   └── layout_event.py
│       │
│       ├── schemas/
│       │   ├── log_schema.py
│       │   ├── alert_schema.py
│       │   └── table_schema.py
│       │
│       ├── services/
│       │   ├── error_analysis.py
│       │   ├── alert_service.py
│       │   ├── camera_detection.py
│       │   └── layout_detection.py
│       │
│       ├── websocket/
│       │   ├── manager.py
│       │   └── events.py
│       │
│       └── tests/
│           ├── test_logs_api.py
│           ├── test_alerts_api.py
│           └── test_websocket.py
│
├── frontend/
│   ├── css/
│   │   └── theme.css
│   │
│   ├── js/
│   │   ├── main.js
│   │   ├── websocket.js
│   │   └── modules/
│   │       ├── logs.js
│   │       ├── tables.js
│   │       ├── alerts.js
│   │       ├── charts.js
│   │       └── tdi.js
│   │
│   ├── html/
│   │   ├── index.html
│   │   └── tdi.html
│   │
│   └── assets/
│       └── icons/
│
├── dummy_data/
│   ├── log_generator.py
│   ├── camera_simulator.py
│   └── layout_simulator.py
│
├── docs/
│   ├── architecture.md
│   └── api_reference.md
│
├── .env
├── .gitignore
└── README.md
