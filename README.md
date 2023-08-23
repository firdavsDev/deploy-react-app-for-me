# FrontEnd deployment

## Install NodeJs and npm (recommend version) 

## Pull Repo from GitHub/GitLab

## cd {project_name}:
    npm i
    npm run build

## Install Ngnix:
    sudo apt-get install nginx

## Create ngnix file in /etc/nginx/sites-available/
    sudo nano /etc/nginx/sites-available/{file_name}
  
  ```
  server {
     listen 3000;
     root /home/hududsayt_user/karantin-region-front/build;
     server_name 192.168.145.23;
     index index.html index.htm;
     location / {
     }
  }
  ```
## Move file to sites-enables:
      sudo ln -s /etc/nginx/sites-available/{file_name} /etc/nginx/sites-enabled

## Check ngnix file sentax:
      sudo nginx -t

## Start Ngnix service:
      sudo service nginx start

## After git pull:
      sudo service nginx restart


  - And you’re done! If you go to your browser and type in the IP address of your server or your domain, you should see your React app live!
