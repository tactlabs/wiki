## APK file Generation :

#### Use this link to set up an account on expo :-
```
https://expo.dev/signup
```

```
expo login
``` 

#### To check which user you are logged in with, use the command :-

``` 
expo whoami
``` 

#### Edit Config
If you want to add the app to the playstore. You should add "versionCode": 1 in app.json under "android".

```
"android":{
    
    "versionCode":1
}
```
#### Finally run the following command :-

```
expo build:android
```
#### Then select the following options on the terminal :-

- Select apk

- Select generate keystore


#### Download apk :-
- After the build is complete you can go to the builds section in your dashboard and download the apk.
