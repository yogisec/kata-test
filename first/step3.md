
Lets build out our docker-compose.yml file. Using the editor in the top right of the screen select the `docker-compose.yml`{{open}} and copy or type the code below:

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

In the file above we specifiy two 'services' which will become our running containers. The first is the `web` service which instructs docker to use the `Dockerfile` located within the current directory to build the image. Additionally it also specifies that we want to expose port 80 to the host and then translate it to port 5000 within the container.

The `redis` service is the second service we are using. In this configuration we are simply pulling a prebuild redis image and running it with default options. Our python web application pulls the number of 'hits' from the redis database and then prints them to the browser window when we load the website.

How will the python web server container know how to reach the redis container?