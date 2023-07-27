FROM nginx
RUN rm -rf /usr/share/nginx/html/index.html
RUN rm -rf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/default.conf
ADD static /usr/share/nginx/html/
ADD nginx.conf /etc/nginx/nginx.conf

# FROM nginx:alpine
# RUN rm -rf /usr/share/nginx/html/index.html
# RUN rm -rf /etc/nginx/nginx.conf
# RUN rm -rf /etc/nginx/conf.d/default.conf
# ADD static /usr/share/nginx/html/
# ADD nginx.conf /etc/nginx/nginx.conf