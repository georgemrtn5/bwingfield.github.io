---
layout:     post
title:      Simple hard drive mirroring in Linux
date:       11-08-2015 11:00:00
summary:    Automatically mirroring two external hard drives with rsync and cron

---


I recently bought two 3TB external hard drives to temporarily store lots of data
for work locally while waiting for a more permanent solution. I used `rsync` to
mirror one external hard drive to the other and
[cron](https://en.wikipedia.org/wiki/Cron) to automate this process.

You might want to run this in a terminal first to see if it works:

`rsync -xavHl --delete /media/first-hard-drive-here /media/second-hard-drive-here`

I then automated the process by running it as a daily cron job. Run `crontab -e`
in a terminal and add the following lines to the bottom of the file: 

`MAILTO="email@example.com"`

`5 0 * * * rsync -xavHl --delete /media/sb00682400/BIG /media/sb00682400/DATA > /dev/null`

This will run at 5 minutes past midnight daily. The `>` at the end deletes
STDOUT (i.e. a successful run). STDERR (i.e. a failed run) will notify you via
`mail`. It is quite useful to have these notifications
[emailed to you](http://www.webupd8.org/2009/11/use-gmail-to-send-emails-from-terminal.html).  

Bad things can happen if you a cron job hasn't finished executing and it runs
again. For example, if this job runs every minute mirroring 1TB of data would
fail (it would take longer than a minute for the job to complete).

This was put together after reading the following sources:

* [http://ubuntuforums.org/showthread.php?t=1760718](http://ubuntuforums.org/showthread.php?t=1760718)
* [http://serverfault.com/questions/54152/how-to-get-e-mail-from-failed-cron-jobs-in-ubuntu](http://serverfault.com/questions/54152/how-to-get-e-mail-from-failed-cron-jobs-in-ubuntu)
