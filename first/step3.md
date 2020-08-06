### Docker Compose File

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

In the file above we specifiy two 'services' which will become our running containers. The first is the `web` service which instructs docker to use the files within the currently directory