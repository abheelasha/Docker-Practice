# Defining base image
FROM ubuntu:latest

# Define /app as working directory. 
# By difining this all the operation will be performed in /app directory hereafter
WORKDIR /app
# Copying all the files present in host filesystem pwd to imagefilesystem/app directory
# The COPY instruction copies new files or directories from 
# <src> and adds them to the filesystem of the image at the path <dest>.
COPY . /app

#installing python and dependencies on container
RUN apt-get update && apt-get install -y python3 python3-pip

#setting ENV variable
#ENV NAME = World

# runs the application, Specify default commands.
CMD python3 app.py

