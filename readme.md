# Docker and Python

For this assignment you will be combining Docker with Python to create an image that generates a QR code PNG file
contains a URL. The QR code can be used with the camera on your phone to allow a user to click on it to send the user to
the target website. You must make your program generate a QR code that takes someone to your GitHub account homepage.
You need upload the QR code to Canvas and put a link to your own repository in Canvas. This assignment is not
automatically graded by GitHub Classroom. You want to make it possible to change the QR code by using environment
variables that can be overriden in the docker-compose.yml file.

## Video

## Readings

* [Entrypoint vs. CMD vs. RUN ](https://codewithyury.com/docker-run-vs-cmd-vs-entrypoint/)
* [Make QR with Python](https://towardsdatascience.com/generate-qrcode-with-python-in-5-lines-42eda283f325)
* [Make Dockerfile](https://thenewstack.io/docker-basics-how-to-use-dockerfiles/)
* [Docker Run Mount Local Windows Important Info](https://medium.com/@kale.miller96/how-to-mount-your-current-working-directory-to-your-docker-container-in-windows-74e47fa104d7)

## Helpful Info

* https://echohack.medium.com/patterns-with-python-poll-an-api-832173a03e93
* https://stackoverflow.com/questions/2083987/how-to-retry-after-exception

## Code Photos

* [Dockerfile](Dockerfile.png)
* [docker-compose.yml](docker-compose.png)
* [main.py](main_py.png)
* [config.py](config_python.png)
* [qr_dode dunder init](qr_creation_code.png) <-must make folder called "qrcodegenerator" and put the code in the __
  init__.py

## Command Reference - No Particular Order

* docker build -t kaw393939/python312 . <- builds image called "kaw393939/python312"
* docker run -it kaw393939/python312   <- Runs python type exit() to get out
* docker run -it kaw393939/python312 <- Runs the default main.py CMD in the dockerfile
* docker run -it kaw393939/python312 app.py  <-overrides cmd/command in dockerfile to run app.py instead
* docker compose up --build < runs the service defined through the docker-compose.yml file that tells it to build the
  Dockerfile
* docker run --volume /Users/keithwilliams/Desktop/fall2022/qrprog/qr_generator_service/images:/home/myuser/images
  Note:  You need to build each time you change your dockerfile
