# Containerized Application  

    git clone https://github.com/sonulodha/containerized-app.git
    
    cd containerized-app
    
    ls 
    
    cd app1
    
    docker build -t mitrasonu/app_v:1
    
    docker images
    
    cd app2

    docker build -t mitrasonu/app_v:2

    docker images
    
    docker push ( to share docker images )
    
    

# deploy and scheduling | monitoring
    
    docker service create --replicas=3 -p 80:8080 --name app mitrasonu/app_v:1
    
    docker service ls
   
    docker service ps app


# docker service node ls
    scaling and Load balancing

    docker service scale app=4

    docker service scale app=6

    docker service scale app=3


# batch execution

    docker service ls


    docker service ps app


    docker ps


    docker rm -f cont-id


    docker service ls


    docker service ps app


# rollout and rollback

    • Rollout: deploy changes to the application or its configuration   
    • Rollback: revert the changes & restore to previous state
      docker swarm ensures there is no downtime during this process.


    docker service update --limit-cpu 1 app

    docker service update  --update-parallelism 1 --update-delay 30s --image mitrasonu/app_v:2  app

    dokcer service rollback app
