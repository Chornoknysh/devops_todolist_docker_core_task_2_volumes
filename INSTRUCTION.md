How to Run MySQL Container
docker run -d \
  --name mysql-local \
  -e MYSQL_DATABASE=app_db \
  -e MYSQL_USER=app_user \
  -e MYSQL_PASSWORD=1234 \
  -e MYSQL_ROOT_PASSWORD=root \
  -v mysql_data:/var/lib/mysql \
  -p 3306:3306 \
  <your-dockerhub-username>/mysql-local:1.0.0

How to Run Django App Container
docker run -d \
  --name todoapp \
  -p 8000:8000 \
  --link mysql-local:mysql \
  <your-dockerhub-username>/todoapp:2.0.0

Access the App
- Open your browser and go to: http://localhost:8000
✅ Docker Hub Links
- MySQL Image: https://hub.docker.com/r/chornoknysh/mysql-local
- Django App Image: https://hub.docker.com/r/chornoknysh/todoapp
