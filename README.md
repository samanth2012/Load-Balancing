# Load-Balancing
1. Load Balancing:
Load balancing distributes incoming traffic across multiple targets, such as Amazon EC2 instances, to ensure no single server bears too much load. AWS offers services like Elastic Load Balancing (ELB) that automatically distribute traffic across multiple targets.
2. Auto Scaling:
Auto Scaling automatically adjusts the number of Amazon EC2 instances in a group based on the incoming traffic or a defined schedule. It helps maintain application performance and availability, and it also allows you to scale out during high traffic periods and scale in during low traffic periods.
3. Integration of Load Balancing and Auto Scaling:
When integrated, Auto Scaling groups work in conjunction with load balancers. The load balancer distributes traffic among instances within the Auto Scaling group. When Auto Scaling dynamically adjusts the number of instances, the load balancer automatically registers or deregisters these instances, ensuring that traffic is evenly distributed.
## Architecture of how Integration of Load Balancing and Auto Scaling Works
![elb](https://github.com/samanth2012/Load-Balancing/assets/114215621/22bc9125-b372-4e53-862c-28bcfa574bee)
## Method of Implementation
1.First We Set Auto Scaling Groups from Launch template and then we will attach load balancer to Auto Scaling group
![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_55_13](https://github.com/samanth2012/Load-Balancing/assets/114215621/9df120f4-e787-4d43-86e7-aa1b6a03c271)
![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_55_23](https://github.com/samanth2012/Load-Balancing/assets/114215621/9dc11018-df9a-494c-bf58-144341044735)

2. We will set desired capacity and maximum capacity of instances  along with we will give a user script data  . so that automatically it launches the multiple instances rather creating manually.
![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_54_55](https://github.com/samanth2012/Load-Balancing/assets/114215621/7eabc959-7a15-4f3a-80c6-dec40fbee201)

![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_56_23](https://github.com/samanth2012/Load-Balancing/assets/114215621/3202043c-f03b-4aad-9650-a9de0d06c462)
![Instances _ EC2 _ us-east-1 - Brave 20-10-2023 09_56_14](https://github.com/samanth2012/Load-Balancing/assets/114215621/dab095b6-f747-4c00-aa4d-cec4229b95ef)
