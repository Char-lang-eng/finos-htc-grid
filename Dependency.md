* Deployment/grid  
  * Create\_ddb\_item.py \- creates tables in dynamodb  
  * Agent\_config.tf \- pulls results with dynamodb  
  * [main.tf](http://main.tf)  
  * [variables.tf](http://variables.tf)  
  * [aws.iam.tf](http://aws.iam.tf)  
  * [dynamodb.tf](http://dynamodb.tf)  
  * /terraform/controlplane  
    * [main.tf](http://main.tf)  
    * [variables.tf](http://variables.tf)  
    * [vpc.tf](http://vfc.tf)  
    * lambda\_cancel\_tasks.tf \- references ddb.state\_table  
    * lambda\_get\_results.tf \- references ddb.state\_table  
    * lambda\_scaling\_metrics.tf \- references ddb.state\_table  
    * lambda\_ttl\_checker.tf \- references ddb.state\_table  
  * /terraform/computeplane/files  
    * filter-dashboard.json  
    * Htc-dashboard.json  
* examples/configurations/  
  * custom\_runtime\_s3\_grid\_config.json.tpl  
  * full\_run\_grid\_config.json.tpl  
  * grid\_config.json.tpl  
  * java\_runtime\_grid\_config.json.tpl  
  * python\_runtime\_grid\_config.json.tpl  
* source/client/python/  
  * test\_apis\_redis.py  
  * test\_api\_s3.py  
  * [agent.py](http://agent.py)  
  * scaling\_metrics.py  
  * cancel\_tasks.py  
  * submit\_tasks.py  
  * ttl\_checker.py  
  * [connector.py](http://connector.py)  
  * state\_table\_dynamodb.py  
  * state\_table\_manager.py