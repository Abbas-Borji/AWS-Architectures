# AWS-Architectures

---

### Architecture - 1
![AWS Architecture 1](https://github.com/Abbas-Borji/AWS-Architectures/blob/main/Architecture%20-%201.svg)

- The architecture depicted above is designed to support a MERN stack application (where "M" represents MySQL).
- It utilizes an auto-scaling group to manage EC2 instances dynamically, maintaining a minimum of one instance when the load is below 70% and a maximum of two instances otherwise, ensuring efficient resource allocation.
- The Simple Email Service (SES) plays a vital role by providing a noreply email for essential processes such as email verification and password reset.
- To maintain security, the S3 Bucket for Files Storage is configured to be private and accessible only by the auto-scaling group, safeguarding sensitive data.
- Additionally, to ensure secure user interactions, HTTPS communication is employed between the load balancer and Route 53, utilizing the SSL certificate applied to the load balancer.
- Similarly, CloudFront and Route 53 communication employ HTTPS with the SSL certificate applied to CloudFront, ensuring that users interact with the application through a secure connection.
