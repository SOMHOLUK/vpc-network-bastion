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

![pic 14](images/14-created-private-server-ec2.png)

<br>

---
