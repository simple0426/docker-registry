FROM node:latest
RUN npm config set registry https://registry.npm.taobao.org && npm install gitbook-cli -g
RUN git clone https://github.com/open-falcon/book.git /open-falcon
WORKDIR /open-falcon
RUN gitbook install && gitbook build
EXPOSE 4000
CMD ["gitbook", "serve"]
