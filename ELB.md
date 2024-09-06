# ELB (Elastic Load Balancer)

- Load balancers are servers that forward traffic to multiple servers (eg-EC2 instances)
- Load balancer knows which instances are healthy and which are not. On the basis of that, it forwards traffic
- Do regular health checks
- High availability across zones
- Takes care of upgardes/maintainance
- Costs less to setup but takes more effort

**Security groups in Load Balancer**

users ---->    load    ----->   EC2
      <----  balancer  <----

- Load balancer security groups allows all trafic from users
- Application security group allows traffic only from Load balancer

## Types of Load Balancers

- **Application Load Balancer** (layer 7)

    - load balancing to multiple HTTP applications across machines (target grps) or same machine (container)
    - supports redirects (eg- from HTTP to HTTPS)
    - routing tables to different target grps based on rules defined by you
    - has fixed DNS name

- **Network Load Balancer** (layer 4)

    - forwards TCP and UDP traffic to your instances
    - handles millions of requests and has low latency
    - has static IP and supports elastic IP
    - also works with target grps

- **Gateway Load Balancer** (layer 3 - Network Layer)

    - manage 3rd party virtual applications like Firewalls, Intrusion Detections, etc.
    - single entry/exit for all traffic
    - target grps only consist EC2 instances or IP adress unlike the other two which can also consist other ALBs and NLBs