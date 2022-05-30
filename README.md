# deploy-djang-in-ngnix-gunicorn
At the very least serve it off gunicorn:

$ pip install gunicorn
$ cd your_project
$ gunicorn project.wsgi  # gunicorn now runs locally on port 8000
And have nginx (or apache) as a reverse proxy:

server {
    location / {
        proxy_pass http://127.0.0.1:8000;
    }
}
Deploying Django (just like any other application) is a world in and of itself, and mastering it takes time. But don't ever run the development server in production
