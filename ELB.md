# Amazon Elastic Load Balancing (ELB)
## Application Load Balancer
	distributes your incoming traffic across multiple targets
	monitors the health of its registered targets
	scales your load balancer as your incoming traffic changes

### Components
1. **Load Balancer**: serves as the single point of contact for clients
2. **Listener Check**: determine how the load balancer routes requests to its registereds targets. It consists of priority, actions and conditions
3. **Target Group** requests to one or more registered targets

![](assets/elb.png)
