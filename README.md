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