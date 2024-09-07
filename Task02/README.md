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

  ![Screenshot from 2024-09-05 15-10-51](https://github.com/user-attachments/assets/1784574e-7ab8-4c66-991f-6a2c7c77001f)

# Rolling Deployment 
- Here we use same infrastructure as ablove in it.
- I have 3 servers running in v1 as shown below. By changing the capacity in Autoscaling group.
![Screenshot from 2024-01-22 19-38-15](https://github.com/Kiran-dehlikar/test/assets/104997588/67550ce0-a374-420e-8f2f-932b56a33299)
![Screenshot from 2024-01-22 19-39-45](https://github.com/Kiran-dehlikar/test/assets/104997588/bf39b6d6-20a0-4358-b480-6d8df3ece0cc)
![Screenshot from 2024-01-22 19-39-45](https://github.com/Kiran-dehlikar/test/assets/104997588/694ada25-45f8-496d-98d4-46d96108bd7f)

- It will gradually increase the instances then we change the capacity in autoscaling group to desired as shown in below screenshots.
![Screenshot from 2024-01-22 20-02-28](https://github.com/Kiran-dehlikar/test/assets/104997588/7e02be20-de8c-4ba4-8668-3e424769220f)

![Screenshot from 2024-01-22 20-07-21](https://github.com/Kiran-dehlikar/test/assets/104997588/727fb960-f2f6-431c-bbb9-d2465a359c7e)

- So due to this v1 replaces the v2 gradually with no downtime.
![Screenshot from 2024-01-22 15-53-09](https://github.com/Kiran-dehlikar/test/assets/104997588/cfe37b90-0d9d-493f-b526-b0269ced5981)
![Screenshot from 2024-01-22 16-48-15](https://github.com/Kiran-dehlikar/test/assets/104997588/f4e752ea-59b5-45ff-8469-d62e3ccdb609)





  


