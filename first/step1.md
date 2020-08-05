### Building Web Application Container

To see a list of runing containers run the following command:

<pre class="file" data-filename="Dockerfile" data-target="replace">
FROM python:3.7-alpine
WORKDIR /code
ENV FLASK_APP app.py
ENV FLASK_RUN_HOST 0.0.0.0
RUN apk add --no-cache gcc musl-dev linux-headers
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
EXPOSE 5000
COPY . .
CMD [&quot;flask&quot;, &quot;run&quot;]
</pre>




### Docker Compose File:


<pre class="file" data-filename="Dockerfile" data-target="replace">
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
</pre>