FROM nginx:latest
RUN mkdir /app
RUN chown -R 1001:1001 /app && chmod -R 755 /app && \
        chown -R 1001:1001 /var/cache/nginx && \
        chown -R 1001:1001 /var/log/nginx && \
        chown -R 1001:1001 /etc/nginx/conf.d
RUN touch /var/run/nginx.pid && \
        chown -R 1001:1001 /var/run/nginx.pid
USER 1001:1001
COPY ["nginx.conf", "/etc/nginx/conf.d/default.conf"]
EXPOSE 8000
