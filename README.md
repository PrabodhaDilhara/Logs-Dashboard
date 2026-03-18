# Logs-Dashboard
Real-time Logs Dashboard for monitoring live table status, logs, alerts, error analysis, and TDI visualization using FastAPI, WebSocket, and frontend UI.


File structure->


logs-dashboard/
│
├── backend/
│   ├── main.py                              ← FastAPI entry point
│   ├── requirements.txt                     ← all packages
│   │
│   └── app/
│       ├── api/
│       │   └── routes/
│       │       ├── logs.py                  ←  /logs, /logs/{table_id}
│       │       ├── tables.py                ←  /tables, /tables/{id}/status
│       │       ├── alerts.py                ←  /alerts, /alerts/history
│       │       └── layout.py                ←  /layout/events
│       │
│       ├── core/
│       │   ├── config.py                    ← app settings, constants
│       │   └── database.py                  ← DB connection 
│       │
│       ├── models/                          ← DB tables from PDF
│       │   ├── log.py                       ← logs table
│       │   ├── alert.py                     ← alerts table
│       │   ├── table_status.py              ← table_status table
│       │   └── layout_event.py              ← layout_events table
│       │
│       ├── schemas/                         ← Pydantic request/response
│       │   ├── log_schema.py
│       │   ├── alert_schema.py
│       │   └── table_schema.py
│       │
│       ├── services/
│       │   ├── error_analysis.py            ←  pattern detection
│       │   ├── alert_service.py             ← dispatch + thresholds
│       │   ├── camera_detection.py          ←  camera offline
│       │   └── layout_detection.py          ←  layout change
│       │
│       ├── websocket/
│       │   ├── manager.py                   ←connection manager
│       │   └── events.py                    ←  event type definitions
│       │
│       └── tests/
│           ├── test_logs_api.py             ←  unit + API tests
│           ├── test_alerts_api.py           ← 
│           └── test_websocket.py            ←  WS stress test
│
├── frontend/
│   ├── css/
│   │   └── theme.css                        ← unified theme, ALL pages use this
│   │
│   ├── js/
│   │   ├── main.js                          ← entry point
│   │   ├── websocket.js                     ← WS client
│   │   └── modules/
│   │       ├── logs.js                      ←  live log viewer
│   │       ├── tables.js                    ←  table status cards
│   │       ├── alerts.js                    ←  alert panel
│   │       ├── charts.js                    ←  error frequency charts
│   │       └── tdi.js                       ←  TDI interface
│   │
│   ├── html/
│   │   ├── index.html                       ← Logs Dashboard page
│   │   └── tdi.html                         ← TDI page 
│   │
│   └── assets/
│       └── icons/                           ← SVG icons (no emojis allowed)
│
├── dummy_data/
│   ├── log_generator.py                     ←  fake log streams
│   ├── camera_simulator.py                  ←  camera offline events
│   └── layout_simulator.py                  ←  layout change events
│
├── docs/
│   ├── architecture.md
│   └── api_reference.md
│
├── .env
├── .gitignore
└── README.md
