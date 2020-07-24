# AWS Lambda with Java: A simple serverless example

## Steps

1. Import the aws-lambda-java-core package (Maven).
```
        <dependency>
            <groupId>com.amazonaws.serverless</groupId>
            <artifactId>aws-serverless-java-container-spring</artifactId>
            <version>1.4</version>
        </dependency>
```        
2. Write your code (Java 8).

3. Package your code (Maven).
Run
````
mvn package
````
That’ll output a jar file with your function under 'target' directory

4. Deploy your package (AWS Lambda).
   * Login to the AWS console and go to the Lambda compute service. It’s under Services > Compute > Lambda. Or you can type “lambda” in the search bar.
   * Create Function: The runtime needs to be Java 8 or you won’t be able to run Java. As you may have noticed, there are several other options for runtime. Some of   those options allow you to edit your functions right in the AWS Console. But there’s no Java compiler in AWS Lambda, so you have to upload a compiled function. 
   * Click the Upload button and navigate that output jar file under target directory
   * Tell AWS Lamda the name of your handler. The pattern it needs is <package>.<class>::<function>

5 Test your AWS Lambda Function: 
  * From the Select a test event drop-down menu, choose the Configure test events option.
  * Event name and the body. For those, put SayHello for name and "Alice, Bob" for body.
  * Click Create, then hit the Test button and see if it shows you good news! It has the link to CloudWatch monitoring and logs of your Lambda app.       
  `Execution result: succeeded(logs)`       


