# Containers-Ping

#-First create a network by using command:  
#                                         docker network create myNetwork
#-Create 2 containers by using these commands:
#                                         docker run -d --network myNetwork --name container1 alpine sleep 3600
#                                         docker run -d --network mynetwork --name container2 python sleep 3600


#-Use commad for output : container1_ip=$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container1)


#-Than add iptables in these containers :
#                                        docker exec -it container1 /bin/sh
#                                        apk add iptables
#                                        docker exec -it container2 /bin/sh
#                                        apk add iptables

#Than for pinging use command:
#                                       docker exec -it container1 ping container2
