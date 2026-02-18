FROM nginx
# frontend
copy code /usr/share/nginx/html
# frontend connecting to backend. they are in same network
RUN rm -rf /etc/nginx/nginx.conf
# inside container -- cat /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY expense.conf /etc/nginx/default.d/expense.conf