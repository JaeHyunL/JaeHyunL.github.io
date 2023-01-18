# uvicorn-gunicorn-fastapi-docker

NotFoundModule Error 라는 문구가 대충 떳다,,



```
oem@DESKTOP-VAPKAVE:/mnt/d/workspace/FastAPI_template$ docker logs -f 845c
Checking for script in /app/prestart.sh
Running script /app/prestart.sh
Running inside /app/prestart.sh, you could add migrations to this file, e.g.:

#! /usr/bin/env bash

# Let the DB start
sleep 10;
# Run migrations
alembic upgrade head

[2023-01-18 02:59:17 +0000] [1] [INFO] Starting gunicorn 20.1.0
[2023-01-18 02:59:17 +0000] [1] [INFO] Listening at: http://0.0.0.0:80 (1)
[2023-01-18 02:59:17 +0000] [1] [INFO] Using worker: uvicorn.workers.UvicornWorker
[2023-01-18 02:59:17 +0000] [7] [INFO] Booting worker with pid: 7
[2023-01-18 02:59:17 +0000] [8] [INFO] Booting worker with pid: 8
[2023-01-18 02:59:17 +0000] [9] [INFO] Booting worker with pid: 9
[2023-01-18 02:59:17 +0000] [7] [ERROR] Exception in worker process
Traceback (most recent call last):
  File "/usr/local/lib/python3.11/site-packages/gunicorn/arbiter.py", line 589, in spawn_worker
    worker.init_process()
  File "/usr/local/lib/python3.11/site-packages/uvicorn/workers.py", line 66, in init_process
    super(UvicornWorker, self).init_process()
  File "/usr/local/lib/python3.11/site-packages/gunicorn/workers/base.py", line 134, in init_process
    self.load_wsgi()
  File "/usr/local/lib/python3.11/site-packages/gunicorn/workers/base.py", line 146, in load_wsgi
    self.wsgi = self.app.wsgi()
                ^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/base.py", line 67, in wsgi
    self.callable = self.load()
                    ^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/wsgiapp.py", line 58, in load
    return self.load_wsgiapp()
           ^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/wsgiapp.py", line 48, in load_wsgiapp
    return util.import_app(self.app_uri)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/util.py", line 359, in import_app
    mod = importlib.import_module(module)
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/importlib/__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "<frozen importlib._bootstrap>", line 1206, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1178, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1149, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 690, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 940, in exec_module
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "/app/main.py", line 6, in <module>
    from app.api.api_v1.api import api_router
ModuleNotFoundError: No module named 'app'
[2023-01-18 02:59:17 +0000] [8] [ERROR] Exception in worker process
Traceback (most recent call last):
  File "/usr/local/lib/python3.11/site-packages/gunicorn/arbiter.py", line 589, in spawn_worker
    worker.init_process()
  File "/usr/local/lib/python3.11/site-packages/uvicorn/workers.py", line 66, in init_process
    super(UvicornWorker, self).init_process()
  File "/usr/local/lib/python3.11/site-packages/gunicorn/workers/base.py", line 134, in init_process
    self.load_wsgi()
  File "/usr/local/lib/python3.11/site-packages/gunicorn/workers/base.py", line 146, in load_wsgi
    self.wsgi = self.app.wsgi()
                ^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/base.py", line 67, in wsgi
    self.callable = self.load()
                    ^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/wsgiapp.py", line 58, in load
    return self.load_wsgiapp()
           ^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/wsgiapp.py", line 48, in load_wsgiapp
    return util.import_app(self.app_uri)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/util.py", line 359, in import_app
    mod = importlib.import_module(module)
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/importlib/__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "<frozen importlib._bootstrap>", line 1206, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1178, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1149, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 690, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 940, in exec_module
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "/app/main.py", line 6, in <module>
    from app.api.api_v1.api import api_router
ModuleNotFoundError: No module named 'app'
[2023-01-18 02:59:17 +0000] [8] [INFO] Worker exiting (pid: 8)
[2023-01-18 02:59:17 +0000] [7] [INFO] Worker exiting (pid: 7)
{"loglevel": "info", "workers": 12, "bind": "0.0.0.0:80", "graceful_timeout": 120, "timeout": 120, "keepalive": 5, "errorlog": "-", "accesslog": "-", "workers_per_core": 1.0, "use_max_workers": null, "host": "0.0.0.0", "port": "80"}
{"loglevel": "info", "workers": 12, "bind": "0.0.0.0:80", "graceful_timeout": 120, "timeout": 120, "keepalive": 5, "errorlog": "-", "accesslog": "-", "workers_per_core": 1.0, "use_max_workers": null, "host": "0.0.0.0", "port": "80"}
[2023-01-18 02:59:17 +0000] [10] [INFO] Booting worker with pid: 10
[2023-01-18 02:59:17 +0000] [9] [ERROR] Exception in worker process
Traceback (most recent call last):
  File "/usr/local/lib/python3.11/site-packages/gunicorn/arbiter.py", line 589, in spawn_worker
    worker.init_process()
  File "/usr/local/lib/python3.11/site-packages/uvicorn/workers.py", line 66, in init_process
    super(UvicornWorker, self).init_process()
  File "/usr/local/lib/python3.11/site-packages/gunicorn/workers/base.py", line 134, in init_process
    self.load_wsgi()
  File "/usr/local/lib/python3.11/site-packages/gunicorn/workers/base.py", line 146, in load_wsgi
    self.wsgi = self.app.wsgi()
                ^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/base.py", line 67, in wsgi
    self.callable = self.load()
                    ^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/wsgiapp.py", line 58, in load
    return self.load_wsgiapp()
           ^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/app/wsgiapp.py", line 48, in load_wsgiapp
    return util.import_app(self.app_uri)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/gunicorn/util.py", line 359, in import_app
    mod = importlib.import_module(module)
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/importlib/__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "<frozen importlib._bootstrap>", line 1206, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1178, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1149, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 690, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 940, in exec_module
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "/app/main.py", line 6, in <module>
    from app.api.api_v1.api import api_router
ModuleNotFoundError: No module named 'app'
[2023-01-18 02:59:17 +0000] [9] [INFO] Worker exiting (pid: 9)
{"loglevel": "info", "workers": 12, "bind": "0.0.0.0:80", "graceful_timeout": 120, "timeout": 120, "keepalive": 5, "errorlog": "-", "accesslog": "-", "workers_per_core": 1.0, "use_max_workers": null, "host": "0.0.0.0", "port": "80"}
[2023-01-18 02:59:17 +0000] [11] [INFO] Booting worker with pid: 11
[2023-01-18 02:59:17 +0000] [1] [WARNING] Worker with pid 11 was terminated due to signal 15
[2023-01-18 02:59:17 +0000] [1] [WARNING] Worker with pid 7 was terminated due to signal 15
[2023-01-18 02:59:17 +0000] [1] [WARNING] Worker with pid 9 was terminated due to signal 15
[2023-01-18 02:59:17 +0000] [1] [WARNING] Worker with pid 10 was terminated due to signal 15
[2023-01-18 02:59:17 +0000] [1] [INFO] Shutting down: Master
[2023-01-18 02:59:17 +0000] [1] [INFO] Reason: Worker failed to boot.
{"loglevel": "info", "workers": 12, "bind": "0.0.0.0:80", "graceful_timeout": 120, "timeout": 120, "keepalive": 5, "errorlog": "-", "accesslog": "-", "workers_per_core": 1.0, "use_max_workers": null, "host": "0.0.0.0", "port": "80"}
```

하 ... 딱봐도 경로가 꼬인것 같은데

내 폴더 경로가 

<img src=https://user-images.githubusercontent.com/48937399/213076790-913e49a8-d9ff-490a-aa82-2872dc880060.png />

이렇게 되어잇다.

짐작하기로는  

```dockerfile
FROM tiangolo/uvicorn-gunicorn:python3.11

LABEL maintainer="Sebastian Ramirez <tiangolo@gmail.com>"

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY ./app /app
```

에 App 밑에 app이 두번들어가서 경로 충돌? 을 일으킨것 같다.

```dockerfile
FROM tiangolo/uvicorn-gunicorn:python3.11

LABEL maintainer="Sebastian Ramirez <tiangolo@gmail.com>"

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY ./ /app
```

으로 수정하니까 작동한다 .. (희한하다...???)

디렉토리 명을 건드리고 싶지 않으면

```dockerfile
FROM tiangolo/uvicorn-gunicorn:python3.11

LABEL maintainer="Sebastian Ramirez <tiangolo@gmail.com>"

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY ./app /app_reload
WORKDIR /app_reload
```

이런식으로 우회를 하는것도 방법이다.