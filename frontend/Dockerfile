FROM registry.access.redhat.com/ubi10/nginx-126:10.0

COPY index.html /usr/share/nginx/html/

COPY nginx.conf /etc/nginx/nginx.conf

USER 1001

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]