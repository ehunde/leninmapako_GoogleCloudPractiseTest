# Console and Cloud Shell

## Objectives:

In this lab, you learn how to perform the following tasks:

   - Create a Cloud Storage bucket using the Cloud Console.

   - Create a Cloud Storage bucket using Cloud Shell.

   - Become familiar with Cloud Shell features.

## Steps:

1. Create a Cloud Storage bucket using the Cloud Console.
   
       gsutil mb gs://my-lenysalesdata-bucket/

2. Create a Cloud Storage bucket using Cloud Shell.
    
       gsutil mb gs://my-lenysalesdata-bucket2/

3. Become familiar with Cloud Shell features.

    - Explore more Cloud Shell features

	### Upload a file

		- Click Upload file. Upload any file from your local machine to the Cloud Shell VM. 
		       
		       gcloud alpha cloud-shell scp localhost:~/myfile.txt cloudshell:~myfile.txt 

		- In Cloud Shell, type ls to confirm that the file was uploaded.

		       ls

		- Copy the file into one of the buckets you created earlier in the lab.

		       gsutil cp myfile.txt gs://lenysalesdata-bucket

	- Create a persistent state in Cloud Shell

    ### Identify available regions
        
         - To list available regions, execute the following command:

               gcloud compute regions list

    ### Create and verify an environment variable

         - Create an environment variable and replace [YOUR_REGION] with the region you selected in the previous step:

               INFRACLASS_REGION=us-central1

         - Verify it with echo:

                echo $INFRACLASS_REGION

    ### Append the environment variable to a file

         - Create a subdirectory for materials used in this class:

                mkdir infraclass

         - Create a file called config in the infraclass directory:

                touch infraclass/config

         - Append the value of your Region environment variable to the config file:

                echo INFRACLASS_REGION=$INFRACLASS_REGION >> ~/infraclass/config

         - Create a second environment variable for your Project ID:

                INFRACLASS_PROJECT_ID=qwiklabs-gcp-0977r234567b8409

         - Append the value of your Project ID environment variable to the config file:
                
               echo INFRACLASS_PROJECT_ID=$INFRACLASS_PROJECT_ID >> ~/infraclass/config

         - Use the source command to set the environment variables, and use the echo command to verify that the project variable was set:
               
               source infraclass/config
               echo $INFRACLASS_PROJECT_ID

         - Close and re-open Cloud Shell. Then issue the echo command again:

               echo $INFRACLASS_PROJECT_ID


    ### Modify the bash profile and create persistence

         - Edit the shell profile with the following command:
              
               nano .profile

         - Add the following line to the end of the file:

               source infraclass/config

         - Use the echo command to verify that the variable is still set:

               echo $INFRACLASS_PROJECT_ID










