/ [Home](index.md)

# PM2 Commands

**Note:** Let's run forever




Install PM2
```
npm install pm2 -g
```




```
pm2 start rjpm2_test.py --name trial1min --cron '*/1 * * * *' --no-autorestart

pm2 start trial.py --name trial1min --cron '*/1 * * * *' --no-autorestart

pm2 start abc.py --name abc --cron '*/1 * * * *' --no-autorestart

pm2 start abc.py --interpreter /Users/rajacsp/opt/anaconda3/envs/fpr/bin/python --name abc --cron '* 4 * * *' --no-autorestart

pm2 save

pm2 ps

pm2 flush
	(clear all logs)

pm2 stop 0

pm2 delete 0

pm2 save

pm2 save --force

pm2 -h

pm2 cron
  <minutes 0:60> <hour 0:24> <day of month 1:31> <month 1:12> <day of week 0:6>


```



### Ref :

  * [PM2](https://github.com/Cron-J/PM2)
  * [Automate your python script with pm2](https://towardsdatascience.com/automate-your-python-script-with-pm2-463238ea0b65)
  * [Cron Sample](https://crontab.guru/every-day-at-1am)


