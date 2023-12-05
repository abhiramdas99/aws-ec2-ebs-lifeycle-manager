# aws-ec2-ebs-lifeycle-manager
This actvities help  you about to taking the automatic backup of your server and remove the older snapshot after every 7 days automatically. 
## We require to configure the following two thing 
- ebs life cycle manager
- tag

## Lets follow the step to do it - 
- set  the tag key anme  and key value to  the ec2 instance
![image](https://github.com/abhiramdas99/aws-ec2-ebs-lifeycle-manager/assets/62290469/b2eedad3-1b61-4561-9f9c-3b8a0ef542d5)
  
- provide the same tag also to attached storage 
![image](https://github.com/abhiramdas99/aws-ec2-ebs-lifeycle-manager/assets/62290469/ce007d7d-2a18-4f54-afb7-b854a4db2b3d)

- Create lifecycle policy
  - navigate  to  : EC2 > Lifecycle Manager > Select policy type > Create lifecycle policy
  - follow the below step :
  ```git
  Step 1:	
	Target Resources : 
		Type : voume 
		tag : prod-daily-backup = yes
		
	Description :
		Daily Backup 
		
	IAM role:
	Default  role  
	
	Policy Status : enabled

step 2 : 
	Schedule Detail :
		sechedule name : daily backup 
		frequency : daily 
		Every : 12 hour
		Starting at : 01;00 utc
		Retention type : count , keep : 2 
  ```

