# My Docker builds
My Docker files for develop with PHP, HHVM+XHP, Nodejs, JXCore, Spidermonkey, V8JS, Server Side React Render and other...

## Usage

    cd docker/image_name/ # where is Dockerfile
    docker build -t hhvm .

**Run for debuging**

    sudo docker run -p 127.0.0.1:9009:9000 -v /www/dockerfs/sites:/www/sites --name=$tag --rm -it $image /sbin/my_init -- bash -l

**Run as daemon**

    sudo docker run -p 127.0.0.1:9009:9000 -v /www/dockerfs/sites:/www/sites --name=$tag -d $image /sbin/my_init


**Login to the container**

    ssh -i ~/.ssh/id_rsa root@$ip

**Running a command inside the container**

    ssh -i ~/.ssh/id_rsa root@$ip echo hello world
