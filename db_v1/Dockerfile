FROM mongo:latest 

RUN echo '+++++++Docker mongo:latest version start runing ... ++++++++' 

RUN apt-get -y update && \ 
apt-get -y install vim && \ 
apt-get install -y curl && \ 
apt-get install -y iputils-ping 

# Set the working directory 
WORKDIR /usr/app 

COPY ./ ./ 
# RUN apk update && \ 
#   add vim && \ 
#   add curl \ 
#   add iputils-ping 

EXPOSE 27017