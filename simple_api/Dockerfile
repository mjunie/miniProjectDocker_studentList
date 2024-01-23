# Use the official Python image as the base image
FROM python:2.7-buster
MAINTAINER junie (juniemacougoum@gmail.com)
WORKDIR /simple_api
RUN mkdir /data

# Copy the current directory contents into the container at /app
ADD . .
COPY ./student_age.json /data
# Installation of dependancies
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt update -y 
RUN apt --yes install python-dev libldap2-dev libssl-dev -y 
RUN apt --yes install libsasl2-dev
RUN pip install flask==1.1.2 flask_httpauth==4.1.0 flask_simpleldap python-dotenv==0.14.0
EXPOSE 5000

# apt update -y && apt install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y

VOLUME /data

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD [ "python", "./student_age.py" ]

  