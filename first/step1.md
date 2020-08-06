
First we need to build our python web application. Don't worry, the python code is already built for you. We just need to build out the docker file to build the container.

Using the editor in the top right of the screen select the `Dockerfile`{{open}} and copy or type the code below:

<pre class="file" data-filename="Dockerfile" data-target="replace">
FROM python:3.7-alpine
WORKDIR /code
ENV FLASK_APP app.py
ENV FLASK_RUN_HOST 0.0.0.0
RUN apk add --no-cache gcc musl-dev linux-headers
COPY ./app/requirements.txt requirements.txt
RUN pip install -r requirements.txt
COPY ./app .
CMD [&quot;flask&quot;, &quot;run&quot;]
</pre>

Overall, the dockerfile above is simple enough. It installs the required python packages, and then runs the flask web application. Notice that we are not specifying any ports to reach the web application. We'll cover that in the next step.


