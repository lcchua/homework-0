_Q1: A CloudFormation template creates infrastructure resources in a group called?_
* A: Config
* **B: Stack**
* C: YML File
* D: JSON

_Q2: Elastic Beanstalk will provision and operate all necessary infrastructure, including?_
* A: Servers
* B: Databases
* C: Load Balancer
* **D: All of the above**

_Q3: A company wants to setup a template for deploying resources to AWS. They want this to be dynamic in nature so that the template can pick up parameters and then spin up resources based on those parameters. Which of the following AWS services would be ideal for this requirement?_
* A: AWS Beanstalk
* **B: AWS CloudFormation**
* C: WS CodeBuild
* D: AWS CodeDeploy

_Q4: Your company’s management team has asked you to devise a disaster recovery strategy for the current resources hosted in AWS. They want to minimize costs, but be able to spin up the infrastructure when needed in another region. How could you accomplish this with the LEAST costs in mind?_
* A: Create a duplicate of the entire infrastructure in another region.
* B: Create a Pilot Light infrastructure in another region.
* C: Use Elastic Beanstalk to create another copy of the infrastructure in another region if a disaster occurs in the primary region.
* **D: Use CloudFormation to spin up resources in another region if a disaster occurs in the primary region.**

_Q5: A company has three different environments: Development, QA, and Production. The company wants to deploy its code first in the Development environment, then QA, and then Production.Which AWS service can be used to meet this requirement?_
* A: Use AWS Data Pipeline to create multiple data pipeline provisions to deploy the application
* B: Use AWS CodeBuild to create, configure, and deploy multiple build application projects
* **C: Use AWS CodeDeploy to create multiple deployment groups**
* D: Use AWS CodeCommit to create multiple repositories to deploy the application

_Q6: A company planning to move to the AWS Cloud, wants to leverage its existing Chef recipes for configuration management of its infrastructure. Which AWS service would be ideal for this requirement?_
* A: AWS Elastic Load Balancer
* B: AWS Elastic Beanstalk
* **C: AWS OpsWorks**
* D: AWS Inspector

_Q7: A company’s requirement is to have a Stack-based model for its resources in AWS. There is a need to have different stacks for the Development and Production environments. Which of the following can be used to fulfill this required methodology?_
* A: Use EC2 tags to define different stack layers for your resources.
* B: Define the metadata for the different layers in DynamoDB.
* **C: Use AWS OpsWorks to define the different layers for your application.**
* D: Use AWS Config to define the different layers for your application.

_Q8: You have been tasked with architecting an application in AWS. The architecture would consist of EC2, the Classic Load Balancer, Auto Scaling and Route 53. There is a directive to ensure that Blue-Green deployments are possible in this architecture. Which routing policy could you ideally use in Route 53 for achieving Blue-Green deployments?_
* A: Simple
* B: Multi-answer
* C: Latency
* **D: Weighted**

_Q9: An in-place deployment is a deployment strategy that updates the application version without replacing any infrastructure components. True or False?_
* **A: True**
* B: False

**Q10: A rolling deployment is a deployment strategy that slowly replaces previous versions of an application with new versions of an application by completely replacing the infrastructure on which the application is running. True or False?**
* **A: True**
* B: False
