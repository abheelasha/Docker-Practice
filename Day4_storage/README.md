#Docker Volume Explained

##Steps followed

1. created image from Dockerfile
2. Created volume using command - docker create volume <volume name>
3. mounted the volume that was created in step 2 while creating container, 
    this can be done using _--volume_ or _--mount_ option as below -

    **Commands - **
    ₹₹₹
    docker run --mount type=volume,src=volume-day4,dst=/app,ro -it docker-storage
    docker volume inspect volume-day4
    docker inspect docker-storage
    #start container with volume
    docker run -d \                                                              
  --name docker-storage \
  --mount source=volume-day4,target=/app \
  docker-storage:latest
₹₹₹
  Response : - docker inspect docker-storage
    "Mounts": [
            {
                "Type": "volume",
                "Name": "volume-day4",
                "Source": "/var/lib/docker/volumes/volume-day4/_data",
                "Destination": "/app",
                "Driver": "local",
                "Mode": "z",
                "RW": true,
                "Propagation": ""

₹₹₹
stop container -
docker container stop docker-storage
remove container -
docker container rm docker-storage           }
remove volume - can't be removed when container is still created
docker volume rm volume-day4

₹₹₹