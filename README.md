# docker-symfony-mysql-nginx
A fully configured docker-compose environment for running a symfony app with mysql and nginx

### Setup

* Fork the repository
* Clone it
* In a terminal (use git bash for windows), cd into the directory cloned
* run the following command (**Replace your name and email** from the command). You can ommit the --webapp to have a bare symfony skeleton without all the dependencies usually used for a full web application

```
docker run --rm -v $(pwd):$(pwd) -w $(pwd) -e "GIT_USERNAME=Your Name" -e "GIT_EMAIL=your@github.email" 2itech/php-symfony-cli symfony new app --webapp
```

--------------------------------------------------------------

##### After the project is created you can run

```
docker compose up -d
```

### Edit your hosts file

Your hosts file is located in :
* OSX / *unix => /etc/hosts
* Windows => C:/Windows/System32/Drivers/etc

Add the following:
```
127.0.0.1   m-2i-tech.academy
```

### Access it from your browser
Go to [http://m-2i-tech.academy](http://m-2i-tech.academy)

### Possible error
1. You may have an error where nginx is unable to write to cache and log directory.

If this happens, you can simply, from your Code Editor or your filesystem, delete the folders 'cache' and 'log' in your app/var folder.

2. The container names are already taken

In this case, you can either remove your existing containers using the same name or you can modify the container_name properties for each service in your compose file.


### To enter your containers
You need to replace the container name with what is in your docker-compose file.

If bash does not work, try ash or sh
```
docker exec -it container_name bash
```
