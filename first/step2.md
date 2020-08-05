### Docker Compose File:

Before we build our docker-compose.yml file. What is docker compose? According to the Docker, "Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration."

What does this mean? It means that we can create multiple services (containers) all with 1 command. For our example the compose file will be building the python image based on the parameters we previously defined in our Dockerfile, starting the image, and then finally it is spinning up a redis database image to store the total number of times someone has accessed our site.

Now we'll build out our docker-compose.yml file. Using the editor in the top right of the screen select the `docker-compose.yml`{{open}} and copy or type the code below:

<pre class="file" data-filename="docker-compose.yml" data-target="replace">
version: '3'
services:
  web:
    build: .
    ports:
      - "80:5000"
  redis:
    image: "redis:alpine"
</pre>
