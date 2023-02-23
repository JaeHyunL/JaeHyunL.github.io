# systemd[1]: docker.socket: Failed with result 'service-start-limit-hi



```bash
oem@DESKTOP-VAPKAVE:/mnt/c/Users/lodics$ systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: failed (Result: exit-code) since Thu 2023-02-23 12:14:58 KST; 1min 50s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
    Process: 1085 ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock (c>
   Main PID: 1085 (code=exited, status=1/FAILURE)

Feb 23 12:14:58 DESKTOP-VAPKAVE systemd[1]: docker.service: Scheduled restart job, restart counter is>
Feb 23 12:14:58 DESKTOP-VAPKAVE systemd[1]: Stopped Docker Application Container Engine.
Feb 23 12:14:58 DESKTOP-VAPKAVE systemd[1]: docker.service: Start request repeated too quickly.
Feb 23 12:14:58 DESKTOP-VAPKAVE systemd[1]: docker.service: Failed with result 'exit-code'.
Feb 23 12:14:58 DESKTOP-VAPKAVE systemd[1]: Failed to start Docker Application Container Engine.
```

어느날 갑자기 WSL에서 작동하는 도커가 동작이 안된다. 

```bash
oem@DESKTOP-VAPKAVE:/mnt/c/Users/lodics$ sudo systemctl start docker
Job for docker.service failed because the control process exited with error code.
See "systemctl status docker.service" and "journalctl -xe" for details.
```



```bash
oem@DESKTOP-VAPKAVE:/mnt/c/Users/lodics$ journalctl -xe
-- Defined-By: systemd
-- Support: http://www.ubuntu.com/support
--
-- A start job for unit docker.service has finished with a failure.
--
-- The job identifier is 3121 and the job result is failed.
Feb 23 12:17:48 DESKTOP-VAPKAVE systemd[1]: docker.socket: Failed with result 'service-start-limit-hi>
-- Subject: Unit failed
-- Defined-By: systemd
-- Support: http://www.ubuntu.com/support
```



```bash
Feb 23 12:17:48 DESKTOP-VAPKAVE systemd[1]: docker.socket: Failed with result 'service-start-limit-hi>
```

위와 같은 로그가 뜨길래

```bash
 sudo rm /etc/docker/daemon.json
```

docekr daemon.json 파일을 지워고 재시작함.

```bash
 oem@DESKTOP-VAPKAVE:/mnt/c/Users/lodics$ sudo systemctl start docker.service
 
 oem@DESKTOP-VAPKAVE:/mnt/c/Users/lodics$ sudo systemctl  status docker.service
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Thu 2023-02-23 12:20:39 KST; 26s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 2463 (dockerd)
      Tasks: 17
     Memory: 47.2M
     CGroup: /system.slice/docker.service
             └─2463 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```

해결.