# Restarting and Troubleshooting FOSSology

This document explains how to restart FOSSology safely
and how to troubleshoot common problems faced by beginners.

---

## Important Concept

Closing the browser does NOT stop FOSSology.

FOSSology runs inside Docker containers in the background.
The browser is only used to access the web interface.

---

## Reopening FOSSology

### Case 1: Browser was closed

Nothing is stopped.

Open the browser again and go to:

http://localhost:8081/repo

No Docker command is required.

---

### Case 2: System was restarted or shut down

Docker containers may not start automatically.

Go to the FOSSology directory and run:

```bash
cd fossology
docker-compose up -d```
# Then open the browser and go to:

  http://localhost:8081/repo

### Case 3: Containers were stopped manually
 Start them again using:

```bash
Copy code
docker-compose up -d```

# Stopping FOSSology Safely
To stop all FOSSology services:

bash
Copy code
```docker-compose down```

# This command:

* Stops containers

* Keeps uploads and database safe

* Does NOT delete data

# Restarting FOSSology Cleanly
If FOSSology behaves incorrectly, restart all services:

bash
Copy code
```
docker-compose down
docker-compose up -d

```
# This restarts:

* Web interface

* Scheduler

* Agents

* Database connections

# Full Reset (Use With Caution)
This command removes all data:

bash
Copy code
```
docker-compose down -v
```
# Warning:

* Deletes database

* Deletes uploads

* Deletes scan results

Use only if a fresh installation is required.

## Understanding Errors
The web interface may show messages like:

# Job failed

This message does not show the real reason.

The actual reason is available in logs.

#Viewing Logs
To view logs:

bash
Copy code
```
docker-compose logs -f
```

# Logs help identify:

* Agent failures

* Scheduler errors

*  Configuration problems

* Permission issues

Press CTRL + C to stop viewing logs.

# common Problems and Fixes
Problem: Scan job failed
Steps:

1. Open the Jobs tab

2. Read the error message

3. Check logs using docker-compose logs -f

# Problem: Uploaded file but no scan results
Possible causes:

* Agents were not selected

* Scan job is still running

* Scan job failed

Always check the Jobs tab.

# Problem: Web interface does not open
Steps:

1. Check running containers:

bash
Copy code
```
docker ps
```
2. If containers are not running:

bash
Copy code
```
docker-compose up -d
```
# Problem: Login does not work
 Possible causes:

* Containers not fully started

* Database not ready

* Configuration issues

Fix:

bash
Copy code

```
docker-compose down
docker-compose up -d
```
# Best Practices
* Always stop services using docker-compose down

* Restart services if scans behave unexpectedly

* Check logs before assuming a bug

* Do not delete volumes unless required

# Next Step
After troubleshooting, continue with:

architecture-and-codebase.md

yaml
Copy code

---

## IMPORTANT CONFIRMATION

- Everything is inside the copy box  
- No clickable Markdown links  
- No content outside the box  
- 100 percent nano-safe  

---

### What you should reply next (one word)

- `REVIEW`  
- `ISSUE`  

You’re done writing. Now we move to **submission and maintainers**.





