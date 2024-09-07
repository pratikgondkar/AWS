#  Assignment-02

## Deployment Strategies

### Problem Statements
In this assignment you have to learn about deployment strategies: - Recreate deployment - Rolling deployment - Blue-green deployment - A/B deployment - Canary deployment

After this you need to implement these 2 below deployment strategies: Must Do - Recreate deployment - Rolling deployment Good to Do - Blue Green deployment - Canary deployment

Recommendation - Don't straight forward jump into creating the utility, first do it manually

- github-link --> https://github.com/OT-TRAINING/DeploymentStrategies

- Hint :

Use ASG
Use LB
Use EC2 service
Use AMI Snapshot

### Recreate Deployment

- Basic Requirements
- Create VPC, 2 Subnets (Public and Private), Route Table, IGW Gateway, NAT Gateway

  ![Screenshot from 2024-09-05 02-35-00](https://github.com/user-attachments/assets/326bfdb2-80e6-440b-a814-84a1c76b6530)

Create a instance for v1 and make the AMI of it.
![Screenshot from 2024-09-05 02-37-30](https://github.com/user-attachments/assets/8f730031-6bdc-4f5e-b7b7-38e0e14d10e5)

![Screenshot from 2024-09-05 03-01-27](https://github.com/user-attachments/assets/d80d706d-5050-4826-a7fe-282843c24dc9)

- Create a Target group for Load Balancer
  
  ![Screenshot from 2024-09-05 03-02-05](https://github.com/user-attachments/assets/8401a3d8-6d2c-47e2-8553-6f795bd7eaf3)

  - Create a Load Balancer and attach Target Group to it.
![Screenshot from 2024-09-05 23-19-22](https://github.com/user-attachments/assets/f8071c8d-cbd3-4062-9844-be709e927edf)

   
  - Create a Launch Template Create a Autoscaling group and attach Load Balancer to it.
    
  ![Screenshot from 2024-09-05 15-16-35](https://github.com/user-attachments/assets/523215f2-0ba8-403a-9453-8f6e5a39265e)

  -  Go to web browser and hit the Load Balancer dns
    ![Screenshot from 2024-09-05 14-54-11](https://github.com/user-attachments/assets/87be24c7-db33-4cf0-8155-b5baa66e6bac)
- Now change the version in Launch template and Go to the auto scaling group and change the capacity to zero.
- It will shows downtime and then increase the capacity. When the instance gets up it will shows V2.

  ![Screenshot from 2024-09-05 14-02-40](https://github.com/user-attachments/assets/a31be835-8e5c-4d75-bff6-3dffde4d5478)

  ![Screenshot from 2024-09-05 14-58-31](https://github.com/user-attachments/assets/d82754be-3a5d-4ab1-810b-99cc90c3ff1e)

  ![Uploading Screenshot from 2024-09-05 15-10-51.png…]()





  


