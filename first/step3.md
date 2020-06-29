# Stop the container

We can stop the container by referencing its name:
```
docker stop shell
```

Now when we check the running processes:
```
docker ps
```

its gone!

But if we run

```
docker ps -a
```

we can see that it is just stopped

# start the container

```
docker start <container ID>
```


Now when we run docker ps the container is back up again!

```
docker ps
```

# stop it again

```
docker stop shell
```

And now remove the container with:

```
docker rm shell
```

