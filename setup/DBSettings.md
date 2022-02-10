# W7 - DB Configuration outside Docker container
## Bind a directory on the host machine into a container

- Add mount Docker's command on settings release section *`settings.js`*, both to run and to rollback actions.

  > Syntax of command:  `--mount type=bind,source={{path_host}},target={{path_container}}`
  
  ```
  run: [{
         cmd: 'ssh',
         args: [
             ...
             --mount type=bind,source=/home/ubuntu/w7app/configs,target=/app/configs
             ....
         ]
     }],
     rollback: [{
         cmd: 'ssh',
         args: [
             ...
             --mount type=bind,source=/home/ubuntu/w7app/configs,target=/app/configs
             ....
         ]
     }]
  ```



- Set file's name of configuration on *`settings.js`*; for example:

  ```javascript
  settings.configUrl = '../configs/w7-micro-db'
  ```



- Create on the host machine the resource `/home/ubuntu/w7app/configs/w7-micro-db.js` in relation of `configUrl` seen in the previous point; for example:

  ```javascript
  const db = {
    own: null,
    data: { v2: null },
  }
  
  db.data.v2 = {
    connection: {
      host: 'localhost',
      database: 'w7Meteo',
      user: 'admin',
      password: '****'
    }
  }
  
  db.own = {
    connection: {
      user: 'admin',
      host: 'localhost',
      database: 'w7User',
      password: '***'
    }
  }
  
  module.exports = db
  
  ```

- see a working example in `w7-microservice-db` and `settings.release` in `w7-microservice-db/settings/_root.js`
