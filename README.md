#### Step 1

#### Created a VPC

---

<br>

![pic 1](images/1-create-vpc.png)

<br>

---

#### Step 2

#### Created 4 subnets, a)PublicSubnetA b)PublicSubnetB c)PrivateSubnetA d)PrivateSubnetB

<br>

![pic 2](images/2-created-subnets.png)

<br>

---

#### Step 3

#### Created Internet Gateway

<br>

![pic 3](images/3-create-demo-igw.png)

<br>

---

#### Step 4

#### Attached Internet Gateway to VPC

<br>

![pic 4](images/4-attach-igw-to-vpc.png)

<br>

---

#### Step 5

#### Created a PublicRouteTable and a PrivateRouteTable

<br>

![pic 5](images/5-create-private-and-public-route-table.png)

<br>

---

#### Step 6

#### Associated the public subnets with the PublicRouteTable to enable internet access for resources in that subnet

<br>

![pic 6](images/6-associate-public-subnets-with-public-route-table.png)

<br>

---

#### Step 7

#### Associated the private subnets with the PrivateRouteTable.

<br>

![pic 7](images/7-Associate-Private-subnets-with-private-route-table.png)

<br>

---

#### Step 8

#### Added routes. Created a route in the PublicRouteTable with a destination of 0.0.0.0/0 and selected the Internet Gateway as the target.

<br>

![pic 8](images/8-add-routes-to-publicroutetable.png)

<br>

---

#### Step 9

#### Created a security group for the bastion host and named it: `bastion-host-sg`

<br>

![pic 9](images/9-security-group-bastion-host.png)

<br>

---

#### Step 10

#### Edited the subnet settings of both PublicSubnet A and PublicSubnetB by selecting, `enable auto-assign public Ipv4 address`.

<br>

![pic 10](images/10-enable-auto-assign-subnet.png)

<br>

---

#### Step 11

#### Created an EC2 instance named `bastion-host` in PublicSubnetB

<br>

![pic 11](images/11-created-bastion-host.png)

<br>

---

#### Step 12

#### Successfully connected to the bastion-host and pinged ietf.org as recommended by AWS.

<br>

![pic 12](images/12-bastion-host-a-accessed-internet.png)

<br>

---

#### Step 13

#### Created a security group called `private-server-sg` for the 2 private instances in the private subnets, `private-server-a` in PrivateSubnetA and `private-server-b` in PrivateSubnetB.

<br>

![pic 13](images/13-security-group-private-server.png)

<br>

---

#### Step 14

#### Created the EC2 instance `private-server-a` in the PrivateSubnetA.

<br>

![pic 14](images/14-Created-private-servers.png)

<br>

---

#### Step 15

#### Created a public NAT gateway in `PublicSubnetA` and clicked on `Allocate Elastic IP` to have an Elastic IP automatically allocated for the Public NAT gateway.

<br>

![pic 15](images/15-ngw-created.png)

<br>

---

#### Step 16

#### Updated the private route table by adding a route of which the `destination` is `0.0.0.0/0` and the `target` is the NAT gateway that you created in step 15. This was done so that traffic goes through NAT Gateway.

<br>

![pic 16](images/15-update-private-route-table.png)

<br>

---

#### Step 17

#### Accessed the private-server-a EC2 instance in Availability zone A, by going through the bastion-host using SSH and used the command `ping ietf.org` in the private-server-a EC2 instance, to show that the private-server-a EC2 has outbound internet connectivity.

<br>

![pic 17](images/17-accessed-private-server-a-through-bastion-host.png)

<br>

---

#### Step 18

#### Accessed the private-server-b EC2 instance in Availability zone B, by going through the bastion-host using SSH and used the command `ping ietf.org` in the private-server-b EC2 instance, to show that the private-server-b EC2 has outbound internet connectivity.

<br>

![pic 18](images/18-accessed-private-server-b-through-bastion-host.png)

<br>

---
