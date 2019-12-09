# aws-bulk-tagging
 A tool for tagging AWS resources massively.

## Goal
Apply a list of tags to a set of AWS resources.

## Use case
You want to add or update the following tags:
                    
| Key  | Value |
| ------------- | ------------- |
| Entity  | SALES  |
                    

To all EC2 instances tagged with:
                    
| Key  | Value |
| ------------- | ------------- |
| Stage  | PROD  |
| App  | AWESOME_SALES_APP  |
                    

In this case, the request payload will be:
```json
{
  "TagFilters": [
    {
      "Key": "Stage",
      "Values": [
        "PROD"
      ]
    },
    {
      "Key": "App",
      "Values": [
        "AWESOME_SALES_APP"
      ]
    }
  ],
  "TagsToApply": {
      "Entity": "SALES"
   },
  "ResourceTypeFilters": [
    "ec2:instance"
  ]
}
```

# How to use it?

## Solution 1
1. Install the Serverless Framework
https://serverless.com/
2. Configure your account and create at least one profile on your dashboard:
https://dashboard.serverless.com/
3. Clone this repository
4. Open a terminal on your local project directory:
`$ sls deploy [--stage dev] [--region eu-west-1]`

## Solution 2
