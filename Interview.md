## Indirect Questions (look for discussion, opinionated with validation):
1.
```
Q: What does DevOps mean to you?
A: Removal of barriers between Dev/Ops teams, automation, IaC.
```
2.
```
Q: What is the difference between CI and CD?
A: Continuous Integration is the pre-requisite for Continuous Delivery (or Deployment). 
CI requires everything to be source controlled; preferably a DVCS; short-lived branches; automated builds; automated tests; visibility.

There's a difference between Continuous Delivery, where releases to production are still done with a manual go-ahead, and Continuous Deployment, where release to production occur automatically.
CD might involve any of release automation (think blue-green, canary etc); feature flags; preferably pipeline as code; database migration automation; rollback automation and also IaC automation involving Chef/Puppet/Terraform etc. 
```
3.
```
Q: Describe some deployment patterns (and the challenges associated eg. database replication, rollbacks etc.)?
A: Blue-green; canary; warm standby; pilot light etc.
```
4.
```
Q: What does IaC imply and what are the benefits?
A: Infrastructure as Code is a paradigm that manages and tracks infrastructure configuration in files rather than manually/via GUIs. 
Allows for more scalable infrastructure configuration; automated testing (acceptance testing of the infrastructure tier; linting or unit testing of the configuration itself); and more importantly allows for transparent tracking of changes through versioning.
```
5.
```
Q: What's your preferred infrastructure automation tool and why?
A: Chef is more config mgmt; Puppet master-agent setup; Ansible simpler; Terraform multi-provider pluggable. 
No right answer here obviously, more to see if they're both eloquent and passionate (without stoking the flame wars!) 
```
6.
```
Q: What is a Virtual Private Cloud (AWS, GCE) or VNet (Azure)?
A: Network segregation with subnets and non-globally routable IP addresses.
Routing differs among these technologies. You have to define routing tables yourself in AWS, whereas all resources in Azure VNets allow the flow of traffic using the system route. Security policies also contain notable differences between the various cloud providers
```
7.
```
Q: How do you set up a VPC in AWS? (Concepts are similar to a physical infrastructure if they don't have AWS experience).
A: Create the following:
 - an empty VPC with CIDR block;
 - a public subnet with associated Internet Gateway;
 - a private subnet with associated NAT Gateway (or instance if they're old school; ensure they understand the difference if they mention NAT Instances);
 - route tables for each subnet, with one routing traffic through the Internet Gateway and one routing through the NAT gateway and assign to respective subnets;
 - security group(s) and NACLs then control inbound and outbound traffic (could ask them to explain the difference between these also (stateful vs. stateless, DENY/ALLOW etc).
```

## Direct Questions (these are more on the Ops side but useful for debugging, exploration etc):

1.
```
Q: What is an ELF file?
A: Unix executable file format (Executable and Linkeable Format), common exec file for linux.
```
2.
```
Q: How do you query the type of a CPU using cat?
A: cat /proc/cpuinfo
```
3:
```
Q: What does the 'w' command output?
A: Uptime and load average
```
4:
```
Q: What does load average tell us?
A: It measures the number of threads that are working and waiting to work (CPU, disk, uninterruptible locks).
```
5:
```
Q: How many hosts does a IP v4 class B network have?
A: 65534.
```
6:
```
Q: What does NAT stand for and when is it used?
A: Network Address Translation. A NAT Gateway is a host that bridges connectivity between a private network and outside networks, used for instance when doing a `yum update` from a private subnet. 
```
7:
```
Q: How do you permenantly configure FD limits in linux
A: By Editing /etc/security/limits.conf and adding appropriate for 'nofiles' (hard and soft) entries.
NB: 'ulimit' is not the right answer, that only affects the current session.
```
