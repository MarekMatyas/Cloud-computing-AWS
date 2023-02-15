# Cloud-computing-AWS

1. Log in 
2. Change region to Ireland eu-west-1


## Cloud computing

Cloud computing means storing and accessing data and programs over the internet instead of your computer's hard drive.

Users access cloud services either through a browser or through an app, connecting to the cloud over the internet.

### SaaS (Software as a service)

Insted of users installing an application on their device, **SaaS** applications are hosted on cloud servers, and users can access them over the internet.

Saas applications:

- Salesforce
- MailChimp
- Slack

### PaaS (Platform as a service)

In this model, companies don't pay for hosted applications, instead they pay for things they need to build their own applications.

PaaS vendors offer everything necessary for building an application, including development tools, infrastructure and operating systems over the Internet.

- Heroku
- Microsoft Azure


### IaaS (Infrastructure as a service)

In this model, a company rents the servers and storage they need from a cloud provider. They then use the cloud infrastructure to build their applications.

IaaS providers:
- Digital Ocean
- Google Compute Engine
- OpenStack

![](cloud.jpg)

Formerly, SaaS, PaaS and IaaS were the three main models of cloud computing, and essentially all cloud services fit into one of these categories. However, in recent years a fourth model has emerged:

### FaaS (Function as a service)

Also known as serverless computing, breaks cloud applications down into even smalled componenets that only run when they are needed.

FaaS or serverless applications still run on servers, as do all these models of cloud computing. But they are called "serverless" because they do not run on dedicated machines, and because the companies building the applications do not have to manage any servers.


## Types of Cloud 

---

1. **Private cloud**: A private cloud is server, data center, or distributed network wholly dedicated to one organization
Also known as an internal cloud or corporate cloud, is a cloud computing environment in which all hardware and software recources are dedicated exclusively to, and accessible only by, a single customer

---

2. **Public cloud**: A public cloud is defined as computing services offered by third-party provides over the public internet, making them available to anyone who wants to use or purchase them. 
They may be free or sold on-demand, allowing customers to pay only per usage for the CPU cycles, storage, or bandwidth they consume.














# How to set up VM through AWS

First we need to create .ssh folder 

`mkdir .ssh`

After we need to navigate into that folder `cd .ssh` (this is the folder where we need to copy the keys)

A key needs to be generated. 

**AWS website**

Log in and make sure your region is Ireland.

In a search bar we search for EC2 server. In this case one key would be generated for us.

**GitBash**
We have to download the key `.pem` and we move the content to the `.ssh` folder.

`nano devops-tech201.pem` to enter the file and we copy paste the content of the key file - `ctrl+x`

To double check `cat devops-tech201.pem` shows the content we pasted.

**AWS**

Go to EC2 dashboard.

Next we want to launch the VM on the cloud. We will have to set the configuration we want for our VM.

Click on "Launch instance" to launch instance fresh.

For the name we will have to specify our name,group and VM's name

We have to search for operating system, in our case "ubuntu 18.04".

"Instance type (t2.micro)" specifies how many cpu's, how much memory and the cost per hour.

After that we will need to select the key.

In network settings we need to create security group and we need to choose `SSH traffic` and on the drop down button we need to choose our own IP address and allow `HTTP traffic` because nginx is using port 80. (HTTPS is needed in the production environment).

Next we come we dont want to create another security group so in the network settings we click on "Edit"

- Subnet setting- Default 1a to make sure its public subnet

- Auto-assing public IP - Enable

- Security group name- your_name-tech201-app

- Same for the description + required ports 3000-80-

1. type- ssh
source type - My IP

2. type- HTTP
source type - Anywhere

To add another rule because we need to add the port 3000

3. port range - 3000
Source type - Anywhere
Type- Custom TCP
Description - For node app



Down in the summary- Number of instances to launch, in our case its 1

Lastly, we click on Launch and once launched we click on the ID provided and it takes us to Dashboard

Now we have to check the functionality.

After selecting our instance we click on the "Connect" button on top

From there we click on SSH client


**GitBash**

In the .ssh folder we run `chmod 400 devops-tech201.pem` (which is the name of the folder with the key) and we tn permissions to read only.

To check the premissions we run `ll`

Go back to AWS and copy the example code(confirming that I am the person that you provided the key to)

copy that into GitBash

After that we need to update and install the nginx

`sudo apt-get update -y`
`sudo apt-get install nginx -y`

After these steps are done we import the IP address into our browser to check the functionality of nginx()

**GitBash**

If everything is up to date so far we come back to our GitBash and exit our machine `exit`.













