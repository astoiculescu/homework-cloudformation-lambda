# homework-cloudformation-lambda
Am creat bucket s3:
  aws s3api create-bucket --bucket homework-lambda-s3 --region eu-west-1

Am citit documentatia pt AWS SDK for Python si am facut un script in python ce incarca un fisier intr-un bucket s3

Am creat template-ul cloudformation pt functia lambda 


Pentru a muta codul de pe local in s3 am folosit comanda:
```
aws cloudformation package --template-file template.yaml --s3-bucket homework-lambda-s3 --output-template-file output.yaml
```

Deploy stack cu comanda:
  aws cloudformation deploy --template-file output.yaml --stack-name lambda-s3-stack --capabilities CAPABILITY_IAM
 
Cand am incercat sa creez stack-ul cu comanda de mai sus a returnat o eroare
Resource handler returned message: "Could not unzip uploaded file. Please check your file, then try to upload again. (Service: Lambda, Status Code: 400, Request ID: 899d6f2a-572f-4c79-9329-f7168786e04f, Extended Request ID: null)" (RequestToken: e421082a-c79d-f00a-5e53-3e0cefade29a, HandlerErrorCode: InvalidRequest)

Am modificat template-ul si am pus direct bucket name si bucket id si am creat stack-ul din consola.
 
 
 Documentatia AWS SDK for Python https://boto3.amazonaws.com/v1/documentation/api/latest/guide/s3-examples.html
 Am urmarit acest tutorial: https://advancedweb.hu/the-anatomy-of-a-cloudformation-template-with-a-simple-lambda-function/
