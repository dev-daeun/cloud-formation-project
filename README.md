# cloud-formation-project

This is an assignment project for [Udacity Cloud Devops Nanodegree](https://www.udacity.com/course/cloud-dev-ops-nanodegree--nd9991).
CloudFormation templates in this repo deploys AWS resources shown in the chart below.
( S3 bucket is already offered in assignment.)
<br><br>
![](./udagram_architecture.png)


To deploy the resources, run the commands below in order.
```
# Deploys basic nework resources such as VPC, subnets, NAT/Interget gateway and router etc.
$ ./create_stack.sh Udagram-network network/network.yml network/network_parameter.json
```

```
# Deploys security group for each instance in subnets.
$ ./create_stack.sh Udagram-security-group servers/security_group.yml servers/security_parameter.json
```

```
# Deploys Lanunch Configuration & Auto-Scaling group applied to instances in private subnets.
$ ./create_stack.sh Udagram-auto-scale servers/auto_scaling_group.yml servers/auto_scaling_parameter.json
```

```
# Deploys Load Balancer which sends user-end traffic to public subnets.
$ ./create_stack.sh Udagram-LB servers/load_balancer.yml servers/load_balancer_parameter.json
```
