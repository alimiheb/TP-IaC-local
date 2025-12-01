FROM alpine:latest

RUN apk update && apk add nginx && rm -rf /var/cache/apk/*

RUN mkdir -p /var/www/localhost/htdocs && echo "<h1>Application Deployed via Terraform IaC!</h1>" > /var/www/localhost/htdocs/index.html

RUN echo 'server { listen 80 default_server; root /var/www/localhost/htdocs; index index.html; location / { try_files $uri $uri/ =404; } }' > /etc/nginx/http.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
