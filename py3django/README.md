# Deploying Python3.6, Django 2.0.2 within Docker Containers

```
docker-compose run web django-admin.py startproject mysite . 
```

You will see something like that:

```
Building web
Step 1 : FROM python:3.6
Trying to pull repository docker.io/library/python ... 
3.6: Pulling from docker.io/library/python
f49cf87b52c1: Pull complete
7b491c575b06: Pull complete
b313b08bab3b: Pull complete
51d6678c3f0e: Pull complete
09f35bd58db2: Pull complete
0f9de702e222: Pull complete
73911d37fcde: Pull complete
99a87e214c92: Pull complete
Digest: sha256:98149ed5f37f48ea3fad26ae6c0042dd2b08228d58edc95ef0fce35f1b3d9e9f
 ---> c1e459c00dc3
Step 2 : ENV PYTHONUNBUFFERED 1
 ---> Running in 430c91591859
 ---> 8bdfa03bace2
Removing intermediate container 430c91591859
Step 3 : RUN mkdir /code
 ---> Running in 07b0bfd76258
 ---> dc67d4a4f3f1
Removing intermediate container 07b0bfd76258
Step 4 : WORKDIR /code
 ---> Running in 7baf212fa069
 ---> ecdf3c039f54
Removing intermediate container 7baf212fa069
Step 5 : ADD requirements.txt /code/
 ---> a12a75305512
Removing intermediate container 624a3bfd639e
Step 6 : RUN pip install -U pip     &&  pip install -r requirements.txt
 ---> Running in 05485c1a0f49
Requirement already up-to-date: pip in /usr/local/lib/python3.6/site-packages
Collecting Django==2.0.2 (from -r requirements.txt (line 1))
  Downloading Django-2.0.2-py3-none-any.whl (7.1MB)
Collecting pytz (from Django==2.0.2->-r requirements.txt (line 1))
  Downloading pytz-2018.3-py2.py3-none-any.whl (509kB)
Installing collected packages: pytz, Django
Successfully installed Django-2.0.2 pytz-2018.3
 ---> 22c3222273ac
Removing intermediate container 05485c1a0f49
Step 7 : ADD . /code/
 ---> ff151988b1e2
Removing intermediate container c572b4186709
Successfully built ff151988b1e2
WARNING: Image for service web was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.

```


With the command above you will create a directorie called mysite, a file as well called admin.py and a  db.sqlite3  


Notice this message:

```
WARNING: Image for service web was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
```

## Running ```the docker-compose up```


```
docker-compose up
```

