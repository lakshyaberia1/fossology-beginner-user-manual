# FOSSology Complete Beginner User Manual

From Git Clone to First Scan to Daily Usage to Troubleshooting
(Audience: Absolute beginners, zero prior knowledge assumed)

## 1. What is FOSSology and Why It Exists

### The real problem
Companies use open-source software in their products.
Open-source software comes with licenses (GPL, MIT, Apache, BSD, etc.).
If licenses are not handled correctly, it can cause:
- legal issues (lawsuits or violations)
- product release blocks
- compliance failures (audits or certifications fail)

### What FOSSology does
FOSSology is a free tool that:
- scans source code files
- detects licenses automatically
- finds copyrights, emails, and URLs
- highlights potential compliance risks

Important: FOSSology does not change or modify your code.
It only reads and analyzes it.

## 2. Big Picture Architecture (Understand Once, Everything Makes Sense)

Here is the official FOSSology architecture diagram:

![FOSSology Architecture Diagram](https://fossology.github.io/gsoc/assets/images/golang_arch-845b2fcaba867fd8c16c3061cf774283.png)

Browser
  |
Web UI (PHP-based interface)
  |
Scheduler (manages jobs like a queue)
  |
Agents / Scanners (the tools that actually read files)
  |
Database (PostgreSQL - stores all results)

### Simple meaning
- Web UI: what you see and click in the browser
- Scheduler: decides which scans run and when
- Agents: the "workers" that unpack files and detect licenses
- Database: saves everything so you can view reports later

Key points:
- The UI never scans files directly (it just sends jobs).
- Agents do all the heavy work in the background.

## 3. System Requirements

You need:
- Linux operating system (Ubuntu is recommended for beginners)
- Docker (version 20+ recommended)
- Docker Compose (version 2+)
- Git
- Stable internet connection (to download images first time)

Check if they are installed:
docker --version
docker-compose --version
git --version

If any command says "not found", install it first.

## 4. Getting FOSSology from Git (STEP-BY-STEP)

### Step 1: Open terminal
Open your terminal app (Ctrl+Alt+T on Ubuntu).

### Step 2: Clone FOSSology repository
git clone https://github.com/fossology/fossology.git

This downloads everything: source code, Docker files, agents, etc.
(It may take a few minutes.)

### Step 3: Enter directory
cd fossology

You should see files like:
- docker-compose.yml
- src/ folder
- README.md

## 5. Starting FOSSology (First Time)

### Step 1: Start containers
docker-compose up -d

- "-d" means run in background (detached mode).
- This starts: database, web server, scheduler, and agents.
First time takes 5-15 minutes (it downloads and builds images).

### Step 2: Check logs if needed
If something goes wrong:
docker-compose logs -f

(Press Ctrl+C to stop viewing logs.)

### Step 3: Verify everything is running
docker ps

You should see 3-4 containers running (like fossology_web, fossology_scheduler, fossology_db).

## 6. Opening the Web Interface

Open your web browser and go to:
http://localhost:8081/repo

Why /repo?
- http://localhost:8081/ shows a blank Apache page (this is normal).
- /repo is the real FOSSology application path.

## 7. Login and First Steps

### Default Login
Username: fossy
Password: fossy

This admin user is created automatically on first start.

Here is an example of what the interface looks like after login:

![FOSSology Main Interface](https://www.linuxfoundation.jp/wp-content/uploads/2017/09/FOSSology-screenshot-e1504819088560.png)

Important Security Tip:
After logging in, immediately change the password!
Go to Admin > Users > Edit User (your fossy user).

## 8. Your First Scan (Step-by-Step)

### Step 1: Upload your code
1. After login, click "Upload" in the top menu > "From File".
2. Choose a small test file or folder (e.g., download a small open-source project zip for testing).
3. Give it a name and description (optional).
4. Click "Upload".

Here is an example of the upload page:

![FOSSology Upload Page](https://user-images.githubusercontent.com/17740596/27568908-229554b0-5b27-11e7-9223-d651af39e8df.png)

### Step 2: Schedule a scan
1. Click "Browse" in the top menu to see your uploads.
2. Click on the name of your new upload.
3. Click "Schedule a Scan" (or "Job" > "Schedule Scan").
4. Select the agents you want:
   - Nomos: main license scanner (always select this)
   - Monk: better for bulk/diff detection
   - Ninka: another license scanner
   - Report: for generating reports later
5. Click "Schedule Scan".

Here is an example of the agent selection page:

![FOSSology Schedule Scan Agents](https://raw.githubusercontent.com/wiki/fossology/fossology/img/Bulk/BulkScan4.png)

### Step 3: Wait for the scan to finish
- Go to "Jobs" > "My Jobs" to see progress.
- Small files finish in minutes; large projects can take hours.

### Step 4: View results
1. Go back to "Browse", click your upload.
2. Click "License Browser" or "Clearing" to see detected licenses.
3. You will see a list of files with found licenses highlighted.

Here is an example of license scan results:

![FOSSology License Scan Results](https://user-images.githubusercontent.com/13619920/51901307-ebaf5800-23e9-11e9-93be-935ac305e6b9.png)

## 9. Daily Usage Tips

- Always upload code as zip/tar for folders.
- Use "From URL" to scan public GitHub repos directly.
- Generate reports: After scan, go to "Jobs" > "Report".
- Clear licenses: Manually review and mark obligations.

## 10. Troubleshooting (Common Issues)

- Containers not starting? Run docker-compose down then up -d again.
- Port 8081 already in use? Edit docker-compose.yml to change port.
- Scan stuck? Check "Jobs" > cancel and reschedule.
- No data after restart? For persistence, use external volume (advanced).

More help: Visit https://www.fossology.org or GitHub issues.

You now have a complete beginner guide! Save this as INSTALL.md or GUIDE.md in your repo.
