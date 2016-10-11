External LB service for AWS Classic ELB
==========

#### About ELB Classic Load Balancers
The [Classic Load Balancer](https://aws.amazon.com/elasticloadbalancing/classicloadbalancer/) option in AWS routes traffic based on application or network level information and is ideal for simple load balancing of traffic across multiple EC2 instances.

#### About this service
This provider keeps pre-existing Classic Load Balancers updated with the EC2 instances Rancher services are running on, allowing one to use Elastic Load Balancing to load balancer Rancher services.

### Usage

1. Deploy the stack for this provider from the Rancher Catalog
2. Using the AWS Console create a Classic ELB load balancer with one or more listeners and configure it according to your applications requirements. Configure the listener(s) with the instance protocol and port matching that of the Rancher service that you want to load balance.
3. Create or update your service to expose one or multiple host ports that match the configuration of your ELB listener(s). Then add the service label `io.rancher.service.external_lb.endpoint` using as value the name of the existing ELB load balancer.
