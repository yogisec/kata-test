
To build the images and start the services (containers) use the command below:

`docker-compose down`{{execute}}

Once both containers after a couple of moments we should see an output similar to the one below:

```
Stopping root_redis_1 ... done
Stopping root_web_1   ... done
Removing root_redis_1 ... done
Removing root_web_1   ... done
Removing network root_default
```

What is that last line `Removing network root_default`?
