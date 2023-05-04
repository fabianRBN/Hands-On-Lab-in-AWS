## User Data for AMI Linux 2023 - Juice Shop

#!/bin/bash 

sudo dnf update -y 

sudo dnf install -y docker 

service docker start 

systemctl enable docker.service

docker pull santospardos/upc:juiceshop

docker run -d -p 80:3000 santospardos/upc:juiceshop


## User Data for AMI Linux 2023 - Neflix

#!/bin/bash 

sudo dnf update -y 

sudo dnf install -y docker 

service docker start 

systemctl enable docker.service

docker pull santospardos/upc:netflix

docker run -d -p 80:80 santospardos/upc:netflix