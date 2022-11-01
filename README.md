#Paint 😍
Windows 95, 98, and XP were the golden years of Paint. You had a tool box and a color box, a foreground color and a background color, and that was all you needed.

![image](https://user-images.githubusercontent.com/111989928/199283612-8818dc40-c52b-4c46-b89d-35360d9b5efc.png)


Just run the below Docker command to access the paint web application from **[My DockerHub Account](https://hub.docker.com/u/raam043)**
```sh
docker run --name paint -d -p 80:80 raam043/
```

To Run cutomized app > Release new Linux server and install Docker & Git
```sh
yum update -y
yum install docker -y
systemctl enable docker
systemctl start docker
yum install pip -y
pip install docker-py
yum install git -y
```


Make app directory and add Application files using git clone
```sh
rm -rf /opt/paint/
mkdir /opt/paint
cd /opt/paint
git clone https://github.com/Raam043/Paint.git
```
Add Dockerfile

vi Dockerfile

```sh
FROM nginx
COPY ./Paint/  /usr/share/nginx/html/
```

Run Docker commands to run application on container
```sh
docker stop paint
docker rm -f paint
docker image rm -f paint
docker build -t paint .
docker run --name paint -d -p 80:80 paint
```
