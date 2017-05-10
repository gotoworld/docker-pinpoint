# Docker Pinpoint

Docker for [Pinpoint](https://github.com/naver/pinpoint). 

## About

All versions of Docker run on Debian (jessie). Minimal requirements are installed, `git`, `wget`, `curl`, `ps`, `netstat`.

### 1.6.1

- Oracle Java SE 6, 7 and 8 with `JAVA_6_HOME`, `JAVA_7_HOME`, `JAVA_8_HOME` and `JAVA_HOME`
- Maven 3.5.0
- HBase 1.1.0



## Quickstart

``` sh
docker run -i -t -p 28080-28082:28080-28082 --cap-add SYS_PTRACE \
yous/pinpoint:1.6.0 bash
```

`--cap-add SYS_PTRACE` is needed for `netstat -anp` for displaying its PID with the program name. 

### Starting

#### Start HBase

- Start: `quickstart/bin/start-hbase.sh`
- Initialize Tables: `quickstart/bin/init-hbase.sh`

#### Start Pinpoint Daemons

- Collector: `quickstart/bin/start-collector.sh`
- Web UI: `quickstart/bin/start-web.sh`
- TestApp: `quickstart/bin/start-testapp.sh`

Visit the following addresses to test out your Pinpoint instance.

- Web UI: `http://localhost:28080`
- TestApp: `http://localhost:28081`

### Stopping

- HBase: `quickstart/bin/stop-hbase.sh`
- Collector: `quickstart/bin/stop-collector.sh`
- Web UI: `quickstart/bin/stop-web.sh`
- TestApp: `quickstart/bin/stop-testapp.sh`

