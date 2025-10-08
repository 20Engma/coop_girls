install docker :

1- update sys :

sudo apt update
sudo apt upgrade -y 

2- install packges:

sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
 
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io -y

sudo systemctl status docker

sudo usermod -aG docker $USER

docker run hello-world
 

--------------------------------------


app simple code

start with vim editor 

vim <your app> 

out >> esc > :wq


const http = require('http');

const hostname = '0.0.0.0';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('***\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});


dockerfile:

FROM node:14


WORKDIR /usr/src/app

COPY app.js .


EXPOSE 3000


CMD ["node", "app.js"]



docker build -t <image name> .


docker run -p 3000:3000 <image name>

docker images to check >> http://localhost:3000



-------

test another command :

push 
pull
regestery 
save as tar 
change image 
install image from docker hub and run it 

check logs 

give a task :


https://tryhackme.com/room/introtocontainerisation




