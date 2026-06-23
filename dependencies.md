Deployment/grid
  Create_ddb_item.py - creates tables in dynamodb
  Agent_config.tf - pulls results with dynamodb
  main.tf
  variables.tf
  aws.iam.tf
  dynamodb.tf
  /terraform/controlplane
    main.tf
    variables.tf
    vpc.tf
    lambda_cancel_tasks.tf - references ddb.state_table
    lambda_get_results.tf - references ddb.state_table
    lambda_scaling_metrics.tf - references ddb.state_table
    lambda_ttl_checker.tf - references ddb.state_table
  /terraform/computeplane/files
    filter-dashboard.json
    Htc-dashboard.json
examples/configurations/
  custom_runtime_s3_grid_config.json.tpl
  full_run_grid_config.json.tpl
  grid_config.json.tpl
  java_runtime_grid_config.json.tpl
  python_runtime_grid_config.json.tpl
source/client/python/
  test_apis_redis.py
  test_api_s3.py
  agent.py
  scaling_metrics.py
  cancel_tasks.py
  submit_tasks.py
  ttl_checker.py
  connector.py
  state_table_dynamodb.py
  state_table_manager.py
