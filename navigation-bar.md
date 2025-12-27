# Understanding the FOSSology Navigation Bar

This document explains the FOSSology navigation bar in detail.  
It is written for absolute beginners who are using FOSSology for the first time.  
Understanding the navigation bar is the key to avoiding 90% of confusion!

Here is what the top navigation bar looks like (example from recent versions):

![FOSSology Top Navigation Bar Example](https://raw.githubusercontent.com/wiki/fossology/fossology/img/Bulk/BulkScan4.png)

(The bar is at the top: Home | Upload | Browse | Jobs | Organize | Admin | Search | Help - order may vary slightly by version)

## Overview of the Navigation Bar

The top navigation bar in FOSSology contains these main options:

- Home
- Upload
- Browse
- Jobs
- Organize
- Search
- Admin
- Help
- (Your username/logout on the right)

Each option has ONE specific job. Clicking the wrong one is the #1 beginner mistake.

## Home

### What it does
- Shows the welcome/dashboard page after login
- Displays system info or announcements

### When to use it
- First thing after login to confirm everything works
- To go back to a "safe" starting point

### Common beginner mistake
- Looking for your uploaded files or scan results here (they are NOT here!)

Important: Home is just a welcome page. No files or results shown.

## Upload

### What it does
- Lets you add new code/packages to FOSSology
- Options: From File, From URL, From Server, From VCS (Git/SVN)

Here is an example of the Upload menu:

![FOSSology Upload Options](https://wiki.fossology.org/_media/036_oss_fossy_20160909_screenshot_monk_highlight_example.png?w=800)

### When to use it
- Every time you want to scan new source code

### Common beginner mistake
- Uploading and waiting for results immediately (NO auto-scan!)

Important: Upload ONLY stores the files. You must schedule a scan separately.

## Browse

### What it does
- File explorer for your uploaded projects
- Shows folder tree + scan results (licenses per file)

Here is an example of the Browse/License Browser page:

![FOSSology Browse and License Results](https://user-images.githubusercontent.com/13619920/51901307-ebaf5800-23e9-11e9-93be-935ac305e6b9.png)

### When to use it
- To see what licenses were found
- To drill down into files and folders

### Common beginner mistake
- Thinking "Browse" means browsing the web

Important: This is YOUR uploaded code explorer.

## Jobs

### What it does
- Shows all running/queued/completed scans
- Progress bar + logs for each job

Here is an example of the Jobs page:

![FOSSology Jobs Page](https://user-images.githubusercontent.com/22311928/65870565-657e5380-e374-11e9-8b71-045d0eedb417.png)

### When to use it
- ALWAYS check here while waiting for scans
- To see why a scan failed (error messages)

### Common beginner mistake
- Ignoring Jobs when "nothing happens"

Important: If scan is stuck → Jobs tells you why.

## Organize

### What it does
- Folders → Create/manage folders
- Uploads → Move, rename, delete existing uploads
- Tags → Label projects

### When to use it
- When you have many projects and need organization

### Common beginner mistake
- Trying to upload new files here (use Upload instead)

Important: Organize works only on already-uploaded items.

## Search

### What it does
- Full-text search across ALL scan results
- Find specific licenses, copyrights, file paths

### When to use it
- After many scans → "Where is GPL used?"
- Quick global search

### Common beginner mistake
- Using Search before any scans (nothing to search!)

Important: Search needs completed scan data.

## Admin

### What it does
- User management
- License clearing decisions
- Scheduler configuration
- Maintenance tasks

Here is an example Admin section:

![FOSSology Admin Configuration](https://user-images.githubusercontent.com/10155976/195266959-0ab5ca93-cc7e-4d27-84de-2bdafa72b4a7.PNG)

### When to use it
- Only if you are the admin
- To add users or change settings

### Common beginner mistake
- Clicking random Admin options

Warning: Wrong changes can break FOSSology!

## Help

### What it does
- Links to official docs
- About → Version info

### When to use it
- Always! Read the built-in help first

### Common beginner mistake
- Googling randomly instead of using official Help

## Typical Beginner Workflow (Follow This Order!)

1. Upload → Add your code
2. Jobs → Schedule scan + watch progress
3. Browse → View detailed results
4. Search → Find specific things across projects
5. Organize → Clean up folders (optional)

Follow this = zero confusion!

## Summary Table

| Menu     | Purpose                          | Use When...                     | Don't Use For...             |
|----------|----------------------------------|---------------------------------|------------------------------|
| Home     | Welcome page                     | Just logged in                  | Viewing results              |
| Upload   | Add new code                     | Starting new analysis           | Scanning (separate step)     |
| Browse   | Explore files + licenses         | Seeing scan results             | Uploading                    |
| Jobs     | Track scan progress              | Waiting for results             | Ignore if stuck!             |
| Organize | Manage folders/uploads           | Many projects                   | New uploads                  |
| Search   | Global search in results         | Finding specific licenses       | Before scans                 |
| Admin    | System settings                  | Admin tasks only                | Everyday use                 |
| Help     | Documentation                    | Need more info                  | Ignore                       |

## What to Read Next

After mastering the navigation bar:
upload-and-scan.md

""This explains how to upload code and run your first scan.""

