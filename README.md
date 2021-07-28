<pre>
#!/bin/bash

# Used for backing up Frappe/ERPNext sites
# Adjust details and add as cron job on server to automate backups

# Script to backup all sites in Frappe Bench to GitHub  
# Switch to bench directory and
# Backup all sites with files to backup folder
# Backup files can be easily restored on a new frappe bench

# Backup Sites
# Add the following line for each site
# Backup location should hold local version of your git repository with backups
cd /opt/bench/erpnext && bench --site [site name] backup --with-files --compress --backup-path=[backup location] 


# Backup to https://github.com/[username]/[repository]    
# First add SSL (to avoid manually entering username and password) via github settings page
cd /opt/bench/backups && git remote set-url origin git@github.com:[username]/[repository].git && git add . && git commit -m "[your standard comment]" && git push origin main 
</pre>
