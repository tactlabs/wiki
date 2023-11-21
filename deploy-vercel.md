/ [Home](index.md)

# Deploy a flask app with Vercel

### Flask app

- create a folder named "api"
- create "requirements.txt" file and "vercel.json" file
- create "app.py" and templates folder
- templates => html files( for example, index.html)
- use the following template for vercel.json file:
    ```
    {
    "rewrites": [
      { 
          "source": "/(.*)", "destination": "/api/app.py" 
      }
    
        ] 
    }
    ```

### Git push

- Run your flask app in local system
- Git push your project

### Login to vercel

```
https://vercel.com
```
- Create an account in vercel and login to the page
- Continue with Github and allow github authentication.
- Select only specfic repositories and import 
- Set a Domain name and click Deploy
- The deploy logs will be displayed and any error while deployment will be shown.

### Congratulations! You have Deployed your flask app.