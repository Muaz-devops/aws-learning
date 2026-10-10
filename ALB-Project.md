# Application Load Balancer (ALB) Project 

## Task:
- Deploy two EC2 instances behind an ALB. 
- The ALB must handle all incoming traffic. 
- EC2 instances should not be accessible directly from the internet.

## Steps and config

### Step 1: Launch two EC2 instances in the same VPC.
- Use different availability zones where possible
- Install a simple web server using user-data making sure each instance returns different content for testing

![Sample user-date](https://github.com/Muaz-devops/aws-learning/blob/main/images/user-data-sample-ALB.JPG)

### Step 2: Create and set up ALB (in 2 Public Subnets)
- Add HTTP (port 80) listener
- Create a Target Group
- Register both EC2 instances (from step 1)
- Configure a health check on the root path / (should be the default path)

![Target-group-ALB](https://github.com/Muaz-devops/aws-learning/blob/main/images/target-group-ALB-project.JPG)

### Step 3: Create Security Groups (SG) 
- For ALB allow HTTP access from anywhere
- For EC2 instance allow access only from ALB


### Step 4: Test and confirm my ALB is working and run health checks. (Refresh to verify traffic alternates between both instances)

![Instanc-1](https://github.com/Muaz-devops/aws-learning/blob/main/images/alb-in-action.JPG)

![Instance-2](https://github.com/Muaz-devops/aws-learning/blob/main/images/alb-in-action-2.JPG)
