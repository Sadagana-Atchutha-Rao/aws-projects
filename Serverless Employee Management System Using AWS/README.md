Instructions

1. Create a DynamoDB table with name employeeData , PK = employeeid, string
2. Create a IAM ROLE with Trusted Entity Lambda and Permissions Dynamodb and attach to Lambda functions
2. Create a Lambda FUnction, Name : getEmployee , attach role and copy paste the code
3. Create a Lambda FUnction, Name : insertEmployeeData , attach role and copy paste the code
4. Create a API Gateway : REST API : 
   Name: employee 
   API Endpoint type: Edge-Optimized (available everywhere, Region= Only for that Region)
   
   Create Method --> Method type : GET , Lambda Function, Region: mumbai, select getEmployee function --> create method
   Just Test the created method, if working or not
   
   Create Method --> Method type : POST , Lambda Function, Region: mumbai, select insertEmployeeData function --> create method
   
   Click on API employee --> Enable CORS --> GET and POST --> Save
  
   Deploy API --> New Stage --> employeeapi
   
   Copy the URL and update in script.js (https://y967l8if70.execute-api.ap-south-1.amazonaws.com/employeeapi)
   
4. Create a Public S3 Bucket and upload index.html and script.js
   Enable static website hosting --> open URL --> it will say access denied
   Go to Bucket Policy and generate a policy for getobject or make the objects public  --> put /* in policy
   
   OPen URL and Submit the data
5. Enable CF for the S3 with ROute53 DNS Name





   


{
  "Id": "Policy1722070443537",
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1722070442353",
      "Action": [
        "s3:GetObject"
      ],
      "Effect": "Allow",
      "Resource": "arn:aws:s3:::serverlessproject-own/*",
      "Principal": "*"
    }
  ]
}
