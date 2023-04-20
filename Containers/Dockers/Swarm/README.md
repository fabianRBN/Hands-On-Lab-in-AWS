## Swarm commands 

sudo yum install docker -y

sudo service docker start

sudo usermod -a -G docker ec2-user

sudo chkconfig docker on

(Close the ssh session and enter again to execute docker with your user (ec2-user))

docker swarm init --advertise-addr manager_private_ip

docker swarm join --token SWMTKN_token manager_private_ip

(docker swarm join --token SWMTKN-1-0umz9m4m6109ddm4qkate0wbz9n9uq4h7e6j1uous53t0saabz-evd4avwxrecruuntxs2xipyzk 172.31.83.127:2377)

docker swarm leave

docker node ls

docker network create --driver overlay --subnet 10.0.0.0/12 --opt encrypted services

docker service create --replicas 2 --name nginx --network services --publish 80:80 nginx

docker service ls

docker service ps nginx

docker exec -it nginx_id

docker service scale nginx=3

docker service ps nginx

docker node update --availability=drain <node hostname>

docker node update --availability=active <node hostname>

docker service scale nginx=2

docker service inspect nginx

docker service rm nginx





docker service create --name tools services wbitt/network-multitool

docker service rm tools


docker service create --name busybox --network services busybox sleep 3000

docker service ps busybox

docker service scale busybox=0
  
### Links
  
https://docs.docker.com/engine/swarm/swarm-tutorial/
  
https://upcloud.com/resources/tutorials/docker-swarm-orchestration
