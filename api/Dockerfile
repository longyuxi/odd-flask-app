# Base Image
FROM python:3.7.16-bullseye

RUN echo "deb http://archive.debian.org/debian stretch main" > /etc/apt/sources.list

# Install netcat
RUN apt-get update && \
    apt-get -y install netcat && \
    apt-get clean

# set working directory
WORKDIR /usr/src/app

# add and install requirements
COPY ./requirements.txt /usr/src/app/requirements.txt
RUN pip install -r requirements.txt

# add app
COPY . /usr/src/app

# run server
CMD python manage.py run -h 0.0.0.0
