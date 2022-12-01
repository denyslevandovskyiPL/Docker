**NETCAT SERVER/CLIENT COMMUNICATION IN DIFFERENT DOCKER CONTAINERS**

#create network
>sudo docker network create --subnet=10.1.1.0/24 --gateway=10.1.1.10 my_net

#build images for client and server. Dockerfile for client is in ./client_files
>sudo docker image build -t client ./client_files
>sudo docker image build -t server ./server_files

#run server and client containers(you should run these commands in different terminals, server first)
sudo docker container run --network=my_net --ip 10.1.1.2 -it -v $(pwd)/server_files/:/home/ server
sudo docker container run --network=my_net -it -v $(pwd)/client_files/:/home/ client

#After you run this commands you can type something in client terminal and your text will occur in server terminal


#If you have any questions, please contact me with email: denys.levandovskyi@plvision.com


