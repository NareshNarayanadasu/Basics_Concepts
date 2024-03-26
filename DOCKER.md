    
    
What is Docker :                 
                 
    Docker is an open platform for developing, shipping, and running applications. 
    Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications.
    
     
    
    




What is container :
    
    A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings
    Every container is isolated 
    

            
    


Docker working :

    Docker works via a Docker engine that is composed of two key elements: a server and a client; and the communication between the two is via REST API. The server communicates the instructions to the client.
    
    
    Docker is a platform that uses OS-level virtualization to deliver software in packages called containers. Here’s a brief summary of how it works: 
    
            § Containers: Docker creates isolated environments, known as containers, which are similar to virtual machines but more lightweight.
            § Docker Engine: It consists of a server and a client that communicate via a REST API. The engine is responsible for creating and managing containers.
            § Docker file: This is a set of instructions for building a Docker image, which is a template for containers containing all necessary components to run an application.
            § Portability: Docker ensures applications can run consistently across different environments, aiding in development and deployment processes.
    
    
        
    


Docker working 


            
        


Docker commands 



    To  Know Docker Version 


        

    Docker image pull

        Download an image from a registry
        The docker pull command serves for downloading Docker images from a registry.
        Aliases  for      docker image pull  -->   docker pull
        
        
        
        
        By default, the docker pull command pulls images from Docker Hub, but it is also possible to manually specify the private registry to pull from.
        
        Before running the docker pull command it needs to search the Docker registry for the image to download.
                    
                      docker image pull [OPTIONS] NAME[:TAG|@DIGEST]
        
        
        
        
    Docker Run
    
        The docker run command is one the most important command you should become familiar with. The docker run command is used to launch Docker containers from a specified image. 
        
        
        To create or launch a new container, you will only need to specify an image name with the docker run command.
        
                    docker container run image-name
                    
        The above command will start a new container from the image stored in the local system. If the specified image is not available in the local system, the command pulls it from the online Docker Hub registry.
        
        There are several ways to run the container including, detached mode or background, attached mode or foreground and an interactive mode.
         
        For attached mode
        
                   docker run image-name
                    
                    
                    
    
        
        
        
        Running the container in detached mode is similar to running the process in the background. This will keep the container running after exiting from the terminal session.
        You can use -d option to run a container in detached mode.
        
                Docker run -d image-name
        
        
        
        run a container in interactive mode to deal with the interactive processes. This will allows you to execute commands inside the container that is still running.
        
        You can use the -i and -t option to start the container in interactive mode.
        
        
                docker container run --name docker-nginx -it nginx /bin/bash
        
        
        This will be attached to the container shell and the command prompt will change as shown below:
        
        
                root@82ea93cbf662:/#
                
        
                
        You can now able to run any command inside the container.
        
        
        If the container is already running, you can attach the running container interactively using the exec option:
        
        
                docker exec -it docker-nginx /bin/bash
                
        The above command will get you inside an already running demonized container and execute your required actions.
        
        
        
        
        
        publishing container port
        
        run a container without publishing container port, you can access the process running in the container only from inside the container. You will need to publish a container port to the host machine ports in order to access the ports from the external machine.
        You can use the option -p with the docker container run command to publish the port.
        
        
                docker container run -p [host-ip]:[host-port]:[container-port]
                
            Where :
                □ host-ip is the IP address of the Docker host. This option is optional and it is not necessary to specify it.
                □ host-port is the port of the Docker host.
                □ container-port is the port of the container where the application is running.
            
        For example, map the Nginx container port 80 to port 8080 on the Docker host localhost interface, run the following command:
        
                docker container run --name docker-nginx -d -p 8080:80 nginx
            
        
                
            
        Docker ps: 
        
            the command is used to show present running containers 
            
        
        
             want to see all the containers existed  
        
        
                    Docker ps --all
                    
        
        
        
        
        Stop and kill 
        
            Docker  Stop command will slowly stops the  container smoothly  within the specified time 
             
            Docker stop command can use  with name of the container or container id 
            
        
            
        
        Here we have  container named as nginx-con  and its  status is up and running  now by using name or containeriid we can stop the container  
        
        
        
        
        
        
        
        
        
        Docker kill command 
        
                Docker kill    it is used to stops the container immediately
                
                
                 
        
