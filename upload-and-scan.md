# Uploading Code and Running Scans in FOSSology

This document explains how to upload source code into FOSSology
and run license scans correctly.

This is the most important part of using FOSSology.

---

## Important Concept: Upload Is Not the Same as Scan

Many beginners think that uploading a file automatically scans it.

This is incorrect.

- Upload means storing files in FOSSology
- Scan means analyzing files using agents

A scan will not run unless you explicitly select analysis options.

---

## Supported Upload Methods

FOSSology supports multiple ways to upload code:

- Upload from File (ZIP archive)
- Upload from URL
- Upload from Version Control System (VCS)

For beginners, Upload from File is recommended.

---

## Uploading a ZIP File (Recommended for Beginners)

### Step 1: Go to Upload Menu

From the navigation bar, click:

Upload

---

### Step 2: Select Upload from File

Choose the option to upload a file from your local system.

---

### Step 3: Select a ZIP Archive

- Choose a ZIP file containing source code
- Make sure the ZIP file is not password-protected

After selecting the file, proceed to the next step.

---

## Selecting Analysis Agents

Agents are the programs that analyze uploaded files.

Without agents, no scanning happens.

---

### Commonly Used Agents for Beginners

- Nomos  
  Fast license detection

- Monk  
  Deep license matching and confirmation

- Copyright  
  Detects copyright statements and authors

For most beginner use cases, selecting these agents is sufficient.

---

## Starting the Scan

After selecting agents:

- Confirm the upload
- Start the analysis job

FOSSology will now:
- Create a scan job
- Queue it in the scheduler
- Execute agents one by one

This process may take time depending on file size.

---

## Monitoring Scan Progress

### Using the Jobs Tab

To check scan progress:

- Click Jobs in the navigation bar
- Look for your running job

Job states include:
- Running
- Completed
- Failed

If a job fails, the Jobs tab will provide error details.

---

## Viewing Scan Results

After the job completes successfully:

1. Go to Browse
2. Open your uploaded project
3. Navigate through folders and files
4. Open license reports

FOSSology shows:
- Detected licenses
- File paths
- License confidence information

---

## Understanding the Results

Important points:
- One file may contain multiple licenses
- Some licenses may require manual review
- Unknown licenses should be investigated carefully

FOSSology provides information to help make compliance decisions,
but final responsibility remains with the user.

---

## Common Beginner Problems

### Uploaded file but no results appear

Possible reasons:
- No agents were selected
- Scan job is still running
- Scan job failed

Check the Jobs tab to confirm status.

---

### Scan job failed

Steps to take:
1. Open the Jobs tab
2. Read the error message
3. Check logs if needed

Logs can be viewed using:

```bash
docker-compose logs -f
