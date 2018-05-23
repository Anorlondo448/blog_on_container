# Wordpress Blog on Container
Simple Blog on Simple Container.

## Getting Started on Local Machine(for mac)
### Prerequisites
- docker

### Installing
- clone this repository
```
$ git clone https://github.com/Anorlondo448/blog_on_container
```

### Running
- start container
```
$ cd blog_on_container
$ docker-compose up
```

### Access
- http://localhost:8080

---

## Getting Started on AWS ECS(for mac)
### Official Page 
- [Install Amazon ECS CLI](https://docs.aws.amazon.com/ja_jp/AmazonECS/latest/developerguide/ECS_CLI_installation.html)


### Installing
- Download the ECS CLI binary.
```
$ sudo curl -o /usr/local/bin/ecs-cli https://s3.amazonaws.com/amazon-ecs-cli/ecs-cli-linux-amd64-latest
```
- Apply execute permissions to the binary.
```
$ sudo chmod +x /usr/local/bin/ecs-cli
$ which ecs-cli
```
- set credential
  - use [direnv](https://github.com/direnv/direnv)
- check version
```
$ ecs-cli --version
```

### AWS Setting
- make Key Pair on EC2 Dashboard

### ENV Setting
- use direnv
```
$ direnv edit .
```
```
export AWS_ACCESS_KEY_ID=[Access Key]
export AWS_SECRET_ACCESS_KEY=[Secret Key]
export AWS_DEFAULT_REGION=[Availability Zone]
export ECS_CLUSTER=[Cluster Name]
```
* [Cluster Name]　Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. ([Creating a Cluster](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/create_cluster.html))


### Launch ECS
- create ECS cluster
```
$ ecs-cli up --keypair [Key Pair Name] --capability-iam --size [Instance Count] --instance-type [Instance Type]
```



