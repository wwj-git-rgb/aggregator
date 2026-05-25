```markdown
# aggregator Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the development patterns, coding conventions, and common workflows for contributing to the `aggregator` repository. The project is a Python-based aggregator for subscription sources, proxy management, and automation scripts, with a focus on modularity and maintainability. You'll learn how to extend subscription logic, update configuration templates, manage push channels, and automate operational scripts using the repository's established patterns.

## Coding Conventions

### File Naming

- **PascalCase** is used for file names (e.g., `Airport.py`, `Clash.py`).
- Submodules and directories are grouped by feature (e.g., `aggregate/subscribe/`, `aggregate/subconverter/`, `aggregate/cmd/`).

### Import Style

- **Relative imports** are preferred within modules.

  ```python
  from .utils import parse_subscription
  from .process import process_sources
  ```

### Export Style

- **Named exports**: Functions and classes are explicitly defined and exported.

  ```python
  # In airport.py
  class AirportCrawler:
      ...

  def fetch_airport_data():
      ...
  ```

### Commit Patterns

- Commit messages are freeform, typically around 30 characters.
- No strict prefixing, but descriptive messages are encouraged.

## Workflows

### subscribe-module-feature-development

**Trigger:** When you want to add, change, or fix subscription logic (e.g., crawling, processing, proxy handling).  
**Command:** `/subscribe-feature`

1. Edit or create one or more of the following files:
    - `aggregate/subscribe/airport.py`
    - `aggregate/subscribe/clash.py`
    - `aggregate/subscribe/crawl.py`
    - `aggregate/subscribe/process.py`
    - `aggregate/subscribe/push.py`
    - `aggregate/subscribe/renewal.py`
    - `aggregate/subscribe/utils.py`
    - `aggregate/subscribe/mailtm.py`
    - `aggregate/subscribe/workflow.py`
    - `aggregate/subscribe/collect.py`
2. Optionally update subconverter configs if relevant:
    - `aggregate/subconverter/pref.example.ini`
    - `aggregate/subconverter/pref.example.yml`
    - `aggregate/subconverter/pref.toml`
3. Commit changes with a message describing the feature or fix.

**Example:**

```python
# aggregate/subscribe/airport.py
class AirportCrawler:
    def crawl(self):
        # Logic to crawl airport subscriptions
        pass
```

### subconverter-config-update

**Trigger:** When you want to adjust how subconverter works or provide new configuration examples.  
**Command:** `/update-subconverter-config`

1. Edit one or more configuration files:
    - `aggregate/subconverter/pref.example.ini`
    - `aggregate/subconverter/pref.example.yml`
    - `aggregate/subconverter/pref.toml`
2. Optionally edit subscribe module files to match config changes.
3. Commit changes.

**Example:**

```ini
# aggregate/subconverter/pref.example.ini
[General]
update_interval = 24
```

### add-or-update-push-channels

**Trigger:** When you want to support a new push channel or modify existing push logic.  
**Command:** `/add-push-channel`

1. Edit `aggregate/subscribe/push.py`.
2. Optionally edit related subscribe files:
    - `aggregate/subscribe/process.py`
    - `aggregate/subscribe/workflow.py`
3. Commit changes.

**Example:**

```python
# aggregate/subscribe/push.py
def send_telegram_notification(message):
    # Logic to send notification via Telegram
    pass
```

### cmd-script-batch-update

**Trigger:** When you want to automate or improve operational scripts for the aggregator system.  
**Command:** `/update-cmd-scripts`

1. Edit or add files in `aggregate/cmd/`:
    - `clash-update.bat`, `clash-update.cmd`, `clash.meta-update.cmd`, etc.
2. Optionally update subconverter config files if relevant.
3. Commit changes.

**Example:**

```bat
:: aggregate/cmd/clash-update.bat
@echo off
python ..\..\aggregate\subscribe\clash.py --update
```

## Testing Patterns

- **Framework:** Unknown (no explicit test framework detected).
- **Test File Pattern:** Files matching `*.test.*` (e.g., `airport.test.py`).
- Tests are likely placed alongside the modules they test.
- To add tests, create files like `airport.test.py` and use standard Python testing practices.

**Example:**

```python
# aggregate/subscribe/airport.test.py
def test_airport_crawler():
    crawler = AirportCrawler()
    assert crawler.crawl() is not None
```

## Commands

| Command                    | Purpose                                                    |
|----------------------------|------------------------------------------------------------|
| /subscribe-feature         | Add, change, or fix subscription logic                     |
| /update-subconverter-config| Update subconverter configuration templates/examples        |
| /add-push-channel          | Add or update push notification channels                   |
| /update-cmd-scripts        | Add or update batch/command scripts for automation         |
```
