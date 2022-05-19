## Building a URL Hashing System with FastAPI and MongoDB

🎉 The deployed app is available on [Heroku](https://url-hashgen.herokuapp.com/)

### To run the development server :-

- Install the dependencies

```
$ cd url-hash-gen
$ pip install -r requirements.txt
```

- Change .env.sample to .env and Edit the environment variables

- To run the uvicorn ASGI server :-

```
$ python main.py
```

- To deploy via Heroku :-

Ensure you have an Heroku account and you have created the app on the Heroku dashboard (https://heroku.com)

1. Add Procfile to run via gunicorn and uvicorn workers

```
web: gunicorn -w 1 -k uvicorn.workers.UvicornWorker main:app
```

2. Deploy on Heroku via heroku CLI

```
$ heroku create <app-name>
$ heroku git:remote -a <app-name>
$ git add .
$ git commit -m "Commit message"
$ git push heroku master
```

To view Heroku logs for a successful deployment :-

```
$ heroku logs --tail
```
