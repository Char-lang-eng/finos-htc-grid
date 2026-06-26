[Dependency (1).md](https://github.com/user-attachments/files/29373084/Dependency.1.md)
* Deployment/grid  
  * Create\_ddb\_item.py \- creates tables in dynamodb  
  * Agent\_config.tf \- pulls results with dynamodb  
  * [main.tf](http://main.tf) \- References Dynamodb in the control plane to set read and write capacity and billing mode  
  * [variables.tf](http://variables.tf) \- Setting read and write capacity  
  * [dynamodb.tf](http://dynamodb.tf) \- manages DDB tables  
  * /terraform/controlplane  
    * [main.tf](http://main.tf) \- A dynamoDB table is added to this array: control\_plane\_kms\_key\_arns  
    * [variables.tf](http://variables.tf) \- Defines a bunch of variables involving dynamoDB   
    * [aws.iam.tf](http://aws.iam.tf) \- All of its actions make use of DynamoDB  
    * [vpc.tf](http://vfc.tf) \- dynamodb appears in the endpoints  
    * lambda\_cancel\_tasks.tf \- references ddb.state\_table  
    * lambda\_get\_results.tf \- references ddb.state\_table  
    * lambda\_scaling\_metrics.tf \- references ddb.state\_table  
    * lambda\_ttl\_checker.tf \- references ddb.state\_table  
  * /terraform/computeplane/files  
    * Filter-dashboard.json \- uses dynamodb queries  
    * Htc-dashboard.json \- mentions ddb regularly but does not depend on it  
* examples/configurations/  
  * custom\_runtime\_s3\_grid\_config.json.tpl \- uses aws workers, reads and writes with dynamodb  
  * full\_run\_grid\_config.json.tpl \- uses aws workers, reads and writes with dynamodb  
  * grid\_config.json.tpl \- uses aws workers, reads and writes with dynamodb  
  * java\_runtime\_grid\_config.json.tpl \- uses aws workers, reads and writes with dynamodb  
  * python\_runtime\_grid\_config.json.tpl \- uses aws workers, reads and writes with dynamodb  
* source/client/python/  
  * test\_apis\_redis.py \- references dynamodb\_results\_pull\_interval\_sec when creating a mock agent  
  * test\_api\_s3.py \- references dynamodb\_results\_pull\_interval\_sec when creating a mock agent  
  * [agent.py](http://agent.py) \- DynamoDB is involved in the running tasks   
  * scaling\_metrics.py \- Logs tasks completed in DynamoDB  
  * cancel\_tasks.py \- Creates a client and dynamoDB variable using boto3  
  * submit\_tasks.py \- submits tasks to dynamodb  
  * ttl\_checker.py \- Queries dynamodb   
  * [connector.py](http://connector.py) \- uses [agent.py](http://agent.py) to get results from dynamodb  
  * state\_table\_dynamodb.py regularly uses self.dynamoDb which is a boto3 resource  
  * state\_table\_manager.py \- imports StateTableDDB, which probably depends on dynamodb
