# Restarting and Troubleshooting FOSSology

This document explains how to safely restart FOSSology
and how to troubleshoot common problems faced by beginners.

This guide assumes FOSSology is running using Docker.

---

## Important Concept

Closing the browser does NOT stop FOSSology.

FOSSology runs inside Docker containers in the background.
The browser is only used to access the web interface.

---

## Restart and Reopen Scenarios

Many beginners confuse browser close, terminal close,
system restart, and Docker restart.
These are different actions.

This section explains each case clearly.

---

## Case 1: You closed the browser

Nothing is stopped.

FOSSology is still running in Docker.

To open it again:
- Open a browser
- Go to:

http://localhost:8081/repo

No terminal command is required.

---

## Case 2: You closed the terminal

Closing the terminal does NOT stop Docker containers.

FOSSology continues running in the background.

To continue working:
- Open a new terminal
- Go to your project directory

```bash
cd fossology-beginner-user-manual
Case 3: You restarted or shut down the computer
When the system restarts, Docker containers usually stop.

You must start FOSSology again manually.

Steps:

bash
Copy code
cd fossology-beginner-user-manual
docker-compose up -d
Then open:

http://localhost:8081/repo

Case 4: You want to restart only FOSSology (recommended fix)
If scans fail or the UI behaves incorrectly,
restart FOSSology services only.

This is safe and does NOT delete data.

bash
Copy code
docker-compose down
docker-compose up -d
This restarts:

Web interface

Scheduler

Agents

Database connections

Case 5: You want to stop FOSSology safely
To stop all FOSSology services:

bash
Copy code
docker-compose down
This command:

Stops containers

Keeps uploads and database safe

Does NOT delete data

Case 6: Full reset (use with caution)
This removes ALL data.

bash
Copy code
docker-compose down -v
This deletes:

Uploaded files

Database

Scan results

Use this only if you want a fresh installation.

Understanding Errors
The web interface may show messages such as:

Job failed

This message does NOT explain the real reason.

The actual reason is available in logs.

Viewing Logs
To view Docker logs:

bash
Copy code
docker-compose logs -f
Logs help identify:

Agent failures

Scheduler errors

Configuration problems

Permission issues

Press CTRL + C to stop viewing logs.

Common Problems and Fixes
Problem: Scan job failed
Steps:

Open the Jobs tab in the UI

Read the error message

Check logs using docker-compose logs -f

Problem: Uploaded file but no scan results
Possible causes:

Analysis agents were not selected

Scan job is still running

Scan job failed

Always verify job status in the Jobs tab.

Problem: Web interface does not open
Steps:

Check running containers:

bash
Copy code
docker ps
If containers are not running:

bash
Copy code
docker-compose up -d
Problem: Login does not work
Possible causes:

Containers not fully started

Database not ready

Configuration issues

Fix:

bash
Copy code
docker-compose down
docker-compose up -d
Performance and System Load Note
High CPU or memory usage is usually caused by:

Multiple Docker containers running

Large scans

Low system RAM

This is NOT hacking and NOT a security issue.

To reduce load, stop services when not needed:

bash
Copy code
docker-compose down
Restart only when required.

Best Practices
Always stop services using docker-compose down

Restart services if scans behave unexpectedly

Check logs before assuming a bug

Do not delete volumes unless required

