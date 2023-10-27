# FrontEnd deployment

### Install NodeJs and npm (recommend version) 

### Pull Repo from GitHub/GitLab

### cd {project_name}:
    npm i
    npm run build

### Install Ngnix:
    sudo apt-get install nginx

### Create ngnix file in /etc/nginx/sites-available/
    sudo nano /etc/nginx/sites-available/{file_name}
  
  ```
  server {
     listen 80;
     root /home/{path}/build;
     server_name IP, domain;
     index index.html index.htm;
     location / {
        try_files $uri $uri/ /index.html;
      } 
  }
  ```
### Move file to sites-enables:
      sudo ln -s /etc/nginx/sites-available/{file_name} /etc/nginx/sites-enabled

## Check ngnix file sentax:
      sudo nginx -t

### Start Ngnix service:
      sudo service nginx start

### After git pull:
     git pull
     npm run build
     sudo service nginx restart

### Check ngnix status:
        sudo service nginx status


  - And you’re done! If you go to your browser and type in the IP address of your server or your domain, you should see your React app live!

## Docker development
If pulled for the first time or the package.json changed run

    docker-compose build
    docker-compose up -d
    docker-compose logs -f web

If you need to install any npm package.

    docker-compose exec web npm install pacakge-name

More: https://medium.com/@sudiptob2/properly-setting-up-react-development-environment-using-docker-a2de46464d0b
