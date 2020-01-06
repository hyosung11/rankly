# rankly
Training in using AWS Lambda

### Amazon Lambda
- serverless applications: hand code over to the cloud provider
- underneath the hood the cloud provider creates a container (docker) and runs the function inside of it.
- cold start problem (downside because the function has to be grabbed from the database and this takes time)

### Amazon Lambda Dashboard
- created account
- Serverless Framework https://serverless.com/framework/docs/providers/aws/guide/intro/
- `serverless` installed `sls`
-`sls create -t aws-nodejs`
- serverless works with AWS as well as other providers like Azure and openwhisk (IBM)
- `sls config credentials --provider aws --key 1234 --secret abc`
`nano credentials`

- AWS Lambda `async`
```JavaScript
'use strict';
module.exports.hello = async (event, context) => {  
    return {    
        statusCode: 200,    
        body: JSON.stringify({      
            message: 'Go Serverless v1.0! Your function executed successfully!',      
            input: event,    
        }),  
    };    
// Use this code if you don't use the http event with the LAMBDA-PROXY integration  
// return { message: 'Go Serverless v1.0! Your function executed successfully!', event };
};
```
