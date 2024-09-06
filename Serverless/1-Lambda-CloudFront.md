 # VPC (Virtual Private Cloud)

**Internet Gateway (IGW)**
- allows resources in a VPC connect to the internet
- IGW must be created manually
- only one VPC can be connected to one IGW and vice-versa
- route table must be updated

**Bastion Hosts**
- it is a public subnet connected to all other private subnets
- used to SSH into private EC2 instances

## NAT Gateway
- does the same thing as bastion host BUT BETTER
- bastion host can communicate with only one private instance at a time while NAT can handle many requests at once
- allows outgoing traffic but does not allow any incoming traffic (which bastion host cannot do)
- created in a specific zone and uses elastic IP (instnaces from seperate availability zone cannot communicate using NAT)
- can't be used by EC2 instances in the same subnet
- requires IGW (Private subnet => NAT GW => IGW)
- very fast and no security grps required (no administration)
- multiple NAT Gateways can be created in multiple AZ's for fault tolerance

**Security grps vs NACL** Only inbound rules are defined in security grps because by default the inbound rules apply to outbound traffic while for NACl, we need to define both inbound and outbound rules
    - NACLs are like firewall which controls traffic from and to subnets
    - 1 NACL can have multiple subnets but 1 subnet can have only 1 NACL

## VPC Peering
- privately connect 2 VPCs and behave as in same network
- not transitive (must be established foe each individual VPC wanting to communicate)
- each VPC's subnet's route table must be updated
- VPC peering connections can be made across regions/accounts

## Types of endpoints
- Interface Endpoints
    - uses ENI(Elastic Network Interface/Elastic IP)
    - uses security grp
    - supports most AWS services hence expensive

- Gateway Endpoints
    - uses a gateway as target in route table
    - does not use security grp
    - supports S3 and DynamoDB hence free


## Lambda in VPC accessing DynamoDB
- **option 1: access from public internet** needs a NAT gateway in a public subnet and an IGW
- **option 2: (better and free) access from private VPC** deploy private VPC Gateway endpoint for DynamoDB and change route tables

Lambda is used for managing unpredictable workload/requests
CloudFront used for making data available across Mulitiple AZs
## Direct Connect
- fastest and most expensive
- private connection bw remote network to your VPC using Virtual Private Gateway
- access public (S3) and private(EC2) resources on saem connection
- usecase- large datasets with consistency
- in case Direct Connect fails, you can set up a Site-to-Site VPN (cheaper) as backup

Which components are required to build a site-to-site VPN connection on AWS? (Select TWO.)
1) Customer gateway
2) Virtual private gateway