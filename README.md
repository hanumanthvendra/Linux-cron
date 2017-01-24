# Linux-cron

				AUTOMATIC JOBS


	As a system administrator some tasks are respective like backup, monitoring, log files.
	To automate them with the help of 
1)at 
2)batch
3)crontab
Crontab:to run some tasks automatically 
to set a crontab for an user
#crontab -e -u <user name>
* * * * * /bin/echo "hello"
A crontab file contains instructions to the cron deamon of the general form 
"run this command at this time on this date"
Cron examines entries once every minute

 field          allowed values
              -----          --------------
              minute         0-59
              hour           0-23
              day of month   1-31
              month          1-12 (or names, see below)
              day of week    0-7 (0 or 7 is Sun, or use names)

       A field may be an asterisk (*), which always stands for ‘‘first-last’’.

       Ranges  of  numbers  are allowed.  Ranges are two numbers separated with a
       hyphen.  The specified range is  inclusive.   For  example,  8-11  for  an
       ‘‘hours’’ entry specifies execution at hours 8, 9, 10 and 11.

       Lists  are  allowed.   A list is a set of numbers (or ranges) separated by
       commas.  Examples: ‘‘1,2,5,9’’, ‘‘0-4,8-12’’.


EXAMPLE CRON FILE
       # use /bin/sh to run commands, no matter what /etc/passwd says
       SHELL=/bin/sh
       # mail any output to ‘paul’, no matter whose crontab this is
       MAILTO=paul
       #
       # run five minutes after midnight, every day
       5 0 * * *       $HOME/bin/daily.job >> $HOME/tmp/out 2>&1
       # run at 2:15pm on the first of every month -- output mailed to paul
       15 14 1 * *     $HOME/bin/monthly
       # run at 10 pm on weekdays, annoy Joe
       0 22 * * 1-5   mail -s "It’s 10pm" joe%Joe,%%Where are your kids?%
       23 0-23/2 * * * echo "run 23 minutes after midn, 2am, 4am ..., everyday"
       5 4 * * sun     echo "run at 5 after 4 every sunday"


To set a crontab for an user
#crontab -e -u <user name>
ex:crontab -e -u alex

To remove a crontab for an user
#crontab -r -u <user name>
ex:crontab -r -u alex
