# Mastering-AWS-VPC

This focuses on AWS vpc infrastructure, including subnets, gateways and routing tables

## Implementation for GatoGrowFast.com

## Setting up a VPC

Sign into AWS account

![Sign into aws account](./images/sign_into_aws_account.png)

- Navigate to the search bar and search for VPC
  ![Search for VPC in the search bar](./images/search_vpc.png)

- Navigate to create VPC tab and click on it
  ![Create VPC](./images/create_vpc.png)

- Select VPC only option, specify the ipv4 CIDR block and Create VPC
![VPC created](./images/vpc_creted.png)

## Creating Subnets

- Locate the subnet tab and click on create subnet
  ![Locate create subnet tab](./images/locate_subnet_tab.png)

- Choose the id the vpc you created previously, enter the subnet name, specify ipv4 CIDR for the subnet
![Configuring the subnet](./images/configuring_the_subnet.png)

- Creating the subnet
  To create the subnet, first click on the add new subnet button
![Add new subnet](./images/add-new-subnet.png)
-Sucessgully creating subnets
Two subnets have been created successfully. If you have CIDR overlaps, try resolve them by choosing a different range from the previous subnet created
![Succesfully create subnets](./images/successfully_create_subnets.png)

## Creating Internet Gateway

- Navigate to the internet gateway options on the left side bar
![Navigating to IGW tab](./images/finding_the_igw_tab.png)
- Click on create internet gateway
![Click in IGW](./images/igw_tab.png)
- Fill in the igw configuration and click create igw
![IGW created](./images/igw_created.png)
- Attach the IGW to your vPC
  Click on the action tab, and click and attach to your vpc
![Attch igw to vpc ](./images/attch_igw_to_vpc.png)

## Enabling internet connectivity by setting up route tables

- Proceed to route tables option tab in th aws console
![Locating route tables tab](./images/locating_route_table.png)

- Click on create route table
![](./images/creating-route-table.png)

- Link the route table to vpc created
![Link RT to VPC](./images/Link_RT_VPC.png)
- After selecting VPC associated with intended RT, click on create route table
![Create RT](./images/create_RT.png)
- Click on subnet association
![Click on subnet association](./images/subnet_association.png)
- Choose the public subnet and click save
![Subnet association setup](./images/subnet_assocaition_setup.png)
- navigate to routes and click edit routes
![navigate to routes](./images/navigate_to_routes.png)
- Click on add route
![Add route tab](./images/Add_route.png)
- Set destination to 0.0.0.0/0 then select internet gateway.
  the route table has now been configured to route traffic to the internet gateway. Since its only the public subnet that is associated with this route table, only resoures within this subnet can access the internet

## Enabling outbound internet access via NAT gateway

- Navigate to the NAT Gateway section and find Create NAT gateway
![Nat gateway tab](./images/nata-gateway_tab.png)
- Click on create Nat gateway
![Create nat button](./images/create_nat.png)
- Give the Nategwy a name/tag
![Naming Natgwy ](./images/nat_naming.png)
- Choose the subnet .i.e the private subnet
![Choosing the subnet](./images/choose_the_subnet.png)
- Choose the connectivity type as private
![Choose private conncectivity](./images/private_connectivity.png)
- Click on create NAT Gateway
![Create NAT gwy](./images/create_NAT_gwy.png)
- NAT gwy successfully created
![NATgwy successfully created](./images/NATgwy_successful.png)
- Select the NATgwy
- Navigate to details tab
- From there, locate the subnet on the nat gwy and click on it
![Back to subnet page](./images/subnet_page.png)
- navigate to the route table
![Go to route table](./images/route_table.png)
- Click on the routable ID
- Click on Edit route tab
![Edit route](./images/edit_route.png)
- Click on add route
- Set destination as 0.0.0.0/0 and target field as NAT gateway and then Choose the nat gwy you created
![setup private subnet and nat](./images/correct_nat_route_setup.png)
- Click save changes
- On the subnet assossiation section, select edit subnet association
![Subnet association](./images/subnet_association.png)
- Choosw the private subnet and click save assosiation
![Save subnet assossiation](./images/chose_network_association.png)

## VPC PEERING

- Create two other VPC in thesame region
- Navigate to peering connection on the sidebar
- Click it and you will be directed to VPC peering page
![VPC peering page](./images/vpc_peering_page.png)
- Click on create peering connection
- Provide a name for the VPC peering connection
- Select the requesterVPC
- Ensure to choose thesame region in this case since they were both created in thesame region
- Next select the accepterVPC
- Then click create peering connection
- In the peering connection, locate action option on the right side where you you can either accept or reject the connection request
![Connection request](./images/connection_request.png)
- Click on accept request
- Click on the main rout table ID of the accepter VPC
- Choose the route table and click and click the route tab
- Then click on edit routes button
- Click add route
- Go to VPC page and locate the requester VPC
- Copy the requesterVPC CIDR and paste in the destination field when adding a route and choose the target as peering connection
- Click save changes
- Copy CIDR of the accepterVPC
- Now click on the main route table ID of the requesterVPC
- Paste the CIDR in the destination field and peering connection for the target
- Then choose the peering connection you created
- The connection has been successfully established
