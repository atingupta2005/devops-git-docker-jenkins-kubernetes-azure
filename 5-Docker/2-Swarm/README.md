# Docker SWARM

## Tasks:
- Create multiple ec2 instances.
- Install docker packages.
- SSH to one of the ec2 instances and run the following command to promote you instance into Manager/Leader node.

```
docker swarm init --advertise-addr=104.211.0.65
```

- Use the output of the above command to create a worker/ manager node

- You can check the status and availability of a node by running the following command:
```
docker node ls
```

```
docker node inspect <node-id>
```

- Create Service
```
docker service create --replicas 2 -p 8080:80 --name web_server_atin nginx
docker service ls
```

- See the status of the service and how it is being distributed to different nodes by using the following command:
```
docker service ps web_server
```

- You can access the service by hitting any of the manager or worker nodes.
- Try out a curl to any of the Docker Machine IPs (manager1 or worker1) or hit the URL (HTTP://<docker-machine-ip>) in the browser
- You should be able to get the standard NGINX Homepage.

- Scaling
```
docker service scale web_server=3
```

```
docker service scale web_server=1
```

- List all the service running in swarm mode
```
docker service ls
```

- Remove a particular service
```
docker service rm web_server
```


- Leave cluster
```
docker swarm leave
```