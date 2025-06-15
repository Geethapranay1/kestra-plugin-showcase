# 🚀 Kestra Plugin Showcase

**ID:** `kestra-plugin-showcase`  
**Namespace:** `hackathon.minimal`  
**Description:** Ultra-simple workflow that actually works 🚀

---

## Overview

This project showcases a **minimal yet powerful Kestra workflow** that:

- Periodically hits an API (`https://httpbin.org/json`)
- Analyzes the response for health status
- Generates a simple report (`api_report.html` + `summary.json`)
- Logs the result

> Ideal for beginners learning Kestra plugin usage with real-world structure and outputs.

---

## Plugins Used

- `io.kestra.plugin.core.trigger.Schedule`  
- `io.kestra.plugin.core.http.Request`  
- `io.kestra.plugin.scripts.python.Script`  
- `io.kestra.plugin.scripts.shell.Commands`  
- `io.kestra.plugin.core.log.Log`

---

## Workflow Breakdown

| Task ID          | Description                          |
|------------------|--------------------------------------|
| `api_check`      | Sends a GET request to httpbin.org   |
| `analyze_data`   | Python-based simple logic for health |
| `generate_reports` | Creates a JSON + HTML visual report |
| `final_log`      | Logs status and output info to Kestra|

---

## Outputs

- `api_status_code`: API status (e.g., 200)
- `report_file`: Path to `api_report.html`
- `summary_file`: Path to `summary.json`
- `execution_summary`: Simple summary string

---

## Triggering

Runs **every 5 minutes** using Cron:
```cron
*/5 * * * *
