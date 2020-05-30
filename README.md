# CrossRegionCFNWithCodePipeline
Use CloudFormation to create a Pipeline in AWS CodePiepline to deply and manage a cross region CloudFormation stack.


Please follow the below steps in order to create the Pipeline and deploy the cross region CloudFormation stack successfully :

1. Create the source code. The source code Zip file (CodepipelineCrossRegion.zip) must contain the YAML or JSOM template file and a parameter configuration file.

2. Upload the Source code to the S3 bucket in the region where you will be creating the Pipeline. Make note of the name of this S3 bucket since it will be used as the 'S3Bucket' parameter during the creation of the main stack.

3. Make sure you have a bucket created in the target region to be mentioned as one of the artifact stores. This bucket name should be passed as the 'ArtifactStoreBucketTargetRegion' parameter.

4. Open the AWS Console and Navigate to CloudFormation console in the region where you would like to create the Pipeline.

5. Click on Create Stack option >> With new resources (standard) .

6. Choose 'Template is Ready' and for the template source , click on 'Upload a template'. You will get an option to choose the template from the local file. Download the template file or copy the template to a different file and upload it from the local machine. This template file will be automatically uploaded to the S3 bucket by CloudFormation.

7. Click on 'Next'. Now enter the 'Stack Name' and the 'Parameters' required for the stack creation. Please refer to Parameters section above for more information on what each parameter is used for in the template.

8. Click on 'Next'. Add any Tags or Service Role if you would like to here and also you can make use of the Advanced options provided by CloudFormation. - https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-add-tags.html

9. Click on 'Next'. Verify if all the parameters are passed correctly and also check other stack options if you have set any.

10. Make sure you acknowledge this message - 'I acknowledge that AWS CloudFormation might create IAM resources.' and then click on 'Create'.
