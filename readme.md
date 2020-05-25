# Amazon EC2 Auto Scaling
One great benefit of using public cloud plaform is to add elasticity to the system
1. Health Monitoring (AWS integrates cloudwatch to auto scaling service)
2. Auto Healing
3. High Availablity (basically aws's general benefits)
4. intelligent scaling

# Scaling
## Vertical Scaling
Example: Scale one instance t2.micro to m5.large
## Horizonal scaling (ASG focus on this kind of scaling)
Example: multiple t2.micro, all are identical in different availablity zones

# Step
1. In EC2, create launch template first (configure which ami will be included in ASG)
2. Create ASG. Note user-data is 'bootstrap' command for all instances in ASG
3. You can have git repo and bake code in user-data(git clone in bootstrap) or do in AMI

# Associate ASG with ELB
1. create new ELB, leave the target group blank first.
2. go to created target group. edit and use ELB and ELB health check, thats all

# Auto Scaling options
1. manual
2. dynamic -- in ASG tab, choose scaling policy 
3. scheduled -- in ASG tab, choose scheduled action
4. predictive(ML)

# How to ssh and operate in instance?
Answer: Use AWS systems manager
1. first go to IAM and create roles so that we can delegate roles to instances => amazonec2roleforSSM
2. Update launch template in advanced details (add IAM above) so that it can be reached by AWS system manager
