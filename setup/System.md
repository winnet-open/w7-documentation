# W7 - Setup System

### Requirements

#### Docker

- Install Docker (ubuntu 18, see [setup/Docker.md](setup/Docker.md)) and login to hub (may also register on https://hub.docker.com)

  ```bash
  sudo docker login
  user etgdocker
  pass: ETGservice2018
  ```

#### PostgreSQL
  DOCUMENTAZIONE SU https://www.postgresql.org/download/linux/ubuntu/


- Install `postgresql`, version 9 or 10 and enable user login
  sudo apt-get install postgresql postgresql-contrib




- add user, database db and run sql script to initialize the database
  ```bash
  sudo su postgres -c "psql -c \"CREATE ROLE w7 SUPERUSER LOGIN PASSWORD 'w7-project'\" "
  sudo su postgres -c "psql -c \"CREATE DATABASE w7 WITH ENCODING='UTF8' OWNER=w7 CONNECTION LIMIT=-1;\" "
  sudo su postgres -c "psql -d w7 -f sys/sql/0-init.sql"
  ```
  
  note `sys/sql/0-init.sql` is in `w7-microservice-db`


- se si deve ripristirnare un DB remoto su IPHOST
```bash
pg_dumpall -h localhost -p 5432 -U postgres -v --globals-only -f users.sql
pg_dump -h IPHOST -U etg -d w7 -c -C >w7.sql
psql -f w7.sql  -h 127.0.0.1 -U etg
```

#### Release automation

- Automate login to remote server
  - sulla macchina dalla quale ci vogliamo collegare lanciare i seguenti comandi:
  ```bash
    ssh-keygen -f %NOMECERTIFICATO%
    ssh-copy-id -i %PATHNOMECERTIFICATO% myuser@serverremoto
  ```
  - option: ``ssh-copy-id`` to server
    ```bash
    ssh-keygen
    ssh-copy-id -i ~/.ssh/id_rsa myuser@server
    ```

  - option: use public pem (for example on Amazon)
    ```bash
    ssh -i /home/myuser/keys/server.pem ubuntu@server
    ```

- Enable `sudo` to `myuser` without password on server (on Amazon is already enabled)

  ```bash
  # in /etc/sudoers.d/myuser
  myuser ALL=(ALL) NOPASSWD: ALL
  ```

- Install docker locally (debian 8, see [setup/Docker.md](setup/Docker.md)) and login to hub

  ```bash
  sudo docker login
  ```

- clone `w7-release` locally 

- install `node.js` locally v. > 8 and run `npm install` from `w7-release` directory
- install angular-cli `sudo npm install -g @angular/cli`


#### Post Installation

- populate `layers` table