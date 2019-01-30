FROM ansible/awx_web:latest
USER root
WORKDIR /etc/nginx
RUN mkdir certs
WORKDIR /etc/nginx/certs
RUN openssl genrsa -out server.key 2048
RUN openssl rsa -in server.key -out server.key 
RUN openssl req -sha256 -new -key server.key -out server.csr -subj '/CN=10.215.196.35' 
RUN openssl x509 -req -sha256 -days 365 -in server.csr -signkey server.key -out server.crt
ADD nginx.conf /etc/nginx/
