# Key AWS Serverless Services

- Lambda
- DynamoDB
- API Gateway
- S3
- Aurora
- Fargate
- CloudFront

# EC2 vs Lambda

## EC2
- Virtual servers
- Limited by RAM
- Continuosly running

## Lambda
- Virtual functions (no servers)
- Limited by time (short execution time)
- Run on-demand
- Automated scaling

## CloudFront
- edge function - runs close to your users (eg: in their region/zone) to reduce latency
- latency-sensitive and short startup time
- handles viewer request/response only
- for handling viewer and origin request/response - use Lamda@Edge
- creat/design all your functions in one region; CloudFront will replicate it to other regions - fast delivery bcuz it is a CDN (Content Delivery) service

**For faster execution, less cost and handling more requests with less latency; use CloudFront**

## API Gateway

- **Edge-optimized**
    - for global clients
    - requests are routed thru CloudFront edge locations (improves latency)
    - API gateway still lives in only 1 region

- **Regional**
    - for local clients
    - manually combine with CloudFront (more control over distribution)

- **Private**
    - can only be accessed from VPC


