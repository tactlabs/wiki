# Tempalte

**Note:** tbw




```
heroku logs app_name --tail

heroku logs --source app

heroku login

heroku addons:create heroku-postgresql:hobby-dev

heroku addons

heroku pg:info

heroku addons:create heroku-postgresql:<PLAN_NAME> --version=9.5
	https://devcenter.heroku.com/articles/heroku-postgresql#provisioning-heroku-postgres
	
ssh on Heroku
heroku ps:exec
	https://devcenter.heroku.com/articles/exec
	
heroku ps:copy filename

heroku ps:copy /app/db/yt_analytics.db -a youtics

heroku request time limit?
30 s
	https://devcenter.heroku.com/articles/request-timeout

```

# Ref :

  * [Heroku CLI Commands](https://devcenter.heroku.com/articles/heroku-cli-commands)
