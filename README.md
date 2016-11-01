# WebFileChecker-Magento-2.x

WebFileChecker extension / module for Magento-2.x / tool / checks detects modified / hacked files / configuration

E.g. why is there an error suddenly, has somebody files modified / hacked or was there an update from outside, what has a programmer / supplier modified, have you been hacked etc. Solution a Web File Checker / Detector or a Web Hacked Checker / Detector. Check your webstore on or detect modifications and configuration settings. Magento 1.x has about 15.000 files and 5000 directories, in Magento 2.x even more ..

Expect no support (too busy), recently tested in 1.8 and 1.9 but some questions can be answered here. But of course real errors will be corrected, but only communication via Q&A!

This program runs every day 2x as cronjob at 07.00 and 15.00 (can be changed in config.xml).

It checks always which Magento files have been modified since the last run. It also checks for changed configuration settings.

If modified you will receive a report per email, otherwise an empty email with subject. After the first run you receive all filenames and configuration settings (not really, more a link to your log the first time).

So you can check always what have been modified (by someone or an update) e.g. to solve errors.

This program can also be called in between from the browser with {url}/index.php/{admin}/webfilechecker (if your provider gives you enought time, if you have Scheduler you may start a cronjob immediately). This is only possible when you log off first from your administration, during the call you need to login. This prevents WebFileChecker to be called via your webstore.

In the protected /var/wfc directory you can find the WebFileChecker log with modifications on date. Or e.g. to clean this log after a long period.

Or press the button to view immeditely your modifications log (or {url}/index.php/{admin}/webfilechecker/view, first log off).

If you create a backup from these few files and later restore, you can determine the changes always again since your last backup! There are only 3 files in the protected /var/wfc directory: 1) ooa_wfc_ref.log (reference log files) 2) ooa_wfc_ref_conf.log (reference log configuration variables) 3) ooa_wfc_mod.log (changes compared to both reference logs). Through restoring 1) and 2) changes can be determined again. If you for example have been hacked, you can easily see which files have been modified!

PLease don't touch the reference logs, these logs are necessary for comparisations in a next run.

Languages Dutch and English.

So what do you need to do for this extension:
- check if your Magento cron job, cron.php / cron.sh is running
- check if you have enough time from your provider to run this program, normally it runs in 1-2 minutes but if your server is slow it can take up to 10 minutes
- create the directory var/wfc by yourself
- protect the directory /var/wfc with a user/password

Extension history:

Such a script was there already for OsCommerce (but more extensive). I tried then in 2013 to find such scripts for other webshops but nothing found. Then I found a snippet on the internet how you could easily determine if programs (files) were changed and used this for the WebFileChecker.
