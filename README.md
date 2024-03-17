# AWS-WordPress-Instance
## Launching and Optimizing WordPress with Amazon Lightsail
About: Amazon Lightsail is one of the easiest ways to get started with AWS. It offers virtual servers, storage, databases, and networking, plus a cost-effective, monthly plan. 
This project shows you how to launch and configure a WordPress instance on Lightsail. It includes steps to connect to your instance by using SSH, signing in to your WordPress website, create a static IP and attach it to your instance, creating a DNS zone, and map it to your instance.

## Step 1: Create an Amazon Lightsail account
a. This tutorial is free tier eligible on the AWS website

## Step 2: Create a WordPress instance in Lightsail
Complete the following steps to get your WordPress instance up and running on Lightsail.

a. Sign in to the Lightsail console.

b. On the Instances tab of the Lightsail home page, choose Create instance.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/b38b2a45-1013-4919-a9e8-875bb9809a26)

c. Choose Change AWS Region and Availability Zone if you want to create your instance in another location based on your location.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/b5c06155-f528-42b1-84a3-993185f9f02b)

d. Choose your instance image for your project.

Choose Linux/Unix as the platform.
Choose WordPress as the blueprint.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/1a287c65-0aa3-476f-a6a8-b5854cc259bd)


e. Choose an instance plan.

A plan includes a machine configuration (RAM, SSD, vCPU) at a low, predictable cost, and data transfer allowance. You can try the $3.50 USD Lightsail plan without charge for three months (up to 750 hours). AWS credits the first three months to your account. You may also delete the instance once your project is up and running — and not needed.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/98f9f07e-2f18-4f96-b0ef-818e4f6ec047)

f. Now enter a name for your instance and choose Create instance.

Create instance name guidelines:

Must be unique within each AWS Region in your Lightsail account.
Must contain 2 to 255 characters.
Must start and end with an alphanumeric character or number.
Can include alphanumeric characters, numbers, periods, dashes, and underscores.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/035ecef6-9cbe-4fdd-bc3a-500765e8c1c9)


## Step 3: Connect to your instance via SSH and get the password for your WordPress website
The default password to sign in to the administration dashboard of your WordPress website is stored on the instance.

Complete the following steps to connect to your instance using the browser-based SSH client in the Lightsail console, and get the password for the administration dashboard.

a. Once the instance is up and running — On the Instances tab of the Lightsail home page, choose the SSH quick-connect icon for your WordPress instance.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/202a4d7c-28cb-4638-b8b8-8925c96062b3)


b. After the browser-based SSH client window opens, enter the following command to retrieve the default application password:

cat $HOME/bitnami_application_password

c. Please make note of the password displayed on the screen. You use it later to sign in to the administration dashboard of your WordPress website.


![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/6d1c3a27-7a04-44e9-b564-7af8624195ac)


## Step 4: Sign in to the administration dashboard of your WordPress website
Now that you have the password for the administration dashboard of your WordPress website, you can sign in. In the administration dashboard, you can change your user password, install plugins, change the theme of your website, and more.

Complete the following steps to sign in to the administration dashboard of your WordPress website.

a. In a browser, go to:
http://PublicIpAddress/wp-login.php

In the address, replace PublicIpAddress with the public IP address of your WordPress instance. You can get your instance’s public IP address from the Lightsail console as shown in the image at the right.

b. Log in to your instance.

In the Username or Email Address box, enter user.
In the Password box, enter the default password obtained earlier in this tutorial.
Choose Log in.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/190d4eab-556f-43cc-bf97-7d9555d8f7a7)

c. You are now signed in to the administration dashboard of your WordPress website where you can perform administrative actions. You can build different website and install packages if you want to.


![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/aa869e07-4447-49de-9957-e4958a04013a)

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/6d0d433e-50f9-4fbe-9ea7-b29655e8b538)


## Step 5: Create a Lightsail static IP address and attach it to your WordPress instance
The default public IP for your WordPress instance changes if you stop and start your instance. A static IP address, attached to an instance, stays the same even if you stop and start your instance.

Complete the following steps to create a static IP address and attach it to your WordPress instance.

a. On the Instances tab of the Lightsail home page, choose your running WordPress instance.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/9099cf63-8a5d-440e-a236-5b40405b75f1)

b. Choose the Networking tab, then choose Create static IP.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/3b956665-9754-4039-a4d7-549fd87c1e6f)


c. The static IP location is preselected based on the instance zone that you chose earlier. Select the created WordPress instance from the Attach to an instance dropdown.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/ebc043c4-7e01-4931-97d2-5f0c86978088)

d. Name your static IP, then choose Create.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/3a5805ef-1e77-446d-9701-9609587693fe)

## Step 6: Create a Lightsail DNS zone and map a domain to your WordPress instance
Transfer management of your domain’s DNS records to Lightsail. This allows you to more easily map a domain to your WordPress instance, and manage more of your website’s resources using the Lightsail console.

Complete the following steps to create a Lightsail DNS zone and map a domain to your WordPress instance.

a. On the Networking tab of the Lightsail home page, choose Create DNS zone.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/63ed8c87-c996-4f02-ae2e-d06b781b61bc)


b. Enter your domain, then choose Create DNS zone.

b. Enter your domain, then choose Create DNS zone.

c. Make note of the name server address listed on the page.

You add these name server addresses to your domain name’s registrar to transfer management of your domain’s DNS records to Lightsail.


![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/a961b95f-83c4-47fe-b146-c611ded205da)
d. After management of your domain’s DNS records are transferred to Lightsail, add an A record to point the apex of your domain to your WordPress instance, as follows:

You add these name server addresses to your domain name’s registrar to transfer management of your domain’s DNS records to Lightsail.

In the DNS zone for your domain, choose Add record.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/63ad3b57-bd8b-4163-907a-2f1042d756d0)


e. Continue adding the following details to complete pointing the apex of your domain to your WordPress instance:

1. In the Subdomain box, enter an @ symbol to map the apex of your domain (such as example.com) to your instance. The @ symbol explicitly symbolizes that you’re adding an apex record. It is not added as a subdomain.

2. In the Resolves to box, choose the static IP that you attached to the WordPress instance in the previous step of this tutorial.

3. Choose the green save icon.

Allow time for the change to propagate through the internet’s DNS before your domain begins routing traffic to your WordPress instance.


![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/c1ba0e31-300d-4e3b-85f4-037057945a43)

## Step 7: Clean up time
a. On the Instances tab of the Lightsail home page, choose the ellipsis (⋮) icon next to the WordPress instance you just created and choose Delete.

![image](https://github.com/JohnnyLouisTech/AWS-WordPress-Instance/assets/29494723/e77df409-f543-4386-af1f-95d04e34c425)



b. Now confirm deletion of your instance.






















