# Load-Balancing and Auto Scaling
1. Load Balancing:
Load balancing distributes incoming traffic across multiple targets, such as Amazon EC2 instances, to ensure no single server bears too much load. AWS offers services like Elastic Load Balancing (ELB) that automatically distribute traffic across multiple targets.
2. Auto Scaling:
Auto Scaling automatically adjusts the number of Amazon EC2 instances in a group based on the incoming traffic or a defined schedule. It helps maintain application performance and availability, and it also allows you to scale out during high traffic periods and scale in during low traffic periods.
3. Integration of Load Balancing and Auto Scaling:
When integrated, Auto Scaling groups work in conjunction with load balancers. The load balancer distributes traffic among instances within the Auto Scaling group. When Auto Scaling dynamically adjusts the number of instances, the load balancer automatically registers or deregisters these instances, ensuring that traffic is evenly distributed.

## Architecture of how Integration of Load Balancing and Auto Scaling Works

![elb](https://github.com/samanth2012/Load-Balancing/assets/114215621/22bc9125-b372-4e53-862c-28bcfa574bee)

## Method of Implementation
1. First We Set Auto Scaling Groups from Launch template and then we will attach load balancer to Auto Scaling group


Auto Scaling Groups

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_55_13](https://github.com/samanth2012/Load-Balancing/assets/114215621/9df120f4-e787-4d43-86e7-aa1b6a03c271)


Load Balancer

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_55_23](https://github.com/samanth2012/Load-Balancing/assets/114215621/9dc11018-df9a-494c-bf58-144341044735)


2. Specify desired capacity and maximum capacity for instances in the Auto Scaling group. Provide a user script so that instances are launched automatically, eliminating the need for manual creation.

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_54_55](https://github.com/samanth2012/Load-Balancing/assets/114215621/7eabc959-7a15-4f3a-80c6-dec40fbee201)


3. The first instance private ip address will be 172.31.4.94

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_56_23](https://github.com/samanth2012/Load-Balancing/assets/114215621/3202043c-f03b-4aad-9650-a9de0d06c462)


4. Copy the load balancer's dns name and paste it in new window then load balancer will first distrubutes traffic to first instance and we will see first instance ip address.

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_56_14](https://github.com/samanth2012/Load-Balancing/assets/114215621/dab095b6-f747-4c00-aa4d-cec4229b95ef)


5. If we refresh the tab the load balancer will disturbute traffic to second instance we get ip address of 172.31.85.28
 
![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_56_31](https://github.com/samanth2012/Load-Balancing/assets/114215621/22c02b54-5335-4679-a6c5-61a0f8b192bd)


6. This is the Second instances ip address
   
![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_56_40](https://github.com/samanth2012/Load-Balancing/assets/114215621/98f68a28-137d-418b-a1ef-a9a546515a34)

Upto now we have see how load balancer works now if a server down new instance should be added so to check I will terminate web2 instance
After Some Time a new webserver will be launched with an ip address of 172.31.80.142

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_59_08](https://github.com/samanth2012/Load-Balancing/assets/114215621/ce6718f5-c31e-46a4-83f5-0e7d835809c1)

If we refresh the tab we can see that at previous step ip address is 172.31.85.28 now it changed to 172.31.80.142

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_59_38](https://github.com/samanth2012/Load-Balancing/assets/114215621/a48dc3bb-e348-4e91-b8fa-3a04cebc5cdb)
