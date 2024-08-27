# EC2-Instance-Management-and-IAM-Policy-Configuration

Launch EC2 instance and create IAM user with restricted access. This ensures vital resources are protected from unauthorized changes.
Services used are:
1. AWS EC2
2. Identity and Access Management (IAM)

## Step 1 (Launch EC2 instance)

1. Navigate to EC2 service from management console search bar and select launch console option.
   
![ec21](https://github.com/user-attachments/assets/afef3163-0bdd-47bb-b3cd-936fce1bbecf)



2. Configure the instance to use access key pairs so SSH can be done securely into the instance when the need be.
   

![ec22](https://github.com/user-attachments/assets/f38951a9-0e4a-4dfc-96e4-76c39b548f8e)

## Step 2 ( Create IAM policy)

1. Navigate to IAM service and choose "Policies" from the sidebar. Then select "create policy" within that tab.


![iam1](https://github.com/user-attachments/assets/60f56ced-0854-4155-a4e5-06982a18f277)



2. Write policy and use the instance ARN to narrow down the permissions to that instance only. This policy only allows the user permission to start/stop that instance in particular only.


![iam3](https://github.com/user-attachments/assets/d66dae21-f6fe-44ff-a1ac-b003a379da7c)


3. Name the policy and its details in the desription box and save.


![iam4](https://github.com/user-attachments/assets/05a235b1-96fb-4349-bc99-4046951ba947)



## Step 3 ( Create IAM user and attach policy )

1. Within IAM service, navigate to user tab on the sidebar. Select create user.


![iamuser1](https://github.com/user-attachments/assets/31b98fb5-07df-4af7-bb53-e060180615b9)


2. As a security measure enable the option to require the new user to change the password upon first login.


![iamuser2](https://github.com/user-attachments/assets/a8d57195-00a2-4a17-abc6-0f7a24937725)


3. The next is to assign permissions to the user. Now search for the custom policy created in the previous text and attach it directly to the new user. And hit the next button to review and finally create the new user.


![iamuser4](https://github.com/user-attachments/assets/0543aefd-dabe-4eb4-a3ea-b49a94f98f9c)


4. Use the console sign-in URL to gain console access to the IAM user account.


![iamuser6](https://github.com/user-attachments/assets/cd051fb4-fde7-44e4-b873-50c53b83c2c8)


## Step 4 ( Log in and verify attached permissions are working properly)

1. Follow the link and you will be required to enter login credentials after which you'll be required to create a new password.


![iamlog2](https://github.com/user-attachments/assets/99cab77b-794d-4dbb-b3f0-d800a80ccfa8)

2. After logging in, navigate to EC2 service ( Side note: Make sure region is set to the same region in which instance was deployed.)
The instance is visble and accessible due to the policy attached to the user. Proceed to test the start/stop functionality.


![iamlog4](https://github.com/user-attachments/assets/aecef038-e4f0-402e-a46e-3427ba880836)


3. Attempt to terminate the instance and you'll be met with an error message. This verifies that the permission policy is functioning as it is supposed to.


![iamlog6](https://github.com/user-attachments/assets/70e510f0-7032-45d6-8817-40231f8e3e77)


