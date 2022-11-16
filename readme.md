# Docker and Python

For this assignment you will be combining Docker with Python to create a program that generates a QR code PNG file that
contains a URL. The QR code can be viewed with the camera on your phone to allow a user to click on it and send them to
the target website. You must make your program generate a QR code that takes someone to the Docker Hub page for your
image. This assignment is not automatically graded by GitHub Classroom. You want to make it possible to change the QR
code by using environment variables that can be overriden in the docker-compose.yml file. You also want to make sure
that when you run the python script that it doesn't run as the root user. You will need to create a repository on
Dockerhub to push the Docker image that this project generates.

Submission Requirements:

1. QR code that links to your own project image on Dockerhub

Example:

* [My Project on Docker Hub QR Code](readme_images/docker_hub.png) <-view with your phone camera and click to go to the site

## Lesson Video

[Instructor Video](https://youtu.be/ATajsJRFWEs)

## Readings - No, really you should read these

* [Entrypoint vs. CMD vs. RUN ](https://codewithyury.com/docker-run-vs-cmd-vs-entrypoint/)
* [Make QR with Python](https://towardsdatascience.com/generate-qrcode-with-python-in-5-lines-42eda283f325)
* [Make Dockerfile](https://thenewstack.io/docker-basics-how-to-use-dockerfiles/)
* [Docker Compose File Basics](https://www.techrepublic.com/article/how-to-build-a-docker-compose-file/)
* [Why you don't run programs as root](https://bencane.com/2012/02/20/why-you-should-avoid-running-applications-as-root/)
* [Environment Variables in Python](https://www.nylas.com/blog/making-use-of-environment-variables-in-python/)
* [Args and Environment Variables in Docker](https://vsupalov.com/docker-arg-env-variable-guide/)
* [Docker Run Mount Local Windows Important Info](https://medium.com/@kale.miller96/how-to-mount-your-current-working-directory-to-your-docker-container-in-windows-74e47fa104d7)
* [How to run a program as another user in linux](https://unix.stackexchange.com/questions/232669/how-can-i-run-a-program-as-another-user-in-every-way)

## Bonus Task - Good Docker practice, it demonstrates using JavaScript / NodeJS

* https://docs.docker.com/get-started/

## Helpful Info

* https://echohack.medium.com/patterns-with-python-poll-an-api-832173a03e93
* https://stackoverflow.com/questions/2083987/how-to-retry-after-exception

## Code Photos

* [Dockerfile](readme_images/Dockerfile.png)
* [docker-compose.yml](readme_images/docker-compose.png)
* [main.py](readme_images/main_py.png)
* [config.py](readme_images/config_python.png)
* [qr_dode dunder init](readme_images/qr_creation_code.png) <-must make folder called "qrcodegenerator" and put the code
  in the __
  init__.py

## Command Reference - No Particular Order

* docker build -t kaw393939/python312 . <- builds image called "kaw393939/python312"
* docker run -it kaw393939/python312   <- Runs python type exit() to get out
* docker run -it kaw393939/python312 <- Runs the default main.py CMD in the dockerfile
* docker run -it kaw393939/python312 app.py  <-overrides cmd/command in dockerfile to run app.py instead
* docker compose up --build < runs the service defined through the docker-compose.yml file that tells it to build the
  Dockerfile
* docker compose up <- Runs the program but doesn't build a new image
* docker run --volume /Users/keithwilliams/Desktop/fall2022/qrprog/qr_generator_service/images:/home/myuser/images
  Note:  You need to build each time you change your dockerfile
* docker exec -it <container ID> bash allows you to login to the running container
* docker tag local-image:tagname new-repo:tagname <renames the image
* docker push new-repo:tagname <pushes the image to docker hub
* docker login <- login to dockerhub if it says access denied when you try to push
