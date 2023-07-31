# AWS Architectures

### MERN Stack AWS Architecture - 1
![AWS Architecture 1](https://github.com/Abbas-Borji/AWS-Architectures/blob/main/Architecture%20-%201.svg)

The architecture depicted above is designed to support a MERN stack application (where "M" represents MySQL).

**Utilizing Auto-Scaling Group for Dynamic EC2 Instances**
- It utilizes an auto-scaling group to manage EC2 instances dynamically, maintaining a minimum of one instance when the load is below 70% and a maximum of two instances otherwise, ensuring efficient resource allocation.

**Leveraging Simple Email Service (SES) for a Noreply Email**
- The Simple Email Service (SES) plays a vital role by providing a noreply email for essential processes such as email verification and password reset.

**Configuring Private S3 Bucket for Files Storage**
- To maintain security, the S3 Bucket for Files Storage is configured to be private and accessible only by the auto-scaling group, safeguarding sensitive data.

**Ensuring Secure User Interactions with HTTPS Communication**
- Additionally, to ensure secure user interactions, HTTPS communication is employed between the load balancer and Route 53, utilizing the SSL certificate applied to the load balancer.

**Securing CloudFront and Route 53 Communication with HTTPS**
- Similarly, CloudFront and Route 53 communication employ HTTPS with the SSL certificate applied to CloudFront, ensuring that users interact with the application through a secure connection.

---

### MERN Stack AWS Architecture - 2
![AWS Architecture 2](https://github.com/Abbas-Borji/AWS-Architectures/blob/main/Architecture%20-%202.svg)

This AWS architecture diagram showcases the infrastructure supporting a MERN (MySQL, Express.js, React.js, Node.js) stack application. The diagram emphasizes scalability, security, and efficient deployment processes.

**Frontend Serving**
- The frontend files are distributed through a Content Delivery Network (CDN) and stored in an Amazon S3 bucket for faster and reliable delivery to end-users.

**Highly Available RDS**
- The application's MySQL database is hosted in Amazon RDS. To ensure high availability, the RDS clusters are distributed across all three Availability Zones within the respective private subnets. This configuration ensures both security and accessibility.

**Auto-Scaling Group**
- The auto-scaling group is deployed across the three Availability Zones to enhance fault tolerance and scalability. It maintains a minimum of one instance during periods of low CPU utilization (below 70%) and automatically scales up to a maximum of three instances during peak loads.

**Pipelines for Continuous Deployment**
- Two separate pipelines are set up for the frontend and backend to facilitate smooth and simultaneous deployment of updates. These pipelines use an Amazon S3 bucket to store and retrieve data and artifacts.

**Private S3 Bucket Access**
- EC2 instances are granted access to retrieve non-public files from a private S3 bucket. This ensures sensitive data remains secure.

**Internet Reachability and Security**
- The auto-scaling group utilizes the three public subnets for internet reachability. Alternatively, a more secure configuration can be achieved by using private subnets with NAT (Network Address Translation) and Internet Gateways.

**Load Balancer and SSL Certificates**
- The load balancer ensures that all HTTP connections are automatically redirected to HTTPS, enhancing the overall security. SSL certificates from AWS Certificate Manager (ACM) are applied to secure connections between AWS services and end-users.
