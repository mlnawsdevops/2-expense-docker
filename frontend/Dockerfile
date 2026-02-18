# frontend
# frontend connecting to backend. they are in same network
# inside container -- cat /etc/nginx/nginx.conf
# COPY expense.conf /etc/nginx/default.d/expense.conf

FROM nginx
copy code /usr/share/nginx/html
RUN rm -rf /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf
