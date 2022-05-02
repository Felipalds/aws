# AWS EC2 Master Class
## What is EC2
- The basis of AWS
- Renting VMs (EC2)
- Storing data (EBS)
- Distribuiting code across machines (ELB)
- Scaling services (ASG)
## What is SSH
- It allows you to control a remote machine, all using the command line
- Port 22
- Each instance have a public DNS
- To connect, we must have a security group - see it in the README file
- The default one is PORT 22 - PROTOCOL tcp - SOURCE 0.0.0.0/0 - NAME
- To connect you need the IPv4 of your EC2 instance
- ssh -i yourfile.pem ec2-user@IPV4
WE CAN AUTOMIZE IT
- vim ~/.ssh/config
it is a file with all your connections
now you put like this:
Host name-of-your-ssh-conn
    Hostname IPv4
    User ec2-user
    IdentityFile pwd-of-your-file
then ssh name-of-your-ssh-conn
## Security groups
- control how traffic is allowed or denied into EC2
- we have inbound and outbound traffic
- it is the most fundamental skill to learn to troubleshoot networking issues
- if there is no rules, anyone can access it - timeout
### Private vs Public IPs (IPv4)
- there are two versions of IP:
1) IPv4 - four numbers - separated by .
2) IPv6 - four numbers and letters - separated by :
- more for IoT
- Public networks is availible for the entire internet
- Private networks is like a private network  - it communicates with WWW with a gateway (public)
- can exist more than one private networks
- publics ids is uniques (by machines)
============================================
By default, EC2 comes with:
- a private IP for the internal AWS network - never changes
- a public IP for WWW - it can change
- we connect with a public IP, but actualy, we ARE in a private IP
