
To build the images and start the services (containers) use the command below:

`docker-compose up -d`{{execute}}

Once both containers are up and running we should see an output such as the one below:

```
Creating root_web_1   ... done
Creating root_redis_1 ... done
```

We should now be able to browse to our website:
Click https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com

With each refresh the counter should increment.

