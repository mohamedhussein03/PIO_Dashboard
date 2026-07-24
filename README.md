# PIO Dashboard

A web based Crisis and Public Information Operations dashboard built with Flask. The platform helps organizations monitor incidents, coordinate response activities, and manage public information from a centralized interface.

The dashboard supports two user roles with different permissions and is designed for live operational environments through automatic data refresh, scenario based management, and a responsive dark mode interface.

## About

PIO Dashboard was developed as an internal operational dashboard for BP. The application was designed to support Public Information Operations during incident and crisis management by providing a centralized platform for monitoring information, coordinating response activities, and managing operational communications.

This repository showcases the software implementation and architecture of the project. It does not contain any confidential BP data or proprietary operational information.

---

## Features

### Scenario Management

- Supports one active scenario at a time
- Most application data is linked to a `scenario_id`
- Allows switching between different crisis scenarios while preserving historical data

### User Roles

#### Admin

- Full Create, Read, Update, Delete (CRUD) access
- Manage all dashboard content
- Configure scenarios
- Create and manage task timers
- Edit and delete responses
- Access all dashboard modals

#### Guest

- Read-only access across the dashboard
- Submit:
  - Social Comment / Response
  - News Comment / Response

---

## Dashboard Overview

### Main Dashboard

- BP Egypt status card
- Incident overview
- Live clock
- Task timer
- BP Monitor
- Weather widget
- Interactive map
- Situational status
- Action tracker
- Calls section

### PIO Dashboard

- Social Monitor
- News & Headlines
- Social Comment / Response
- News Comment / Response

---

## BP Monitor

A live scrolling information banner that displays one rolling message for the active scenario.

Features

- Large bold text
- "BP" highlighted in green
- Scrolls from left to right
- Starts completely off-screen
- Completes a full cycle before repeating
- Animation speed configurable through CSS

---

## Task Timer

Each scenario supports one active countdown timer.

Fields

- Title
- Countdown
- Attendees
- Next Meeting
- Location

Features

- Countdown value becomes fixed after creation
- Remaining time calculated from the server
- Stored in the database
- Admin only management

---

## Action Tracker

Track operational activities in real time.

Features

- Fixed table headers
- Newest entries displayed first
- Editable rows
- Status color indicators

| Status | Color |
|--------|-------|
| Submitted | Blue |
| Pending | Yellow |
| Completed | Green |
| None | Gray |

---

## Automatic Refresh

The dashboard refreshes automatically every 60 seconds to keep operational data current.

Automatic refresh pauses whenever:

- An input field is focused
- A textarea is focused
- A modal is open

This prevents administrators from losing unsaved work while editing.

---

## Response System

### Social Responses

Fields

- Title
- Text
- Created At
- Scenario ID

### News Responses

Fields

- Title
- Text
- Created At
- Scenario ID

Permissions

| Action | Admin | Guest |
|---------|-------|-------|
| View | ✅ | ✅ |
| Create | ✅ | ✅ |
| Delete | ✅ | ❌ |

---

## Images

The media dashboard supports external images only.

- Images loaded using `image_url`
- No local file uploads
- Images displayed above content
- Text never overlays images

---

## Technology Stack

### Backend

- Flask
- Flask-Login
- Flask-SQLAlchemy
- Flask-Migrate

### Frontend

- Jinja2
- Vanilla JavaScript
- HTML5
- CSS3

### Database

- SQLite (Development)
- SQLite or MySQL (Production)

### Deployment

- PythonAnywhere
- Gunicorn
- Python 3.10 Virtual Environment

---

## Project Structure

```
PIO_Dashboard/
│
├── app/
│   ├── __init__.py
│   ├── extensions.py
│   ├── models.py
│   ├── main/
│   │   ├── __init__.py
│   │   └── routes.py
│   ├── templates/
│   │   └── dashboard/
│   │       ├── base.html
│   │       ├── home.html
│   │       ├── media.html
│   │       └── modals.html
│   └── static/
│       ├── css/
│       ├── js/
│       └── sounds/
│
├── migrations/
├── instance/
│   └── app.db
├── requirements.txt
├── run.py
└── .env
```

---

## Design Principles

- Dark mode support
- Responsive layout
- Minimal page reloads
- Automatic live updates
- Consistent modal system
- Scenario based data management
- Operational dashboard optimized for crisis response

---

## Future Improvements

- Role-based permission expansion
- Real-time updates using WebSockets
- Notification system
- Audit logging
- Analytics dashboard
- Multi-language support
- Interactive GIS integration

---

<img width="1907" height="910" alt="Screenshot 2026-07-24 154926" src="https://github.com/user-attachments/assets/9735b997-0551-4c54-8057-21b0df3b9d4d" />

<img width="1919" height="868" alt="Screenshot 2026-07-24 154941" src="https://github.com/user-attachments/assets/f817de4f-0097-4763-95ac-c2604d5b50bf" />

<img width="1912" height="895" alt="Screenshot 2026-07-24 154954" src="https://github.com/user-attachments/assets/87433943-b000-4260-ad37-be9dd71d2356" />




## License

This project was developed as part of a Public Information Operations dashboard and is intended for operational use.
