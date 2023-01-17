First log in to the console as the AWS account root user

Creating an IAM user
In this task, you will create an IAM user with administrator access.

In the Services search box, enter IAM, and open the IAM console.

In the navigation pane, choose Users.

Choose Add users and in the Set user details page, configure the following settings.
User name: Admin
Select AWS credential type:
Access key - Programmatic access
Password - AWS Management Console access
Console password: Custom password and enter a password of your choosing
Require password reset: Clear this option
Choose Next: Permissions.

In the Set permission page, choose Attach existing policies directly.

In the Filter policies box, search for administrator.

Under Policy name, select AdministratorAccess.

Choose Next: Tags, and then choose Next: Review.

Choose Create user.

You can sign in with the new IAM admin user by choosing the URL at the bottom of the Success window.

Note: The sign-in URL should look like the following: https://123456789012.signin.aws.amazon.com/console.

Log in to the console with the Admin user and password that you created.

Setting up an IAM role for an EC2 instance
In this task, you will log in as the Admin user and create an IAM role. The role allows Amazon Elastic Compute Cloud (Amazon EC2) to access both Amazon Simple Storage Service (Amazon S3) and Amazon DynamoDB. You will later assign this role to an EC2 instance that hosts the employee directory application.

Now that you are logged in as the Admin user, use the Services search bar to search for IAM again, and open the service by choosing IAM.

In the navigation pane, choose Roles.

Choose Create role.

In the Select trusted entity page, configure the following settings.
Trusted entity type: AWS service
Use case: EC2
Choose Next.

In the permissions filter box, search for amazons3full, and select AmazonS3FullAccess.

In the filter box, search for amazondynamodb, and select AmazonDynamoDBFullAccess.

Choose Next.

For Role name, paste S3DynamoDBFullAccessRole and choose Create role.