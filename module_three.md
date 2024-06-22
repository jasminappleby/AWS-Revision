# Regions

 When deciding the right Region for you services, data and applications, consider the following 4 business factors: 

- Compliance with data governance and legel requirements
    Depending on your company and location, you might need to run your data out of a specific area. 
    
    For example, if your company requires all of its data to reside within the boundaries of the UK, you could chose the London Region.
    
    This is not necessary for all companies, as not all companies have location-specific data regulations. This factor wouldn't be relevant. 

- Proximity to your customers
    Selecting a Region that is close to your customers will help you get content to them faster. 
    
    For example, your company is based in Washington, DC, and your customers live in Singapore. You might consider running your infrastructure in the Northern Virginia Region to be close to your company's headquarters, and run your applications from the Singapore Region to be close to your customers.

- Available services within a Region
    Sometimes, the closest Region may not have all the features you want to offer your customers. AWS is always working on innovation, so they are constantly making new services and expanding features within exisitng services. 
    
    However, making a new service available around the world sometimes requires AWS to build out physical hardware one Region at a time. 
    
    Suppose that your developers want to build an application that uses Amazon Bracket (AWS Quantum Computing Platform). Currently, Amazon Bracket is not yet available in every AWS Region around the world, so your developers would have to run it in one of the Regions that already offers it. 

- Pricing
    If you want to run an app in both the US and Brazil, it may cost you more to run the same workload out of Sao Paulo compared to Oregon. 
    Costs will vary region to region.


# Availability Zones
- An Availability Zones is a single data centre or a group of data centres within a single Region.
- Z are located tens of miles apart from each other.
- This is close enough to have low latency between AZ.
- However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that   multiple AZ are affected.

## Running EC2 instances in multiple AZ

### EC2 instance in a single Availability Zone
- Suppose that you are running an app on a single EC2 instance in the Northern California Region.
- The instance is running in the us-west-1a AZ. 
- If us-west-1a were to fail, you would lose your instance. 

### EC2 instances in multiple AZ
- Best practise is to run apps across at least two AZ in a Region.
- You may want to run us-west-1a and us-west-1b.

### Availability Zone failure
- If us-west-1a were to fail, your application would still be running in us-west-1b.


# Edge Locations
- A site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery. 

- If your company's data is stored in Brazil, and you have customers who live in China, to provice content to these customers, you don't need to move all your content to one of the Chinese Regions. 
- Instead of requiring your customers to get their data from Brazil, you can cache a copy locally at an edge location that is close to your customers in China.
- When a customer in China requests one of your files, Amazon CloudFront retrieves the file from the cache in the edge location and delivers the file to the customer. The file is delivered to the customer faster because it came from the edge location near China instead of the original source in Brazil.


# Ways to Interact with AWS Services

## AWS Management Console
- A web-based interface for accessing and managing AWS services.
- Quickly access recently used services and search for other services by name, keyword or acronym.
- Includes wizards and automated workflows that can simplify the process of completing tasks.
- Can also be used on a mobile app to monitor resources, viewing alarms and accessing billing information. 
- Multiple identities can stay logged into the AWS Console mobile app at the same time. 


## AWS Command Line Interface
- Enables you to control multiple AWS services directly from the CLI within one tool.
- Available on Windows, macOS and Linux. 
- Saves time when making API requests.
- Automate actions that your services and apps perform through scripts. (Launch EC2, connect an EC2 to specific Auto Scaling group, etc)

## Software development kits (SDKs)
- SDKs make it easier to use AWS services through an API designed for your programming language or platform.
- SDKs enable you to use AWS services with your existing apps or create entirely new apps that will run on AWS.
- AWS provides documentation and sample code for each supported programming language (C++, Java, .NET, etc)

# AWS Elastic Beanstalk and AWS CloudFormation

## Elastic Beanstalk
- You provide code and config settings, and Elastic Beanstalk deploys resources necessary to perform the following tasks: 
    - Adjust capacity
    - Load balancing
    - Automatic scaling 
    - Application health monitoring

## AWS CloudFormation
- You can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.
- Provisions your resources in a safe, repeatable manner, enabling you to frequently build your infrastructure and applications without having to perform manual actions or write custom scripts. 
- It determines the right operations to perform when managing your stack and rolls back automatically if it detecrs errors.




