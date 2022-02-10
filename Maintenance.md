- client request

- w7-frontend: nginx /maintenance/$target pass to w7-microservice-maintenance

- w7-microservice-maintenance: 
  - check auth token and grants
  - attach "maintenance" access token
  - pass request to etg-maintenance

- etg-maintenance: nginx 
  - check allowed ip
  - validate access token
  - pass to etg-maintenance app

### Disk full

In order to remove all unused images not just dangling ones.
```bash
docker system prune -all
```



