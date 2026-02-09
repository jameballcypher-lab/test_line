# test_line 


docker-compose down
docker-compose up -d
docker exec -it laravel_app composer create-project laravel/laravel:^11.0 .
docker exec -it laravel_app chmod -R 777 storage bootstrap/cache


docker-compose restart laravel_nginx
docker exec -it laravel_nginx nginx -t
docker exec -it laravel_nginx nginx -s reload

http://localhost:8090/
http://localhost:8090/info.php 

แก้ permission (สำคัญมาก)
docker exec -it laravel_app touch database/database.sqlite
docker exec -it laravel_app ls -l database/database.sqlite
docker exec -it laravel_app chmod 777 database
docker exec -it laravel_app chmod 666 database/database.sqlite
docker exec -it laravel_app php artisan migrate
docker exec -it laravel_app php artisan tinker

## GIT ##
git add .
git commit -m "add gitignore for laravel docker project"
git status
git push -u origin main

