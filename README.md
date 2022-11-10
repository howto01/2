def lambda_handler(event, context):  
   number1 = event['Number1']  
   number2 = event['Number2']  
   sum = number1 + number2  
   return {"Number1": number1 , "Number2": number2 , "Sum": sum} 



var aws = require(“aws-sdk”);  
var ses = new aws.SES({ region: “ap-south-1” });  
exports.handler = async function (event) {  
var params = {  
Destination: {  
ToAddresses: [“-inft@atharvacoe.ac.in”],  
},  
Message: {  
Body: {  
Text: { Data: “this is the notification msg that object is uploaded in the bucket” }, },  
Subject: { Data: “notification” },  
},  
Source: “-inft@atharvacoe.ac.in”,  
};  
return ses.sendEmail(params).promise()  
};  
